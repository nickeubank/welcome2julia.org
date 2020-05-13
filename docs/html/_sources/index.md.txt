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

- **Statistical Modelling / Machine Learning**
    - [`Statistics`](https://docs.julialang.org/en/v1/stdlib/Statistics/): The Julia standard library comes with a wide range of statistics functionality, but to gain access to these functions you must first load `Statistics`.
    - [`FreqTables.jl`](https://github.com/nalimilan/FreqTables.jl): Create frequency tables / cross-tabulations. Tightly integrated with DataFrames.
    - [`HypothesisTests.jl`](https://juliastats.org/HypothesisTests.jl/stable/): A range of hypothesis testing tools.
    - [`GLM.jl`](https://juliastats.org/GLM.jl/stable/manual/): Tools for estimating linear and generalized linear models. Tightly integrated with DataFrames.
    - [`StatsModels.jl`](https://juliastats.org/StatsModels.jl/stable/): For converting heterogeneous DataFrames into homogenous matrices for use with linear algebra libraries or machine learning applications that don't directly support DataFrames. Will do things like convert categorical variables into indicators/one-hot-encodings, create interaction terms, etc.
    - [`MultivariateStats.jl`](https://multivariatestatsjl.readthedocs.io/en/stable/index.html): linear regression, ridge regression, PCA, component analyses tools. Not well integrated with DataFrames, but easily used using `StatsModels`.
    - [`Clustering.jl`](https://juliastats.org/Clustering.jl/stable/): All forms of clustering algorithms and tools for cluster evaluation.
    - [`Flux.jl`](https://fluxml.ai/Flux.jl/stable/): A pure-Julia package for building your own machine learning models (a little more low-level than `Scikit-Learn`). Not well integrated with DataFrames, but easily used using `StatsModels`.
    - [`ScikitLearn.jl`](https://scikitlearnjl.readthedocs.io/en/latest/): A Julia wrapper around the full Python `scikit-learn` machine learning library. Not well integrated with DataFrames, but easily used using `StatsModels`.
- **Plotting**
    - [`Plots.jl`](http://docs.juliaplots.org/latest/): Powerful, modern plotting library with a syntax akin to that of `matplotlib` (in Python) or `plot` (in R). [`StatsPlots`](http://docs.juliaplots.org/latest/tutorial/#Using-Plot-Recipes-1) provides `Plots.jl` with recipes for many standard statistical plots.
    - [`Gadfly.jl`](http://gadflyjl.org/stable/): High-level plotting library with a "grammar of graphics" syntax akin to that of `ggplot` (in R).
    - [`VegaLite.jl`](https://www.queryverse.org/VegaLite.jl/stable/): High-level plotting library that uses a different "grammar of graphics" syntax and has an emphasis on interactive graphics.
- **Data Wrangling**:
    - [`DataFramesMeta.jl`](https://github.com/JuliaData/DataFramesMeta.jl): A range of convenience functions for DataFrames that augment `select` and `transform` to provide a user experience similar to that provided by `dplyr` in R.
    - [`Query.jl`](https://github.com/queryverse/Query.jl): `Query` provides a single framework for data wrangling that works with a range of libraries, including DataFrames, other tabular data libraries (more on those below), and even non-tabular data. Provides many convenience functions analogous to those in `dplyr` or `linq`.
- **And More!**
    - [`LightGraphs.jl`](https://github.com/JuliaGraphs/LightGraphs.jl): A pure-Julia, high performance network analysis library. Edgelists in DataFrames can be easily converted into Graphs using the [`GraphDataFrameBridge.jl`](https://github.com/JuliaGraphs/GraphDataFrameBridge.jl) package.
- **IO**:
    - DataFrames work well with a range of formats, including (but not limited to) CSVs (using [`CSV.jl`](https://github.com/JuliaData/CSV.jl)), Stata, SPSS, and SAS files (using [`StatFiles.jl`](https://github.com/queryverse/StatFiles.jl)), JSON (using [`JSONTables.jl`](https://github.com/JuliaData/JSONTables.jl)), and reading (though not writing) parquet files (using [`ParquetFiles.jl`](https://github.com/queryverse/ParquetFiles.jl)).

While not all of these libraries are tightly integrated with DataFrames, because
DataFrames are essentially collections of aligned Julia vectors, so it is easy
to (a) pull out a vector for use with a non-DataFrames-integrated library, or (b)
use `StatsModels` to convert your table into a homogenously-typed matrix.

### Other Julia Tabular Libraries

DataFrames is a great general purpose tool for data manipulation and
wrangling, but it's not ideal for all applications. For users with more
specialized needs, consider using:

- [`TypedTables.jl`](https://juliadata.github.io/TypedTables.jl/stable/): Type-stable heterogeneous tables. Useful for improved performance when the structure of your table is relatively stable.
- [`JuliaDB.jl`](https://juliadata.github.io/JuliaDB.jl/stable/): For users working with data that is too large to fit in memory, we suggest JuliaDB, which offers better performance for large datasets, and can handle out-of-core data manipulations (Python users can think of JuliaDB as the Julia version of `dask`).

Note that most tabular data libraries in the Julia ecosystem (including DataFrames)
support a common interface. As a result, some libraries are
capable or working with a range of tabular data structures, making it easy to
move between tabular libraries as your needs change. A user of
[`Query.jl`](https://github.com/queryverse/Query.jl), for example, can use the
same code to manipulate data in a DataFrame, a TypedTable, or a JuliaDB table.



Questions or comments?
-----------------------

Please let me know! All source files (and underlying jupyter notebooks) for this site can be `found on github <https://github.com/nickeubank/practicaldatascience/>`_, and you can raise issues there by creating a new issue, or by emailing me at `nick@nickeubank.com <mailto:nick@nickeubank.com>`_.

.. toctree::
   :maxdepth: 2
   :hidden:

   CLASS SCHEDULE <class_schedule>

.. toctree::
   :maxdepth: 2
   :hidden:
   :caption: PYTHON & PANDAS

   Setting Up Python <setup_environment>
   Managing Packages <managing_python_packages>
   Python / R Differences <python_v_r>
   Python: Vars v Objects <vars_v_objects>
   Numbers in Computers <ints_and_floats>
   Pandas 1: Series <pandas_series>
   Pandas 2: DataFrames <pandas_dataframes>
   Plotting, Basics <plotting_part1>
   Plotting, Advanced <plotting_part2>
   Pandas 3: Views <views_and_copies_in_pandas>

.. toctree::
   :maxdepth: 2
   :hidden:
   :caption: OTHER TOOLS

   Command Line, Basics <command_line_part1>
   Command Line, Advanced  <command_line_part2>
   Jupyter <jupyter>
   Git and Github <git_and_github>

.. toctree::
   :maxdepth: 2
   :hidden:
   :caption: SKILLS

   Getting Help Online <getting_help>
   Defensive Programming <defensive_programming>
   Workflow Management <workflow>
   What is Big Data? <what_is_big_data>
   Working with Big Data <big_data_strategies>
   Understanding Performance <performance_understanding>
   Solving Performance Probs <performance_solutions>
   Parallel Computing <parallelism>
   Distributed Computing <distributed_computing>

.. toctree::
   :maxdepth: 2
   :hidden:
   :caption: OTHER

   Not a MIDS Student? <not_a_mids_student>
   Cheat Sheets <cheatsheets>
