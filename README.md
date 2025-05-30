# FireDucks

FireDucks is a high-performance compiler-accelerated dataframe library for python. It is being developed with speed and pandas compatibility in mind.

## License

[FireDucks](https://pypi.org/project/fireducks/) is released on pypi.org under the 3-Clause BSD License (the Modified BSD License).

## Let's experience the power of FireDucks!&#x1f986;&#x1f986;&#x1f986;

Anyone can experience the ease of use and high-speed performance of FireDucks for free.

If you have a Google account, you can try it out right now on Google colab.
Please select 'v2-8 TPU' from the runtime settings, because it has high number of cpu cores and runtime memory.

| notebook contents | sample notebook links(open in Google colab) |
|-----------|---------|
| **A short presentation of some frequently used data analysis using pandas.** | [pandas_nyc_demo.ipynb](https://colab.research.google.com/github/fireducks-dev/fireducks/blob/main/notebooks/nyc_demo/pandas_nyc_demo.ipynb)               |
| **A short presentation of some frequently used data analysis using FireDucks.** | [fireducks_pandas_nyc_demo.ipynb](https://colab.research.google.com/github/fireducks-dev/fireducks/blob/main/notebooks/nyc_demo/fireducks_pandas_nyc_demo.ipynb)     |
| **Demonstrating true strength of FireDucks in Query planning and optimization.** | [tpch-query3-pandas-fireducks-cudf.ipynb](https://colab.research.google.com/github/fireducks-dev/fireducks/blob/main/notebooks/tpch-query3-pandas-fireducks-cudf.ipynb)               |
| **NYC Taxi trips (Jan-2015) analysis using FireDucks, pandas and polars.**      | [FireDucks_vs_Pandas_vs_Polars.ipynb](https://colab.research.google.com/github/fireducks-dev/fireducks/blob/main/notebooks/FireDucks_vs_Pandas_vs_Polars.ipynb)               |

## Install 

FireDucks is currently available for Linux (manylinux) on the x86\_64 architecture (we will support it for other platforms based on user requests) 
and it can be simply installed using `pip` as follows:

```shell
pip install fireducks
```

Please make sure you are using **Python >3.8, <=3.13**, otherwise you may encounter
error saying: *"No matching distribution found for fireducks"*.

&#x26a0; Since FireDucks 1.1.0, we have upgraded dependent pyarrow to 18.0.0. Therefore, python 3.8 is no longer supported.

## Usage

FireDucks provides two types of usage: [Import Hook](#import-hook) and
[Explicit Import](#explicit-import).

### Import Hook 

FireDucks provides an import hook utility. This utility runs the given Python
script by automatically replacing `import pandas` statement with FireDucks. So
this utility enables you to use FireDucks for your existing program as it is.
The import hook can be activated by Python interpreter's `-m` option as follows.

```shell
python3 -m fireducks.pandas your_script.py
```

For IPython/Jupyter Notebook, a magic command is available as follows.

```python
%load_ext fireducks.pandas
import pandas as pd
```

This is very useful when your program includes many Python scripts which import
pandas internally. You don't need to replace individual `import` statements from
those scripts manually.

If you use any external libraries (like matplotlib etc.) which may internally
use pandas DataFrame, please make sure to enable the hook to avoid any
unintended executional issues.

&#x1f4e2; _The import hook feature has changed its name to `fireducks.pandas` from
FireDucks [0.11.0](https://fireducks-dev.github.io/docs/release-note/#v0.11.0). 
An old module name `fireducks.imhook` is also available as an alias._

### Explicit Import 

FireDucks has pandas-like module `fireducks.pandas` which can be imported instead
of pandas. If you want to use FireDucks for an existing pandas program, replace
the import statement as follows.

```python
# import pandas as pd
import fireducks.pandas as pd
```

&#x1f4bb; **Web site: <https://fireducks-dev.github.io>**

This repository is used for communication such as issue report and Q&A. [Please open new issue](https://github.com/fireducks-dev/fireducks/issues/new/choose).

&#x2709; Contact: <mailto:contact@fireducks.jp.nec.com>

&#x1f91d;Slack: <https://join.slack.com/t/fireducks/shared_invite/zt-34qpdgr6q-_iWdIoZW4l_hGhljKS0pyg>
