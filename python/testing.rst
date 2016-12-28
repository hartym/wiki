Testing with Python
===================

Pytest recipes
::::::::::::::

Parametrizing fixtures and test functions
-----------------------------------------

Reference: http://doc.pytest.org/en/latest/parametrize.html

.. code-block:: python

    import pytest
    @pytest.mark.parametrize("test_input,expected", [
        ("3+5", 8),
        ("2+4", 6),
        ("6*9", 42),
    ])
    def test_eval(test_input, expected):
        assert eval(test_input) == expected

Other libraries
:::::::::::::::

* `Hypothesis <https://hypothesis.readthedocs.io/>`_
* `Cassette <http://cassette.readthedocs.io/>`_

