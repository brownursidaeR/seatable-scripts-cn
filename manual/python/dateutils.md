# 时间操作函数DateUtils

我们在 python 的 datetime 模块的基础上提供一系列函数可以对时间字符串进行查询以及操作。

#### 函数引入

```python
from seatable_api import dateutils
```

#### date

返回 ISO 格式化的日期

```python
dateutils.date(2020, 5, 16) # 2020-05-16
```

#### dateadd

对时间进行加法运算，通过传递不同的单位参数可以加年，月，周，日，小时，分钟，秒，默认使用‘日’作为单位

```python
time_str = "2020-6-15"
time_str_s = "2020-6-15 15:23:21"

dateutils.dateadd(time_str, -2, 'years') # 2018-06-15T00:00:00
dateutils.dateadd(time_str, 3, 'months') # 2020-09-15T00:00:00
dateutils.dateadd(time_str_s, 44, 'minutes') # 2020-06-15T16:07:21
dateutils.dateadd(time_str_s, 1000, 'days') # 2023-03-12T15:23:21
dateutils.dateadd(time_str_s, 3, 'weeks') # 2020-07-06T15:23:21
dateutils.dateadd(time_str_s, -3, 'hours') # 2020-06-15T12:23:21
dateutils.dateadd(time_str_s, 3, 'seconds') # 2020-06-15T15:23:24
```

#### datediff

计算两个日期之间相隔的秒数，天数， 月数，年数， 参数可以为 S, Y, M, D, YM, MD

其中

* YM, 开始时间与结束时间之间月份之差, 忽略日期中的天和年份
* MD, 开始时间与结束时间之间天数之差, 忽略日期中的月份和年份
* YD,  开始时间与结束时间的日期部分之差, 忽略日期中的年份。

```python
time_start = "2019-6-1"
time_end = "2020-5-15"
dateutils.datediff(start=time_start, end=time_end, unit='S') # seconds 30153600
dateutils.datediff(start=time_start, end=time_end, unit='Y') # years 1
dateutils.datediff(start=time_start, end=time_end, unit='D') # days 349
dateutils.datediff(start=time_start, end=time_end, unit='H') # hours 8377
dateutils.datediff(start=time_start, end=time_end, unit='M') # months 12
dateutils.datediff(start=time_start, end=time_end, unit='YM') #  -1
dateutils.datediff(start=time_start, end=time_end, unit='MD') #  14
dateutils.datediff("2019-2-28","2020-2-1", unit='YD') # -27
```

#### emonth

返回某个日期的前一个月或后一个月的最后一天， 参数 direction 可以为1或-1

```python
dateutils.emonth('2020-3-25', direction=-1) # 2021-02-28
dateutils.emonth('2021-3-25', direction=1) # 2021-04-30
```

#### year

返回某个日期的年

```python
dateutils.year("2019-1-1") # 2019
```

#### month

返回某个日期的月

```python
dateutils.month("2019-5-4") # 5
```

#### months

返回两个日期相差的月数

```python
dateutils.month("2019-5-1","2020-5-4") # 12
```

#### day

返某个日期的天

```python
dateutils.day('2020-6-15 15:23:21') # 15
```

#### days

返回两个日期相差的天数

```python
dateutils.days('2019-6-1', '2020-5-15') # 349
```

#### hour

返回时间的小时数

```pyhton
dateutils.hour("2020-1-1 12:20:30") # 12
```

#### hours

返回两个日期相差的小时数

```python
dateutils.hours("2019-6-3 20:1:12","2020-5-3 13:13:13") # 8034
```

#### minute

返回时间的分钟数

```python
dateutils.minute("2020-5-3 13:13:13") # 13
```

#### second

返回时间的秒数

```python
dateutils.second("2020-5-3 13:13:33") # 33
```

#### weekday

返回某个日期是星期几, 记周一为0， 周日为6

```python
dateutils.weekday("2019-6-3") # 0
```

#### isoweekday

基于iso标准，返回某个日期是星期几，记周一为1， 周日为7

```python
dateutils.isoweekday("2019-6-3") # 1
```

#### weeknum

返回某个日期是当年的第几周，含1月1日为周为第一周

```python
dateutils.weeknum('2012-1-2') # 2
```

#### isoweeknum

返回某个日期当年的 ISO 周计数， 即当年第一个周四开始记为第一周

```python
dateutils.isoweeknum('2012-1-2') # 1
```

#### isomonth

返回某个日期字符串的 ISO 格式的月份

~~~python
dateutils.isomonth("2012-1-2") # 2012-01
~~~

