Usage
=====

.. _installation:

Installation
------------

To use pypbp, first install it using pip:

.. code-block:: console

   (.venv) $ pip install pypbp

A minimal reproducible example
----------------

>>> import pypbp as pbp
>>> results, xstar, clustered_patterns, parameters = pbp.pbp_fit(time_series = pbp.time_series, 
            train_percentage = 0.5, 
            xstar = 200, 
            maxfun = 200)
>>> parameters
{'m': 7,
 'd_cluster': 0.19880907592368005,
 'alpha': 0.7478052377700806,
 'auroc': -0.95,
 'd_base': 0.30000000000000004}
 >>> pbp.pbp_plot(time_series = pbp.time_series, clustered_patterns = clustered_patterns, 
             parameters = parameters, 
             xnew = [10, 60, 20, 10, 20, 80, 90])
