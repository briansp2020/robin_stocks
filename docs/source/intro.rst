
Introduction
============

----

.. image:: _static/pics/wolf.jpg

Philosophy
----------

I've written the code in accordance with what I consider the best coding practices.
Some of these are part of `PEP 20 <https://www.python.org/dev/pep-0020>`_ standards and some are my own. They are as follows:

* Explicit is better than implicit

This is the reason why my code uses ``import robin_stocks.module as module`` instead of ``from module import *``.
This means that calls to a function from the module must be written as ``module.function`` instead of the simply
``function``. When viewing the code, it's easy to see which functions come from which modules.

* Flat is better than nested

The __init__.py file contains an import of all the functions I want to be made public to the user. This allows
the user to call ``robin_stocks.function`` for all functions. Without the imports, the user would have to call
``robin_stocks.module.function`` and be sure to use the correct module name every single time. This may seem contradictory
to the first standard, but the difference is that whereas I the developer must make explicit calls, for the end user it is
unnecessary.

* Three strikes and you refactor

If you find yourself copying and pasting the same code 3 or more times, then it means you should put that code in
its own function. Thus, I created the :func:`robin_stocks.helper.request_get` function, and then provided input parameters to
handle different use cases.

* Type is in the name

A person should be able to look at the code and know the purpose of all the names they see. For this reason
I have written names of functions as ``snake_case``, names of input parameters and local function variables as
``camelCase``, and names of global variables, class names, and enum names as ``PascalCase``

License
-------

Copyright (c) 2018 Joshua M. Fernandes

Permission is hereby granted, free of charge, to any person obtaining a copy of
this software and associated documentation files (the "Software"), to deal in
the Software without restriction, including without limitation the rights to
use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies
of the Software, and to permit persons to whom the Software is furnished to do
so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
