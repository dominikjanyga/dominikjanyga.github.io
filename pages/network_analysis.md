# Network analysis of the polish stock companies

**Project description:** Due to its growing popularity and application in many fields, network analysis is a key tool for understanding complex relationships and structures.


## Contents
1. [Data Collection](#1-data-collection-of-polish-stock-companies-using-pandas-and-yfinance-libraries)
2. [Data Cleaning](#2-data-cleaning)
3. [Network Analysis and Testing](#3-network-analysis-and-testing)
4. [Conclusion](#4-conclusion)

## 1. Data collection of polish stock companies using pandas and yfinance libraries.

[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/dominikjanyga/network-analysis/blob/main/1_network_analysis_data_collection.ipynb)

### Loading libraries.

In the first step, I imported libraries which will be helpful in data scraping and processing. I used `pandas` to read HTML tables from the [Stooq website](https://stooq.pl/), which lists all the components of the WIG index. Additionally, I used the `yfinance` library to obtain financial information on companies listed on the Warsaw Stock Exchange (WSE).

```python
import pandas as pd
import yfinance as yf
```

I mount Google Drive in a Google Colab environment. All the future data will be saved in my google drive, making it easy to access and load datasets. 

```python
from google.colab import drive
drive.mount('/content/drive')
```

### Collecting Ticker Symbols from Stooq

This step involves scraping ticker symbols for companies listed on the Warsaw Stock Exchange. By looping through Stooq’s HTML tables, I extract each ticker symbol, which represents a stock listed in the WSE, and save it to a list for later use.

```python
ticker_list = []

for page in range(1, 9):
    page_url = f"https://stooq.pl/q/i/?s=wig&l={page}"
    wig_table = pd.read_html(page_url)[1]
    wig_selected_rows = wig_table.iloc[5:-1, 0].tolist()
    ticker_list.extend(wig_selected_rows)

print(ticker_list)
len(ticker_list)
```
## 2. Data Cleaning

[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/dominikjanyga/network-analysis/blob/main/2_network_analysis_data_cleaning.ipynb)

### 3. Network Analysis and Testing

[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/dominikjanyga/network-analysis/blob/main/3_network_analysis_testing.ipynb)


### 4. Conclusion

Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque laudantium, totam rem aperiam, eaque ipsa quae ab illo inventore veritatis et quasi architecto beatae vitae dicta sunt explicabo. 

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).
