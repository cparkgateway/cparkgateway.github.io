---
title: Python Code
description: None Provided
layout: code
---

```python
import math

def convert_months_to_days(month, isLeap):
    month_days = [0, 31, 59, 90, 120, 151, 181, 212, 243, 273, 304, 334]
    days = month_days[month-1]
    if(isLeap & (month > 2)):
        days += 1
    
    return days

def convert_years_to_days(year_input):
    year = year_input - 1
    leap_days = math.floor(year / 4) * 366
    nonleap_days = (year - math.floor(year / 4)) * 365
    return leap_days + nonleap_days 

day = 24
month = 2
year = 2020

base_days = convert_years_to_days(year) + convert_months_to_days(month, True) + day

day = int(input("Day: "))
month = int(input("Month: "))
year = int(input("Year: "))
isLeap = False
if((year % 4) == 0):
    isLeap = True

base_days2 = convert_years_to_days(year) + convert_months_to_days(month, isLeap) + day

difference = base_days2 - base_days
isNeg = False

print("Days off: " + str(difference))
if(difference < 0):
    difference = difference * -1
    difference = difference % 7
    isNeg = True
else:
    difference = difference % 7

if(isNeg):
    difference = (7 - difference) % 7

weekdays = ['Monday', 'Tuesday', 'Wednesday', 'Thursday', 'Friday', 'Saturday', 'Sunday']
print(weekdays[difference])
```
