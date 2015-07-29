Game of Go
==========

This is not about golang, but about the Game of Go.

If you don't know what it is about, you can discover the game of go on http://senseis.xmp.net/?WhatIsGo and interactively discover the rules of the game by following the tutorial at http://playgo.to/iwtg/en/ (also available in a lot of other languages).

Game resources
::::::::::::::

* Charles Matthews' "On Your Side" (fuseki): http://gobase.org/studying/articles/matthews/fuseki/
* http://senseis.xmp.net/
* http://francois.mizessyn.pagesperso-orange.fr/ (french)
* http://internetgoschool.com/

Computer Go
:::::::::::

Go is interesting for a computer scientist because 1) the possible combinations of valid positions outruns by far any computer or computer cluster, forbidding bruteforce approaches and 2) comparative evaluation of two positions is very difficult for a computer.

Traditionaly, people tried to make computers play go with algorithms that mimics human reflection and strategy, achieving very poor results (any good beginner could beat the strongest bot). Since a few years, new approaches have come up, like the use of "Monte Carlo" based algorithms (basically bots that play based on the statistics obtained by playing a high number of random games from the actual position, can run massively on parralel independant computers) or CNN (machine learning approach trained on databases of professional games).


Convolutional Neural Networks
-----------------------------

* http://arxiv.org/pdf/1412.3409v1.pdf
* http://www.cs.toronto.edu/~cmaddis/pubs/deepgo.pdf
