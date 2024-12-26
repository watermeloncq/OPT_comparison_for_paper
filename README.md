# Paper Code: Comparative Analysis of Optimization Models
![stock_portfolio_value](https://github.com/user-attachments/assets/c4b40ada-a612-4795-82bc-9da20e8f0b1c)
![OPT_comparison](https://github.com/user-attachments/assets/cda3ede4-c6c0-4422-8b30-5a91fff526a7)


## 1. About

This is the source code for comparing different optimization models in paper: [arXiv:2412.18563](https://arxiv.org/abs/2412.18563), with training reward visualization module.

## 2. Required Python Packages

As RiskFolio-Lib depends on CVXPY package, and newer versions of CVXPY have discontinued support for older python versions, the **Python environment must be upgraded to version 3.9 or higher.**

Execute the following commands to install the required Python packages:

```
pip install pybind11
pip install cvxpy
pip install riskfolio-lib
pip install yfinance
pip install mosek
pip install seaborn
pip install pickleshare
pip install tensorboard
pip install tqdm
pip install pandas
```



## 3. Prerequisites for Code Execution

Clone or download the repository to your local machine.

Store data files in the following directories:

- **Stock data from WIND database:** "./Stocks/data/stocks-for-process/"

- **Tensorboard logs (modify path in source code):** "./extract_tblog/data/stokcs/"

- **Backtesting results (modify path in source code):** "./Stocks/data/DRL_trained_results/"



## 4. Code Execution Steps

Execution Procedure:

Step 1: Extract TensorBoard log data: "./extract_tblog/extract_tblog_to_csv.ipynb"

Step 2: Process stock data: "./Stocks/data/load&processing-chinese-stocks.ipynb"

Step 3: Execute all notebooks in "./OPT_comparison_code/Stocks" (e.g., Stocks_opt_for_ClassicMV_MinRisk.ipynb). Note: The backtesting period's start date must be specified in "year-month-day" format within the code line "idx = data.index.get_loc('202X-XX-XX')".

Step 4: Run the following notebooks sequentially:
- "./plot_DRL_trained_log.ipynb"
- "./plot_DRL_BackTest.ipynb"
- "./plot_OPT_comparison_Stocks.ipynb"
- "./plot_other_OPT_results_Stocks.ipynb"

  Note: Adjust data file paths as required

And vector graphics of experimental results are stored in "./img"
