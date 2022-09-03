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

To retrieve a list of random ingredients,
you can use the ``lumache.get_random_ingredients()`` function:

.. autofunction:: lumache.get_random_ingredients

The ``kind`` parameter should be either ``"meat"``, ``"fish"``,
or ``"veggies"``. Otherwise, :py:func:`lumache.get_random_ingredients`
will raise an exception.

.. autoexception:: lumache.InvalidKindError

For example:

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
