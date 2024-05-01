# backtrader-test

## Installation Guide

```zsh
# install backtrader and yahoo data feed
poetry add backtrader
poetry add yfinance

# bug fix #1 - fixed!
# add user agent
# ./.venv/lib/python3.10/site-packages/
# backtrader/feeds/yahoo.py line 271
sess.headers['User-Agent'] = 'backtrader'
# yfinance requires a user agent as of ?

# bug fix #2 - fixed!
# remove warnings
# backtrader/plot/locator.py line 35
from matplotlib.dates import (HOURS_PER_DAY, MIN_PER_HOUR, SEC_PER_MIN,
                              MONTHS_PER_YEAR, DAYS_PER_WEEK,
                              SEC_PER_HOUR, SEC_PER_DAY,
                              num2date, rrulewrapper, YearLocator,
                              MicrosecondLocator)
# matplotlib.dates warnings deprecated in >3.3.0
```
