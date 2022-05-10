|discord|_
|test|_
|stars|_

About
=====

SQLite wrapper in the `Mys programming language`_.

Project: https://github.com/mys-lang/package-sqlite

An example
==========

A basic example that creates a table and then inserts and selects rows.

.. code-block:: mys

   from sqlite import Database

   func main():
       database = Database("my.db")
       database.execute("CREATE TABLE tab(foo, bar, baz)")
       database.execute("INSERT INTO tab VALUES(1, 'one', null)")
       database.execute("INSERT INTO tab VALUES(2,  2.2, 'two')")
       database.execute("INSERT INTO tab VALUES(3,  'three', null)")
       statement = database.prepare("SELECT * FROM tab WHERE foo >= ? ORDER BY foo")
       statement.bind_int(1, 2)

       while statement.fetch():
           print("Row:")
           print("  foo:", statement.column_value_string(0))
           print("  bar:", statement.column_value_string(1))
           print("  baz:", statement.column_value_string(2))

Build and run:

.. code-block:: myscon

   ❯ mys run
    ✔ Reading package configuration (0 seconds)
    ✔ Building (1.51 seconds)
   Row:
     foo: 2
     bar: 2.200000
     baz: "two"
   Row:
     foo: 3
     bar: "three"
     baz: null

API
===

.. mysfile:: src/lib.mys

.. |discord| image:: https://img.shields.io/discord/777073391320170507?label=Discord&logo=discord&logoColor=white
.. _discord: https://discord.gg/GFDN7JvWKS

.. |test| image:: https://github.com/mys-lang/package-sqlite/actions/workflows/pythonpackage.yml/badge.svg
.. _test: https://github.com/mys-lang/package-sqlite/actions/workflows/pythonpackage.yml

.. |stars| image:: https://img.shields.io/github/stars/mys-lang/package-sqlite?style=social
.. _stars: https://github.com/mys-lang/package-sqlite

.. _Mys programming language: https://mys-lang.org
