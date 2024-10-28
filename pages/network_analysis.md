# Network analysis of the polish stock companies

**Project description:** Due to its growing popularity and application in many fields, network analysis is a key tool for understanding complex relationships and structures.


## Contents
1. [Data Collection](#1-data-collection-of-polish-stock-companies-using-pandas-and-yfinance-libraries)
2. [Data Cleaning](#2-data-cleaning)
3. [Network Analysis and Testing](#3-network-analysis-and-testing)
4. [Conclusion](#4-conclusion)

## 1. Data collection of polish stock companies using pandas and yfinance libraries.

```python
import pandas as pd
import yfinance as yf
```
Here, I am using a function that reads the HTML table from the stooq webpage. The goal is to obtain all ticker symbols for the companies that are listed on the Warsaw Stock Exchange and save them all to the empty list.
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

```javascript
if (isAwesome){
  return true
}
```

### 3. Network Analysis and Testing



### 4. Conclusion

Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque laudantium, totam rem aperiam, eaque ipsa quae ab illo inventore veritatis et quasi architecto beatae vitae dicta sunt explicabo. 

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).
