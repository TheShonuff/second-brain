---
tags:
  - SQL
---
# TO_CHAR
Converts either a number or a date value to a string value.

### Syntax
TO_CHAR(input_value, [format_mask], [nls_parameter] )

- **Input Value** Is a mandatory value to convert into a string type. This is the main input of the functio
- **Format Mask** This is the format that the *input value* should be displayed as.
- **NLS Parameter** This value is used to determine how the output value is displayed.


[Example](https://www.databasestar.com/oracle-to_char/)
## Format Mask

### Year
| Parameter | Explanation                                                     |
| --------- | --------------------------------------------------------------- |
| YEAR      | Year, spelled out in full words                                 |
| YYYY      | 4-digit year                                                    |
| YYY       | Last 3 digits of year                                           |
| YY        | Last 2 digits of year                                           |
| Y         | Last digit of year                                              |
| IYY       | Last 3 digits of ISO year                                       |
| IY        | Last 2 digits of ISO year                                       |
| I         | Last digit of ISO year                                          |
| IYYY      | 4-digit year, Which is based on the ISO standard                |
| RRRR      | This format accepts a 2-digit year, and returns a 4-digit year. |                                                                 |

### Month
| Parameter | Explanation                                                 |
| --------- | ----------------------------------------------------------- |
| Q         | Quarter of year, from 1 to 4. JAN to MAR = 1                |
| MM        | Month, from 01 to 12. Jan = 01                              |
| MON       | Abbreviated Name of month                                   |
| MONTH     | Name of month, padded with blanks to length of 9 characters |
| RM        | Roman numeral month, from 1 to XII. Jan = 1                                                            |

### Week
| Parameter | Explanation                                                                                    |
| --------- | ---------------------------------------------------------------------------------------------- |
| WW        | Week of year, from 1 to 53. Week 1 starts on the first day of the year                         |
| W         | Week of month, from 1 to 5. Week 1 starts on the first day of the month and end on the seventh |
| IW        | Week of the year, from 1 to 52 or 1 to 53, based on ISO standard                                                                                               |

### Day
| Parameter | Explanation                |
| --------- | -------------------------- |
| D         | Day of week, from 1 to 7   |
| DAY       | Name of day                |
| DD        | Day of month, from 1 to 31 |
| DDD       | Day of year, from 1 to 366 |
| DY        | Abbreviated name of day    |
| J         | Julian day, which is the number of days since January 1, 4712 BC                           |

### Time
| Parameter | Explanation                            |
| --------- | -------------------------------------- |
| HH        | Hour of the day, from 1 to 12          |
| HH12      | Hour of day, from 1 to 12              |
| HH24      | Hour of day, from 0 to 23              |
| MI        | Minute, from 0 to 59                   |
| SS        | Second, from 0 to 59                   |
| SSSSS     | Seconds past midnight, from 0 to 86399 |
| FF        | Fractional seconds. This uses a value from 1 to 9 after FF, to indicate the number of digits in the fractional seconds(IE FF7)                                       |

### Indicators
| Parameter  | Explanation                 |
| ---------- | --------------------------- |
| AM, PM     | Meridian Indicator          |
| AD or A.D  | AD indicator                |
| BC or B.C. | BC indicator                |
| TZD        | Daylight saving information |
| TZH        | Time Zone Hour              |
| TZM        | Time Zone Minute            |
| TZR        | Time Zone Region                            |


## Examples
```SQL
SELECT TO_CHAR(12345.67, '99999.9') FROM DUAL;
```

```SQL
SELECT TO_CHAR(12345, '00000000') FROM dual;
```

```SQL
SELECT TO_CHAR(SYSDATE, 'YYYY_MM_DD') FROM dual;
```

