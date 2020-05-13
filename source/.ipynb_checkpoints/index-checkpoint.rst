Welcome To Julia!
=================

Julia is a new, modern programming language designed for data science and
scientific programming. It has a syntax like Python, but speeds like C, and
incorporates decades of insights about programming language design.

While I believe the language is wonderful and surprisingly intuitive, the Julia
data ecosystem can be a difficult space for new users to navigate,
in part because the Julia ecosystem tends to distribute functionality across
different libraries more than some other languages.

With that in mind, I've created this site to offer new Julia users a guide to
the Julia ecosystem. This site is not a tutorial, but rather a guide to help
people find the right packages to meet their needs.

Tabular Data Libraries
----------------------

Most people doing data science work have to work with messy tabular data of mixed
types, and for that there are two main choices: `DataFrames.jl <http://juliadata.github.io/DataFrames.jl/stable>`_ and
`JuliaDB.jl <https://juliadb.org/>`_.

DataFrames provides a lightweight set of tools for working with tabular data
in Julia. Its design and functionality are similar to those of `pandas`
(in Python) and `data.frames` (in R), making it a great general purpose
data science tool, especially for those coming to Julia from R or Python. I would
recommend this as a starting point to the vast majority of users.

But if you're working with data that is too large to fit in memory, JuliaDB offers
better performance for large datasets, and can handle out-of-core data manipulations
(Python users can think of JuliaDB as the Julia version of `dask`).

You can find much more on [tabular data libraries here](tabular_data_libraries).

Statistical Modelling
---------------------

- `Statistics <https://docs.julialang.org/en/v1/stdlib/Statistics/>`_: The Julia standard library comes with a wide range of statistics functionality, but to gain access to these functions you must first load `Statistics`.
- `FreqTables.jl <https://github.com/nalimilan/FreqTables.jl>`_: Create frequency tables / cross-tabulations. Tightly integrated with DataFrames.
- `HypothesisTests.jl <https://juliastats.org/HypothesisTests.jl/stable/>`_: A range of hypothesis testing tools.
- `GLM.jl <https://juliastats.org/GLM.jl/stable/manual/>`_: Tools for estimating linear and generalized linear models. Tightly integrated with DataFrames.
- `StatsModels.jl <https://juliastats.org/StatsModels.jl/stable/>`_: For converting heterogeneous DataFrames into homogenous matrices for use with linear algebra libraries or machine learning applications that don't directly support DataFrames. Will do things like convert categorical variables into indicators/one-hot-encodings, create interaction terms, etc.
- `MultivariateStats.jl <https://multivariatestatsjl.readthedocs.io/en/stable/index.html>`_: linear regression, ridge regression, PCA, component analyses tools. Not well integrated with DataFrames, but easily used using `StatsModels`.

Unsupervised Machine Learning
-----------------------------

- `Clustering.jl <https://juliastats.org/Clustering.jl/stable/>`_: All forms of clustering algorithms and tools for cluster evaluation.

Supervised Machine Learning
---------------------------

- `Flux.jl <https://fluxml.ai/Flux.jl/stable/>`_: A pure-Julia package for building your own (deep-learning) machine learning models (a little more low-level than `Scikit-Learn`). Not well integrated with DataFrames, but easily used using `StatsModels`.
- `ScikitLearn.jl <https://scikitlearnjl.readthedocs.io/en/latest/>`_: A Julia wrapper around the full Python `scikit-learn` machine learning library, making any tool you can't immediately find in a pure-Julia library immediately accessible.

Plotting
--------

- `Plots.jl <http://docs.juliaplots.org/latest/>`_: Powerful, modern plotting library with a syntax akin to that of `matplotlib` (in Python) or `plot` (in R). `StatsPlots <http://docs.juliaplots.org/latest/tutorial/#Using-Plot-Recipes-1) provides `Plots.jl` with recipes for many standard statistical plots.
- `Gadfly.jl <http://gadflyjl.org/stable/>`_: High-level plotting library with a "grammar of graphics" syntax akin to that of `ggplot` (in R).
- `VegaLite.jl <https://www.queryverse.org/VegaLite.jl/stable/>`_: High-level plotting library that uses a different "grammar of graphics" syntax and has an emphasis on interactive graphics.


And More!
---------

- `LightGraphs.jl <https://github.com/JuliaGraphs/LightGraphs.jl>`_: A pure-Julia, high performance network analysis library. Edgelists in DataFrames can be easily converted into Graphs using the `GraphDataFrameBridge.jl <https://github.com/JuliaGraphs/GraphDataFrameBridge.jl>`_ package.

Questions or comments?
----------------------

Please let me know! All source files (and underlying jupyter notebooks) for this site can be `found on github <https://github.com/nickeubank/welcome2julia.org/>`_, and you can raise issues there by creating a new issue, or by emailing me at `nick@nickeubank.com <mailto:nick@nickeubank.com>`_.

.. toctree::
   :maxdepth: 2
   :hidden:

   Note to Pandas Users <note_to_pandas_users>
   Note to R Users <note_to_r_users>
   Tabular Data Tools <tabular_data_tools>
   Statistics <statistics>
   Unsupervised ML <unsupervised_machine_learning>
   Supervised ML <supervised_machine_learning>
   Network Analysis <network_analysis>