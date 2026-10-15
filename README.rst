.. image:: https://img.shields.io/coveralls/github/timcera/tsgettoolbox_modis
    :alt: Test Coverage
    :target: https://coveralls.io/r/timcera/tsgettoolbox_modis?branch=master
    :height: 20

.. image:: https://img.shields.io/pypi/v/tsgettoolbox_modis
    :alt: Latest release
    :target: https://pypi.python.org/pypi/tsgettoolbox_modis/
    :height: 20

.. image:: https://img.shields.io/pypi/l/tsgettoolbox_modis
    :alt: BSD-3 clause license
    :target: https://pypi.python.org/pypi/tsgettoolbox_modis/
    :height: 20

.. image:: https://img.shields.io/pypi/pyversions/tsgettoolbox_modis
    :alt: PyPI - Python Version
    :target: https://pypi.org/project/tsgettoolbox_modis/
    :height: 20

tsgettoolbox_modis - Quick Guide
================================
The 'tsgettoolbox_modis' is a plugin-in for 'tsgettoolbox' that supplies
a command line interface and Python library to get time-series data from the
MODIS.  The tsgettoolbox_modis will work with Python 3.10+.

Documentation
-------------
Reference documentation is at `tsgettoolbox MODIS API`_.

Installation
------------
At the command line::

    $ pip install tsgettoolbox_modis

    OR

    $ conda install -c conda-forge tsgettoolbox_modis

Usage Summary - Command Line
----------------------------
Just run 'tsgettoolbox --help' to get a list of subcommands.  To get detailed
help for a particular sub-command, for instance 'modis', type 'tsgettoolbox
modis --help'.

+-------------+---------+--------+---------+----------+-----------------------+
| Sub-command | Spatial | Time   | Type    | Time     | Description           |
|             | Extent  | Extent |         | Interval |                       |
+=============+=========+========+=========+==========+=======================+
| modis       | global  | 2000-  | grid    | 4D,8D,   | MODIS derived data    |
|             |         |        | 250m,   | 16D,A    |                       |
|             |         |        | 500m,   |          |                       |
|             |         |        | 1000m   |          |                       |
+-------------+---------+--------+---------+----------+-----------------------+

+-------------------+-------------+
| Time Interval     | Description |
| Code              |             |
+===================+=============+
| D                 | Daily       |
+-------------------+-------------+
| A                 | Annual      |
+-------------------+-------------+

Usage Summary - Python Library
------------------------------
To use the tsgettoolbox in a project::

    from tsgettoolbox import tsgettoolbox
    df = tsgettoolbox.modis(
        product="MOD15A2H",
        band="Lai_500m",
        lat=29.75,
        lon=-82.32,
        start_date="3 years ago",
        end_date="2 years ago",
    )
    print(df.head())

Refer to the API Documentation at `tsgettoolbox MODIS API`_.

Usage Summary - Command Line
----------------------------

    tsgettoolbox modis \
        --product="MOD15A2H" \
        --band="Lai_500m" \
        --lat=29.75 \
        --lon=-82.32 \
        --start_date="3 years ago" \
        --end_date="2 years ago" > output.csv

Refer to the command line documentation at `tsgettoolbox MODIS CLI`_.

Development
~~~~~~~~~~~
Development is managed on bitbucket or github.
https://bitbucket.org/timcera/tsgettoolbox_modis/overview.
https://github.com/timcera/tsgettoolbox_modis

.. _tsgettoolbox_documentation: https://timcera.bitbucket.io/linked_pkg_dirs/tsgettoolbox/docs/index.html
.. _tsgettoolbox MODIS API: https://timcera.bitbucket.io/linked_pkg_dirs/tsgettoolbox/docs/_function_autosummary/tsgettoolbox.modis.html
.. _tsgettoolbox MODIS CLI: https://timcera.bitbucket.io/linked_pkg_dirs/tsgettoolbox/docs/command_line.html#modis
