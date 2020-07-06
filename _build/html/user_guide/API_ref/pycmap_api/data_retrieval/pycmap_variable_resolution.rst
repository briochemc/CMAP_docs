.. _varRes:




Variable Resolution
===================


.. image:: https://colab.research.google.com/assets/colab-badge.svg
   :target: https://colab.research.google.com/github/simonscmap/pycmap/blob/master/docs/Resolution.ipynb

.. image:: https://mybinder.org/badge_logo.svg
   :target: https://mybinder.org/v2/gh/simonscmap/pycmap/master?filepath=docs%2FResolution.ipynb


.. method:: get_var_resolution(tableName, varName)


    Returns spatial and temporal resolutions of the given variable.

    |

    :Parameters:
        **tableName: string**
            The name of table associated with the dataset. A full list of table names can be found in the :ref:`Catalog`.
        **varName: string or list of string**
            Variable short name. A full list of variable short names can be found in the :ref:`Catalog`.


    :returns: Pandas dataframe.



|

**Example**

Returns the spatial and temporal resolution of the short name variable, AOD, in the MODIS Aerosol Optical Depth dataset. 

.. code-block:: python

  #!pip install pycmap -q     #uncomment to install pycmap, if necessary

  import pycmap

  api = pycmap.API(token='<YOUR_API_KEY>')
  api.get_var_resolution('tblModis_AOD_REP', 'AOD')

.. figure:: /_static/overview_icons/sql.png
 :scale: 10 %

**SQL Statement**

Here is how to achieve the same results using a direct SQL statement. Please refer to :ref:`query` for more information.

.. code-block:: sql

  EXEC uspVariableResolution 'tableName', 'varName'


**Example**

Returns the spatial and temporal resolution of the short name variable, AOD, in the MODIS Aerosol Optical Depth dataset. 

.. code-block:: sql

  EXEC uspVariableResolution 'tblModis_AOD_REP', 'AOD'
