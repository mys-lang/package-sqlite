Welcome to SQLite package documentation!
========================================

SQLite in the `Mys programming language`_.

Example
-------

A basic example that creates a table and then inserts and selects rows.

.. code-block:: python

   from sqlite import Database

   def main():
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

Project
-------

- `GitHub`_: Official project repository.

.. toctree::
   :maxdepth: 1
   :titlesonly:
   :hidden:

   modules

.. _Mys programming language: https://mys.readthedocs.io/en/latest/

.. _GitHub: https://github.com/mys-lang/package-sqlite
