.. _varCover:




Variable Coverage
=================


.. image:: https://colab.research.google.com/assets/colab-badge.svg
   :target: https://colab.research.google.com/github/simonscmap/pycmap/blob/master/docs/Coverage.ipynb

.. image:: https://mybinder.org/badge_logo.svg
   :target: https://mybinder.org/v2/gh/simonscmap/pycmap/master?filepath=docs%2FCoverage.ipynb


.. method:: get_var_coverage(tableName, varName)


    Returns spatial and temporal coverage of the given variable.


    |

    :Parameters:
        **tableName: string**
            The name of table associated with the dataset. A full list of table names can be found in the :ref:`Catalog`.
        **variable: string or list of string**
            Variable short name. A full list of variable short names can be found in the :ref:`Catalog`.


    :returns: Pandas dataframe.




|

**Example**

Returns the spatial and temporal coverage of the short name variable, chl, in the Chlorophyll Reprocessed dataset. 

.. code-block:: python

  #!pip install pycmap -q     #uncomment to install pycmap, if necessary

  import pycmap

  api = pycmap.API(token='<YOUR_API_KEY>')
  api.get_var_coverage('tblCHL_REP', 'chl')


.. figure:: /_static/overview_icons/sql.png
 :scale: 10 %

**SQL Statement**

Here is how to achieve the same results using a direct SQL statement. Please refer to :ref:`query` for more information.

.. code-block:: sql

  EXEC uspVariableCoverage 'tableName', 'varName'

**Example**

Returns the spatial and temporal coverage of the short name variable, chl, in the Chlorophyll Reprocessed dataset. 

.. code-block:: sql

  EXEC uspVariableCoverage 'tblCHL_REP', 'chl'
