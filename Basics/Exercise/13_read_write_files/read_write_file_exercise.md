## Exercise: Python Read Write File
1. [poem.txt](https://github.com/codebasics/py/blob/master/Basics/Exercise/13_read_write_files/poem.txt) contains famous poem "Road not taken" by poet Robert Frost. You have to read this file in your python program and find out words with maximum occurance.


[Solution](https://github.com/codebasics/py/blob/master/Basics/Exercise/13_read_write_files/exercise_2_stocks.py)

2. [stocks.csv](https://github.com/codebasics/py/blob/master/Basics/Exercise/13_read_write_files/stocks.csv) contains stock price, earnings per share and book value. You are writing a stock market application that will process this file and create a new file
with financial metrics such as pe ratio and price to book ratio. These are calculated as,
```
pe ratio = price / earnings per share
price to book ratio = price / book value
```


Your input format (stocks.csv) is,

|Company Name|Price|Earnings Per Share|Book Value|
|-------|----------|-------|----------|
|Reliance|1467|66|653|
|Tata Steel|391|89|572|

Output.csv should look like this,

|Company Name|PE Ratio|PB Ratio|
|-------|----------|-------|
|Reliance|22.23|2.25|
|Tata Steel|4.39|0.68|


import csv
real_file = open("c:\\data\\stocks.csv", "r")
edit_file = open("edit1_sample.csv", "w")
dict_read_file = csv.DictReader(real_file)
edit_file.write(f"Company Name, PE Ratio, PB Ratio \n")
# next(real_file)
for line in dict_read_file:
   pe_column = round((int(line["Price"])/int(line["Earnings Per Share"])), 2)
   price_to_book_column = round((int(line["Price"]) / int(line[" Book Value"])), 2)
   edit_file.write(f"{line["Company Name"]}, {pe_column}, {price_to_book_column} \n")
   print(price_to_book_column,pe_column)
real_file.close()
edit_file.close()

[Solution](https://github.com/codebasics/py/blob/master/Basics/Exercise/13_read_write_files/exercise_2_stocks.py)
