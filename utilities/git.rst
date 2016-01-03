Git
===

Aliases
:::::::

.. code-block:: shell

	git config --global alias.ci commit
	git config --global alias.st status
	git config --global alias.co checkout
	git config --global alias.br branch
	git config --global alias.lg "log --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit"

User setup
::::::::::

.. code-block:: shell

	git config --global user.name "Romain Dorgueil"
	git config --global user.email "romain@dorgueil.net"

	
References
::::::::::

* `Original article with my git config and aliases <http://romain.dorgueil.net/blog/en/git/2014/12/16/git-config.html>`_
* Github flow: https://guides.github.com/introduction/flow/
* Git-flow: http://nvie.com/posts/a-successful-git-branching-model/


*Deprecated* - Colors (not required after git 1.8.4)
::::::::::::::::::::::::::::::::::::::::::::::::::::

.. code-block:: shell

	git config --global color.branch auto
	git config --global color.diff auto
	git config --global color.interactive auto
	git config --global color.status auto

or

.. code-block:: shell

	git config --global color.ui true
