0.8.4 (unreleased)
------------------

- Nothing changed yet.


0.8.3 (2021-07-07)
------------------

- SQLAlchemy 1.4.x support
  (`Pull #221 <https://github.com/sqlalchemy-redshift/sqlalchemy-redshift/pull/221>`_)


0.8.2 (2021-01-08)
------------------

- Allow supplying multiple role ARNs in COPY and UNLOAD commands. This allows
  the first role to assume other roles as explained
  `here <https://docs.aws.amazon.com/redshift/latest/mgmt/authorizing-redshift-service.html#authorizing-redshift-service-chaining-roles>`_.


0.8.1 (2020-07-15)
------------------

- Support AWS partitions for role-based access control in COPY and UNLOAD
  commands. This allows these commands to be used, e.g. in GovCloud.


0.8.0 (2020-06-30)
------------------

- Add option to drop materialized view with CASCADE
  (`Pull #204 <https://github.com/sqlalchemy-redshift/sqlalchemy-redshift/pull/204>`_)
- Fix invalid SQLAlchemy version comparison
  (`Pull #206 <https://github.com/sqlalchemy-redshift/sqlalchemy-redshift/pull/206>`_)


0.7.9 (2020-05-29)
------------------

- Fix for supporting SQLAlchemy 1.3.11+
  (`Issue #195 <https://github.com/sqlalchemy-redshift/sqlalchemy-redshift/pull/195>`_)

0.7.8 (2020-05-27)
------------------

- Added support for materialized views
  (`Issue #202 <https://github.com/sqlalchemy-redshift/sqlalchemy-redshift/pull/202>`_)
- Fix reflection of unique constraints
  (`Issue #199 <https://github.com/sqlalchemy-redshift/sqlalchemy-redshift/pull/199>`_)
- Support for altering column comments in Alembic migrations
  (`Issue #191 <https://github.com/sqlalchemy-redshift/sqlalchemy-redshift/issues/191>`_)

0.7.7 (2020-02-02)
------------------

- Import Iterable from collections.abc for Python 3.9 compatibility
  (`Issue #189 <https://github.com/sqlalchemy-redshift/sqlalchemy-redshift/issues/189>`_)
- Add support for Parquet format in ``UNLOAD`` command
  (`Issue #187 <https://github.com/sqlalchemy-redshift/sqlalchemy-redshift/issues/187>`_)


0.7.6 (2020-01-17)
------------------

- Fix unhashable type error for sortkey reflection in SQLAlchemy >= 1.3.11
  (`Issue #180 <https://github.com/sqlalchemy-redshift/sqlalchemy-redshift/pull/180>`_)
- Expose supported types for import from the dialect
  (`Issue #181 <https://github.com/sqlalchemy-redshift/sqlalchemy-redshift/issues/181>`_)
- Reflect column comments
  (`Issue #186 <https://github.com/sqlalchemy-redshift/sqlalchemy-redshift/pull/186>`_)


0.7.5 (2019-10-09)
------------------

- Extend psycopg2 package version check to also support psycopg2-binary and psycopg2cffi
  (`Issue #178 <https://github.com/sqlalchemy-redshift/sqlalchemy-redshift/pull/178>`_)


0.7.4 (2019-10-08)
------------------

- Drop hard dependency on psycopg2 but require package to be present on runtime
  (`Issue #165 <https://github.com/sqlalchemy-redshift/sqlalchemy-redshift/pull/165>`_)
- Switch from info to keyword arguments on columns for ``SQLAlchemy >= 1.3.0``
  (`Issue #161 <https://github.com/sqlalchemy-redshift/sqlalchemy-redshift/pull/161>`_)
- Add support for column info on redshift late binding views
  (`Issue #159 <https://github.com/sqlalchemy-redshift/sqlalchemy-redshift/pull/159>`_)
- Add support for ``MAXFILESIZE`` argument to ``UNLOAD``.
  (`Issue #123 <https://github.com/sqlalchemy-redshift/sqlalchemy-redshift/issues/123>`_)
- Add support for the `CREATE LIBRARY`_ command.
  (`Issue #124 <https://github.com/sqlalchemy-redshift/sqlalchemy-redshift/issues/124>`_)
- Add support for the `ALTER TABLE APPEND`_ command.
  (`Issue #162 <https://github.com/sqlalchemy-redshift/sqlalchemy-redshift/pull/162>`_)
- Add support for the ``CSV`` format to `UnloadFromSelect`.
  (`Issue #169 <https://github.com/sqlalchemy-redshift/sqlalchemy-redshift/issues/169>`_)
- Update the list of reserved words (adds "az64" and "language")
  (`Issue #176 <https://github.com/sqlalchemy-redshift/sqlalchemy-redshift/issues/176>`_)

.. _CREATE LIBRARY: https://docs.aws.amazon.com/redshift/latest/dg/r_CREATE_LIBRARY.html
.. _ALTER TABLE APPEND: https://docs.aws.amazon.com/redshift/latest/dg/r_ALTER_TABLE_APPEND.html


0.7.3 (2019-01-16)
------------------

- Add support for ``REGION`` argument to ``COPY`` and ``UNLOAD`` commands.
  (`Issue #90 <https://github.com/sqlalchemy-redshift/sqlalchemy-redshift/issues/90>`_)


0.7.2 (2018-12-11)
------------------

- Update tests to adapt to changes in Redshift and SQLAlchemy
  (`Issue #140 <https://github.com/sqlalchemy-redshift/sqlalchemy-redshift/pull/140>`_)
- Add `header` option to `UnloadFromSelect` command
  (`Issue #156 <https://github.com/sqlalchemy-redshift/sqlalchemy-redshift/pull/156>`_)
- Add support for Parquet and ORC file formats in the COPY command
  (`Issue #151 <https://github.com/sqlalchemy-redshift/sqlalchemy-redshift/pull/150>`_)
- Add official support for Python 3.7
  (`Issue #153 <https://github.com/sqlalchemy-redshift/sqlalchemy-redshift/pull/153>`_)
- Avoid manipulating search path in table metadata fetch by using system tables
  directly (`Issue #147 <https://github.com/sqlalchemy-redshift/sqlalchemy-redshift/pull/147>`_)

0.7.1 (2018-01-17)
------------------

- Fix incompatibility of reflection code with SQLAlchemy 1.2.0+
  (`Issue #138 <https://github.com/sqlalchemy-redshift/sqlalchemy-redshift/issues/138>`_)


0.7.0 (2017-10-03)
------------------

- Do not enumerate `search_path` with external schemas (`Issue #120
  <https://github.com/sqlalchemy-redshift/sqlalchemy-redshift/pull/120>`_)
- Return constraint name from get_pk_constraint and get_foreign_keys
- Use Enums for Format, Compression and Encoding.
  Deprecate string parameters for these parameter types
  (`Issue #133 <https://github.com/sqlalchemy-redshift/sqlalchemy-redshift/pull/133>`_)
- Update included certificate with the `transitional ACM cert bundle
  <https://docs.aws.amazon.com/redshift/latest/mgmt/connecting-transitioning-to-acm-certs.html>`_
  (`Issue #130 <https://github.com/sqlalchemy-redshift/sqlalchemy-redshift/pull/130>`_)


0.6.0 (2017-05-04)
------------------

- Support role-based access control in COPY and UNLOAD commands
  (`Issue #88 <https://github.com/sqlalchemy-redshift/sqlalchemy-redshift/pull/88>`_)
- Increase max_identifier_length to 127 characters
  (`Issue #96 <https://github.com/sqlalchemy-redshift/sqlalchemy-redshift/issues/96>`_)
- Fix a bug where table names containing a period caused an error on reflection
  (`Issue #97 <https://github.com/sqlalchemy-redshift/sqlalchemy-redshift/pull/97>`_)
- Performance improvement for reflection by caching table constraint info
  (`Issue #101 <https://github.com/sqlalchemy-redshift/sqlalchemy-redshift/issues/101>`_)
- Support BZIP2 compression in COPY command
  (`Issue #110 <https://github.com/sqlalchemy-redshift/sqlalchemy-redshift/issues/110>`_)
- Allow tests to tolerate new default column encodings in Redshift
  (`Issue #114 <https://github.com/sqlalchemy-redshift/sqlalchemy-redshift/pull/114>`_)
- Pull in set of reserved words from Redshift docs
  (`Issue #94 <https://github.com/sqlalchemy-redshift/sqlalchemy-redshift/issues/94>` _)


0.5.0 (2016-04-21)
------------------

- Support reflecting tables with foriegn keys to tables in non-public schemas
  (`Issue #70 <https://github.com/sqlalchemy-redshift/sqlalchemy-redshift/pull/70>`_)
- Fix a bug where DISTKEY and SORTKEY could not be used on column names containing
  spaces or commas. This is a breaking behavioral change for a command like
  `__table_args__ = {'redshift_sortkey': ('foo, bar')}`. Previously, this would sort
  on the columns named `foo` and `bar`. Now, it sorts on the column named `foo, bar`.
  (`Issue #74 <https://github.com/sqlalchemy-redshift/sqlalchemy-redshift/pull/74>`_)


0.4.0 (2015-11-17)
------------------

- Change the name of the package to `sqlalchemy_redshift` to match the naming
  convention for other dialects; the `redshift_sqlalchemy` package now emits
  a `DeprecationWarning` and references `sqlalchemy_redshift`.
  The `redshift_sqlalchemy` compatibility package will be removed
  in a future release.
  (`Issue #58 <https://github.com/sqlalchemy-redshift/sqlalchemy-redshift/pull/58>`_)
- Fix a bug where reflected tables could have incorrect column order for some
  `CREATE TABLE` statements, particularly for columns with an `IDENTITY`
  constraint.
  (`Issue #60 <https://github.com/sqlalchemy-redshift/sqlalchemy-redshift/pull/60>`_)
- Fix a bug where reflecting a table could raise a ``NoSuchTableError``
  in cases where its schema is not on the current ``search_path``
  (`Issue #64 <https://github.com/sqlalchemy-redshift/sqlalchemy-redshift/pull/64>`_)
- Add python 3.5 to the list of versions for integration tests.
  (`Issue #61 <https://github.com/sqlalchemy-redshift/sqlalchemy-redshift/pull/61>`_)


0.3.1 (2015-10-08)
------------------

- Fix breakages to CopyCommand introduced in 0.3.0:
  Thanks `solackerman <https://github.com/solackerman>`_.
  (`Issue #53 <https://github.com/sqlalchemy-redshift/sqlalchemy-redshift/pull/53>`_)

  - When `format` is omitted, no `FORMAT AS ...` is appended to the query. This
    makes the default the same as a normal redshift query.
  - fix STATUPDATE as a COPY parameter


0.3.0 (2015-09-29)
------------------

- Fix view support to be more in line with SQLAlchemy standards.
  `get_view_definition` output no longer includes a trailing semicolon and
  views no longer raise an exception when reflected as `Table` objects.
  (`Issue #46 <https://github.com/sqlalchemy-redshift/sqlalchemy-redshift/pull/46>`_)
- Rename RedShiftDDLCompiler to RedshiftDDLCompiler.
  (`Issue #43 <https://github.com/sqlalchemy-redshift/sqlalchemy-redshift/pull/43>`_)
- Update commands
  (`Issue #52 <https://github.com/sqlalchemy-redshift/sqlalchemy-redshift/pull/52>`_)

  - Expose optional TRUNCATECOLUMNS in CopyCommand.
  - Add all other COPY parameters to CopyCommand.
  - Move commands to their own module.
  - Support inserts into ordered columns in CopyCommand.


0.2.0 (2015-09-04)
------------------

- Use SYSDATE instead of NOW().
  Thanks `bouk <https://github.com/bouk>`_.
  (`Issue #15 <https://github.com/sqlalchemy-redshift/sqlalchemy-redshift/pull/15>`_)
- Default to SSL with hardcoded AWS Redshift CA.
  (`Issue #20 <https://github.com/sqlalchemy-redshift/sqlalchemy-redshift/pull/20>`_)
- Refactor of CopyCommand including support for specifying format and
  compression type. (`Issue #21 <https://github.com/sqlalchemy-redshift/sqlalchemy-redshift/pull/21>`_)
- Explicitly require SQLAlchemy >= 0.9.2 for 'dialect_options'.
  (`Issue #13 <https://github.com/sqlalchemy-redshift/sqlalchemy-redshift/pull/13>`_)
- Refactor of UnloadFromSelect including support for specifying all documented
  redshift options.
  (`Issue #27 <https://github.com/sqlalchemy-redshift/sqlalchemy-redshift/pull/27>`_)
- Fix unicode issue with SORTKEY on python 2.
  (`Issue #34 <https://github.com/sqlalchemy-redshift/sqlalchemy-redshift/pull/34>`_)
- Add support for Redshift ``DELETE`` statements that refer other tables in
  the ``WHERE`` clause.
  Thanks `haleemur <https://github.com/haleemur>`_.
  (`Issue #35 <https://github.com/sqlalchemy-redshift/sqlalchemy-redshift/issues/35>`_)
- Raise ``NoSuchTableError`` when trying to reflect a table that doesn't exist.
  (`Issue #38 <https://github.com/sqlalchemy-redshift/sqlalchemy-redshift/issues/38>`_)

0.1.2 (2015-08-11)
------------------

- Register postgresql.visit_rename_table for redshift's
  alembic RenameTable.
  Thanks `bouk <https://github.com/bouk>`_.
  (`Issue #7 <https://github.com/sqlalchemy-redshift/sqlalchemy-redshift/pull/7>`_)


0.1.1 (2015-05-20)
------------------

- Register RedshiftImpl as an alembic 3rd party dialect.


0.1.0 (2015-05-11)
------------------

- First version of sqlalchemy-redshift that can be installed from PyPI
