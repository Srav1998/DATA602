# Forex Bid Price Prediction
Link to Dataset: [https://www.openml.org/d/41816](https://www.openml.org/d/41816)
### Objective: I want to predict the number of times the bid prices changes within a time interval and classify whether the bid price rises in the next time interval or not.
#### For now, I didn't make any changes to the dataframe.But, I would like to extract Monthly changes by splitting Timestamp column.
### Dataset Description
#### Features
#### 1. Timestamp: The time of the current data point (Europe/Amsterdam).
#### 2. Bid_Open: The bid price at the start of this time interval
#### 3. Bid_High: The highest bid price during this time interval
#### 4. Bid_Low: The lowest bid price during this time interval
#### 5. Bid_Close: The bid price at the end of this time interval
#### 6. Bid_Volume: The number of times the Bid Price changed within this time interval
#### 7. Ask_Open: The ask price at the start of this time interval
#### 8. Ask_High: The highest ask price during this time interval
#### 9. Ask_Low: The lowest ask price during this time interval
#### 10. Ask_Close: The ask price at the end of this time interval
#### 11. Ask_Volume: The number of times the Ask Price changed within this time interval
#### 12. Class: Whether the average price will go up during the next interval

### * This is the historical price data of the FOREX USD/DKK from Dukascopy.
### * One instance (row) is one candlestick of one hour.
### * The whole dataset has the data range from 1-1-2018 to 13-12-2018 and does not include the weekends, since the FOREX is not traded in the weekend.
### * The timezone of the feature Timestamp is Europe/Amsterdam.
### * The class attribute is the direction of the mean of the High_Bid and the High_Ask of the following hour,relative to the High_Bid and High_Ask mean of the current minute.
### * This means the class attribute is True when the mean High price is going up the following hour,and the class attribute is False when the mean High price is going down (or stays the same) the following hour.
