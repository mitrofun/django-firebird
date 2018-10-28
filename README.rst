===============
django-firebird
===============

Firebird SQL backend for django
-------------------------------

**Repo Note**:

This project is fork (django-firebird)[https://github.com/maxirobaina/django-firebird]


This version of django-firebird is working with *fbd* [1], therefore it will work only with firebird 2.x and later.
*fbd* is the official stable python-firebird driver, also it has support for python 3.


[1] http://pypi.python.org/pypi/fdb/


Requirements
------------
  * Python Python 3.x
  * Django 2.0
  * fdb (http://pypi.python.org/pypi/fdb/)

Instalation
-----------

**Using pip**

    pip install -e git+https://github.com/mitrofun/django-firebird#egg=django-firebird


Configuration
-------------

Modify your setting.py ::

    DATABASES = {
        'default': {
            'ENGINE' : 'firebird',
            'NAME' : '/var/lib/firebird/2.5/data/django_firebird.fdb', # Path to database or db alias
            'USER' : 'SYSDBA',           # Your db user
            'PASSWORD' : '*****',    # db user password
            'HOST' : '127.0.0.1',        # Your host machine
            'PORT' : '3050',             # If is empty, use default 3050
            #'OPTIONS' : {'charset':'ISO8859_1'}
        }
    }

Known bugs and issues
---------------------

* Some database migrations doesn't work by default. Sometimes is better make intermediate migrations for solve problems.
* Some Query Expressions doesn't work by default. We need to make some workaround, ie: Use Cast().
* Combined duration expressions need more research. No all combination of expressions works.


Legacy driver
-------------

Why the change from kinterbasdb to fdb?

If you want to know more about the differences between *fdb* and *kinterbasdb* you can look at:

http://thread.gmane.org/gmane.comp.db.firebird.python/185/focus=187

http://pythonhosted.org//fdb/differences-from-kdb.html

If you still use *kinterbasdb*, the original google code repository has an updated django-firebird 1.4.x LTS version.

https://github.com/mariuz/django-firebird-1.4
