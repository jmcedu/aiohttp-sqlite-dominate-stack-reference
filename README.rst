aiohttp-sqlite-dominate-stack-reference
=======================================

**aiohttp-sqlite-dominate-stack-reference** is a skeletal implementation of an
aiohttp-based web application that uses sqlite
(`aiosqlite <https://github.com/jreese/aiosqlite>`_, actually) for the
database access and `dominate <https://github.com/Knio/dominate>`_ for HTML
generation (rather than a templating language/tool).  The feature set is
intentionally vapid, meant only to demonstrate the basics and offer a
starting-point.

Install and Configuration
-------------------------
::

	$ python3 -m venv ve
	$ . ve/bin/activate
	$ pip install --upgrade pip
	$ git clone https://github.com/jmcedu/aiohttp-sqlite-dominate-stack-reference.git
	$ cd cd aiohttp-sqlite-dominate-stack-reference/
	$ pip install -r requirements.txt

Create the tiny starter reference database::

	$ cat test1.sql | sqlite3 test1.db

And run your app::

	$ python -m aiohttp.web -H localhost -P 8080 test1_app.main:init
	
(Or, with `aiohttp-devtools <https://github.com/aio-libs/aiohttp-devtools>`_)::

	$ adev runserver --livereload test1_app

(Other adev options may be desirable, and additions like 
`aiohttp-debugtoolbar <https://github.com/aio-libs/aiohttp-debugtoolbar>`_
might be useful.)

Finally, launch a browser and go to http://localhost:8080/select_test1 or one
of the other handlers to interact with the app.

License
-------

This project is licensed under the terms of the MIT license.
