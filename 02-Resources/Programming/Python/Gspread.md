---
tags:
  - python
  - pandas
---

# Gspread
- [Gspread Documentation](https://docs.gspread.org/en/latest/oauth2.html)
- Config path <code>~/.config/gspread_pandas/google_secret.json</code>
- [Gspread_pandas Documentation](https://gspread-pandas.readthedocs.io/en/latest/index.html)
- [Authentication Help](https://stackoverflow.com/questions/38949318/google-sheets-api-returns-the-caller-does-not-have-permission-when-using-serve)

## Basic Template
```Python
from gspread_pandas import Spread, Client
import gspread

spread = Spread('Example SpreadSheet')

spread.df_to_sheet(df, index=false, sheet='New Test Sheet', start='A2', replace='True')
```
#### Additional Installs
[gspread-pandas](https://github.com/aiguofer/gspread-pandas)
```Shell
pip install gspread_pandas
```

```Python
gc = gspread.service_account()
sh.gc.open("Application-Test")

worksheet_title = "2023"
try:
	worksheet - sh.worksheet(worksheet_title)
except: gspread.WorksheetNotFound:
	worksheet = sh.add_worksheet(title=worksheet_title, rows=1000, cols=1000)

df_read = get_as_dataframe(worksheet)
```