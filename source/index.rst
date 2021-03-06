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
- `LinearAlgebra <https://docs.julialang.org/en/v1/stdlib/LinearAlgebra/>`_: Like `Statistics`, many linear algebra functionality (factorizations, inversions, etc.) live in a library you have to load to use. Similarly, `SparseArrays <https://docs.julialang.org/en/v1/stdlib/SparseArrays/>`_ are also in the standard library but must be loaded to be used. 
- `FreqTables.jl <https://github.com/nalimilan/FreqTables.jl>`_: Create frequency tables / cross-tabulations. Tightly integrated with DataFrames.
- `HypothesisTests.jl <https://juliastats.org/HypothesisTests.jl/stable/>`_: A range of hypothesis testing tools.
- `GLM.jl <https://juliastats.org/GLM.jl/stable/manual/>`_: Tools for estimating linear and generalized linear models. Tightly integrated with DataFrames.
- `StatsModels.jl <https://juliastats.org/StatsModels.jl/stable/>`_: For converting heterogeneous DataFrames into homogenous matrices for use with linear algebra libraries or machine learning applications that don't directly support DataFrames. Will do things like convert categorical variables into indicators/one-hot-encodings, create interaction terms, etc.
- `MultivariateStats.jl <https://multivariatestatsjl.readthedocs.io/en/stable/index.html>`_: linear regression, ridge regression, PCA, component analyses tools. Not well integrated with DataFrames, but easily used using `StatsModels`.
- `FixedEffectModels.jl <https://github.com/FixedEffects/FixedEffectModels.jl>`_: For panel regressions with (efficient) fixed effects and clustered standard errors.

Machine Learning
----------------

Perhaps more than any other part of the Julia ecosystem, machine learning tools are scattered across a bewildering array of libraries. There's a library for clustering (`Clustering.jl <https://juliastats.org/Clustering.jl/stable/>`_), a library for decision trees (`DecisionTree.jl <https://github.com/bensadeghi/DecisionTree.jl>`_), a library for XGBoost (`XGBoost.jl <https://github.com/dmlc/XGBoost.jl>`_), and, if you want to really build your own models, the extremely powerful `Flux.jl <https://fluxml.ai/Flux.jl/stable/>`_.

Thankfully, though, if you're more of an applied user, there is a single package the pulls from all these different libraries and provides a single, `scikit-learn` inspired API: `MLJ.jl <https://github.com/alan-turing-institute/MLJ.jl>`_. MLJ provides a common interface for a wide range of machine learning algorithms. You can find a list of all supported models (both supervised and unsupervised), as well as an evaluation of the maturity of each library, `here <https://github.com/alan-turing-institute/MLJ.jl#available-models>`_, and `some great tutorials here <https://alan-turing-institute.github.io/MLJTutorials/>`_.  For *most* applied users, MLJ is probably a good place to start, especially if you like / are familiar with `scikit-learn`.

There are two exceptions to the "just use MLJ.jl" suggestion, however.

First, MLJ doesn't offer much for deep learning. If you want to do deep learning, I would suggest `KNet.jl <https://denizyuret.github.io/Knet.jl/stable/tutorial/#Introduction-to-Knet-1>`_ if you want a pure Julia package. It has a clean API, supports both NVIDIA and AMD GPUs, is fast and is likely the best choice for "standard" deep learning. And of course Julia has a TensorFlow wrapper (`TensorFlow.jl <https://github.com/malmaud/TensorFlow.jl>`_), which in all honesty is a lot easier to use then the Python API. (No analogue for PyTorch in Julia yet, though.)

And second, if you want to really build your own model from the ground up, then you probably want to use the pure-Julia `Flux.jl <https://github.com/FluxML/Flux.jl>`_, which has some great building blocks, but fewer pre-built models.

All this talk of fragmentation making you nervous that you won't find the tool you want? Worry not! If you ever get stuck with Julia machine learning, you can always fall back on `ScikitLearn.jl <https://scikitlearnjl.readthedocs.io/en/latest/>`_, a simple wrapper for the full `scikit-learn` stack. :)


Plotting
--------

- `Plots.jl <http://docs.juliaplots.org/latest/>`_: Powerful, modern plotting library with a syntax akin to that of `matplotlib` (in Python) or `plot` (in R). `StatsPlots <http://docs.juliaplots.org/latest/tutorial/#Using-Plot-Recipes-1`_ provides `Plots.jl` with recipes for many standard statistical plots.
- `Gadfly.jl <http://gadflyjl.org/stable/>`_: High-level plotting library with a "grammar of graphics" syntax akin to that of `ggplot` (in R).
- `VegaLite.jl <https://www.queryverse.org/VegaLite.jl/stable/>`_: High-level plotting library that uses a different "grammar of graphics" syntax and has an emphasis on interactive graphics.


And More!
---------

- `LightGraphs.jl <https://github.com/JuliaGraphs/LightGraphs.jl>`_: A pure-Julia, high performance network analysis library. Edgelists in DataFrames can be easily converted into Graphs using the `GraphDataFrameBridge.jl <https://github.com/JuliaGraphs/GraphDataFrameBridge.jl>`_ package.
- `TextAnalysis.jl <https://github.com/JuliaText/TextAnalysis.jl>`_: A pure-Julia NLP package.

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
