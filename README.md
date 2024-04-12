![Coincap (Price USD)](https://img.shields.io/coincap/price-usd/bitcoin?logo=bitcoin)
# ![Coincap (Change Percent 24Hr)](https://img.shields.io/coincap/change-percent-24hr/bitcoin?logo=bitcoin)
```python
study(title="RSI Chart Bars",overlay = true, shorttitle="RSI Bars")
src = close, len = input(14, minval=1, title="Length")
up = rma(max(change(src), 0), len)
down = rma(-min(change(src), 0), len)
rsi = down == 0 ? 100 : up == 0 ? 0 : 100 - (100 / (1 + up / down))
src1 = close, len1 = input(70, minval=1, title="UpLevel")
src2 = close, len2 = input(30, minval=1, title="DownLevel")
isup() => rsi > len1
isdown() => rsi < len2
barcolor(isup() ? green : isdown() ? red : na )
```
