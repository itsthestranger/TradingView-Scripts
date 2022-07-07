This is a little script to display the daily open based on NY time as a horizontal line on the chart for each day.

```python
// This source code is subject to the terms of the Mozilla Public License 2.0 at https://mozilla.org/MPL/2.0/
// © crypto_stranger (@crypticprice)

//@version=5
indicator("NY Daily Open (@crypticprice)", overlay=true)
t1 = time(timeframe.period, "0000-0000:23456", "America/New_York")


t2 = time(timeframe.period, "0000-2345:1234567", "America/New_York")

if timeframe.period == '240'
    t2 := time(timeframe.period, "0000-2000:1234567", "America/New_York")
if timeframe.period == '60'
    t2 := time(timeframe.period, "0000-2300:1234567", "America/New_York")
if timeframe.period == '30'
    t2 := time(timeframe.period, "0000-2330:1234567", "America/New_York")
if timeframe.period == '15'
    t2 := time(timeframe.period, "0000-2345:1234567", "America/New_York")
if timeframe.period == '5'
    t2 := time(timeframe.period, "0000-2355:1234567", "America/New_York")
if timeframe.period == '3'
    t2 := time(timeframe.period, "0000-2353:1234567", "America/New_York")
if timeframe.period == '1'
    t2 := time(timeframe.period, "0000-2359:1234567", "America/New_York")

t3 = time(timeframe.period, "0000-0001:1234567", "America/New_York")


o = request.security(syminfo.tickerid,timeframe.period,open)


var op = open

if t3
    op := o

plot(t2 ? op : na, title="High", color=color.purple, linewidth=1, style=plot.style_linebr )



```
