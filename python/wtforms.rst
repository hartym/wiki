WTForms
=======

WTForms is a framework agnostic library handling web forms in python.

Official documentation: https://wtforms.readthedocs.org/en/latest/

Basics
::::::

Create a form...

.. code-block:: python

    class UrlFilterForm(wtforms.Form):
        scheme = wtforms.StringField()
        netloc = wtforms.StringField()
        path = wtforms.StringField()
        query = wtforms.StringField()
        fragment = wtforms.StringField()
        
Render it in a jinja2 template...

.. code-block:: python

    <form class="form-inline">
        {% for field in form %}
            <div class="form-group">
                {{ field.label }}{% if field.flags.required %}*{% endif %}
                {{ field(class='form-control') }}
            </div>
        {% endfor %}
        <button type="submit" class="btn btn-outline-primary">Submit</button>
    </form>


Cookbook
::::::::

Basic form handler
------------------

.. code-block:: python

  def handle(self, request):
        form = MyForm(request.form)

        if request.method == 'POST' and form.validate():
            # validation succeeded, handle success here
            return self.redirect('...')

        return self.render_template('...', form=form)


Basic template (bootstrap enabled)
----------------------------------

.. code-block:: html+jinja

    <form class="form-horizontal" method="post" action="">
        {{ form.some_hidden_field() | safe }}
        
        <!-- ... more hidden fields ... -->
        
        <div class="form-group {% if form.some_field.errors %}has-error{% endif %}">
            {{ form.some_field.label(class="col-sm-2 control-label") }}
            <div class="col-sm-10">
                {{ form.some_field(class='form-control') | safe }}
                {% if form.some_field.errors %}
                    <ul class="errors">{% for error in form.some_field.errors %}<li>{{ error }}</li>{% endfor %}</ul>
                {% endif %}
            </div>
        </div>
        
        <!-- ... more fields ... -->
        
        <div class="form-group">
            <div class="col-sm-offset-2 col-sm-10">
                <button type="submit" class="btn btn-default">Add</button>
            </div>
        </div>
    </form>


Override default once form is instanciated
------------------------------------------

This cannot be done by setting ``form.myfield.default`` after the form is instanciated, because apparently wtforms copy the default value into the field data at this time (see http://stackoverflow.com/questions/5519729/wtforms-how-to-select-options-in-selectmultiplefield/5519971). You can still override the data.

.. code-block:: python

        form.my_field.data = '...'
        
Dynamically add errors after form validation
--------------------------------------------

.. code-block:: python

        form.my_field.errors.append('Caramba!')
