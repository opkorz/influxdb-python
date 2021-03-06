

InfluxDB-Python is a client for interacting with InfluxDB_.

.. image:: https://travis-ci.org/influxdb/influxdb-python.svg?branch=master
    :target: https://travis-ci.org/influxdb/influxdb-python

.. image:: https://readthedocs.org/projects/influxdb-python/badge/?version=latest&style
    :target: https://readthedocs.org/projects/influxdb-python/?badge=latest
    :alt: Documentation Status

.. image:: https://img.shields.io/coveralls/influxdb/influxdb-python.svg
  :target: https://coveralls.io/r/influxdb/influxdb-python
  :alt: Coverage

.. image:: https://pypip.in/download/influxdb/badge.svg
    :target: https://pypi.python.org/pypi//influxdb/
    :alt: Downloads

.. image:: https://pypip.in/version/influxdb/badge.svg
    :target: https://pypi.python.org/pypi/influxdb/
    :alt: Latest Version

.. image:: https://pypip.in/py_versions/influxdb/badge.svg
    :target: https://pypi.python.org/pypi/influxdb/
    :alt: Supported Python versions

.. image:: https://pypip.in/license/influxdb/badge.svg
    :target: https://pypi.python.org/pypi/influxdb/
    :alt: License

.. _readme-about:

InfluxDB is an open-source distributed time series database, find more about InfluxDB_ at http://influxdb.com/


.. _installation:

Installation
============

Install, upgrade and uninstall InfluxDB-Python with these commands::

    $ pip install influxdb
    $ pip install --upgrade influxdb
    $ pip uninstall influxdb

On Debian/Ubuntu, you can install it with this command::

    $ sudo apt-get install python-influxdb

Dependencies
============

The InfluxDB-Python distribution is supported and tested on Python 2.7 and Python 3.3.

Main dependencie is:

- Requests: HTTP library for human beings (http://docs.python-requests.org/)


Additional dependencies are:

- Sphinx: Tool to create and manage the documentation (http://sphinx-doc.org/)
- Nose: to auto-discover tests (http://nose.readthedocs.org/en/latest/)
- Mock: to mock tests (https://pypi.python.org/pypi/mock)


Documentation
=============

InfluxDB-Python documentation is available at http://influxdb-python.readthedocs.org

You will need Sphinx_ installed to generate the documentation.

The documentation can be generated by running::

    $ tox -e docs


Generated documentation can be found in the *docs/build/html/* directory.


Examples
========

Here's a basic example (for more see the examples directory)::

    $ python

    >>> from influxdb import InfluxDBClient

    >>> json_body = [{
        "points": [
            ["1", 1, 1.0],
            ["2", 2, 2.0]
        ],
        "name": "foo",
        "columns": ["column_one", "column_two", "column_three"]
    }]

    >>> client = InfluxDBClient('localhost', 8086, 'root', 'root', 'example')

    >>> client.create_database('example')

    >>> client.write_points(json_body)

    >>> result = client.query('select column_one from foo;')

    >>> print("Result: {0}".format(result))


Testing
=======

Make sure you have tox by running the following::

    $ pip install tox

To test influxdb-python with multiple version of Python, you can use Tox_::

    $ tox


Support
=======

For issues with, questions about, or feedback for InfluxDB_, please look into
our community page: http://influxdb.com/community/.


Development
===========

All development is done on Github_. Use Issues_ to report
problems or submit contributions.

.. _Github: https://github.com/influxdb/influxdb-python/
.. _Issues: https://github.com/influxdb/influxdb-python/issues


Source code
===========

The source code is currently available on Github: https://github.com/influxdb/influxdb-python


.. _InfluxDB: http://influxdb.com/
.. _Sphinx: http://sphinx.pocoo.org/
.. _Tox: https://tox.readthedocs.org
