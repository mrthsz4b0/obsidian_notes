# Formulas
## convertFromUtc()
### Format options
#### Standard date and time format specifiers

To format date in Power Automat in different dates format as you desire, you have to check the following table that describes the standard date and time format specifiers.

FORMAT SPECIFIER

DESCRIPTION

EXAMPLES

“d”

Short date pattern.  
  
More information:[The short date (“d”) format specifier](https://docs.microsoft.com/en-us/dotnet/standard/base-types/standard-date-and-time-format-strings#ShortDate).

2009-06-15T13:45:30 -> 6/15/2009 (en-US)  
  
2009-06-15T13:45:30 -> 15/06/2009 (fr-FR)  
  
2009-06-15T13:45:30 -> 2009/06/15 (ja-JP)

“D”

Long date pattern.  
  
More information:[The long date (“D”) format specifier](https://docs.microsoft.com/en-us/dotnet/standard/base-types/standard-date-and-time-format-strings#LongDate).

2009-06-15T13:45:30 -> Monday, June 15, 2009 (en-US)  
  
2009-06-15T13:45:30 -> 15 июня 2009 г. (ru-RU)  
  
2009-06-15T13:45:30 -> Montag, 15. Juni 2009 (de-DE)

“f”

Full date/time pattern (short time).  
  
More information: [The full date short time (“f”) format specifier](https://docs.microsoft.com/en-us/dotnet/standard/base-types/standard-date-and-time-format-strings#FullDateShortTime).

2009-06-15T13:45:30 -> Monday, June 15, 2009 1:45 PM (en-US)  
  
2009-06-15T13:45:30 -> den 15 juni 2009 13:45 (sv-SE)  
  
2009-06-15T13:45:30 -> Δευτέρα, 15 Ιουνίου 2009 1:45 μμ (el-GR)

“F”

Full date/time pattern (long time).  
  
More information: [The full date long time (“F”) format specifier](https://docs.microsoft.com/en-us/dotnet/standard/base-types/standard-date-and-time-format-strings#FullDateLongTime).

2009-06-15T13:45:30 -> Monday, June 15, 2009 1:45:30 PM (en-US)  
  
2009-06-15T13:45:30 -> den 15 juni 2009 13:45:30 (sv-SE)  
  
2009-06-15T13:45:30 -> Δευτέρα, 15 Ιουνίου 2009 1:45:30 μμ (el-GR)

“g”

General date/time pattern (short time).  
  
More information: [The general date short time (“g”) format specifier](https://docs.microsoft.com/en-us/dotnet/standard/base-types/standard-date-and-time-format-strings#GeneralDateShortTime).

2009-06-15T13:45:30 -> 6/15/2009 1:45 PM (en-US)  
  
2009-06-15T13:45:30 -> 15/06/2009 13:45 (es-ES)  
  
2009-06-15T13:45:30 -> 2009/6/15 13:45 (zh-CN)

“G”

General date/time pattern (long time).  
  
More information: [The general date long time (“G”) format specifier](https://docs.microsoft.com/en-us/dotnet/standard/base-types/standard-date-and-time-format-strings#GeneralDateLongTime).

2009-06-15T13:45:30 -> 6/15/2009 1:45:30 PM (en-US)  
  
2009-06-15T13:45:30 -> 15/06/2009 13:45:30 (es-ES)  
  
2009-06-15T13:45:30 -> 2009/6/15 13:45:30 (zh-CN)

“M”, “m”

Month/day pattern.  
  
More information: [The month (“M”, “m”) format specifier](https://docs.microsoft.com/en-us/dotnet/standard/base-types/standard-date-and-time-format-strings#MonthDay).

2009-06-15T13:45:30 -> June 15 (en-US)  
  
2009-06-15T13:45:30 -> 15. juni (da-DK)  
  
2009-06-15T13:45:30 -> 15 Juni (id-ID)

“O”, “o”

round-trip date/time pattern.  
  
More information: [The round-trip (“O”, “o”) format specifier](https://docs.microsoft.com/en-us/dotnet/standard/base-types/standard-date-and-time-format-strings#Roundtrip).

[DateTime](https://docs.microsoft.com/en-us/dotnet/api/system.datetime) values:  
  
2009-06-15T13:45:30 (DateTimeKind.Local) –> 2009-06-15T13:45:30.0000000-07:00  
  
2009-06-15T13:45:30 (DateTimeKind.Utc) –> 2009-06-15T13:45:30.0000000Z  
  
2009-06-15T13:45:30 (DateTimeKind.Unspecified) –> 2009-06-15T13:45:30.0000000  
  
[DateTimeOffset](https://docs.microsoft.com/en-us/dotnet/api/system.datetimeoffset) values:  
  
2009-06-15T13:45:30-07:00 –> 2009-06-15T13:45:30.0000000-07:00

“R”, “r”

RFC1123 pattern.  
  
More information: [The RFC1123 (“R”, “r”) format specifier](https://docs.microsoft.com/en-us/dotnet/standard/base-types/standard-date-and-time-format-strings#RFC1123).

2009-06-15T13:45:30 -> Mon, 15 Jun 2009 20:45:30 GMT

“s”

Sortable date/time pattern.  
  
More information: [The sortable (“s”) format specifier](https://docs.microsoft.com/en-us/dotnet/standard/base-types/standard-date-and-time-format-strings#Sortable).

2009-06-15T13:45:30 (DateTimeKind.Local) -> 2009-06-15T13:45:30  
  
2009-06-15T13:45:30 (DateTimeKind.Utc) -> 2009-06-15T13:45:30

“t”

Short time pattern.  
  
More information: [The short time (“t”) format specifier](https://docs.microsoft.com/en-us/dotnet/standard/base-types/standard-date-and-time-format-strings#ShortTime).

2009-06-15T13:45:30 -> 1:45 PM (en-US)  
  
2009-06-15T13:45:30 -> 13:45 (hr-HR)  
  
2009-06-15T13:45:30 -> 01:45 م (ar-EG)

“T”

Long time pattern.  
  
More information: [The long time (“T”) format specifier](https://docs.microsoft.com/en-us/dotnet/standard/base-types/standard-date-and-time-format-strings#LongTime).

2009-06-15T13:45:30 -> 1:45:30 PM (en-US)  
  
2009-06-15T13:45:30 -> 13:45:30 (hr-HR)  
  
2009-06-15T13:45:30 -> 01:45:30 م (ar-EG)

“u”

Universal sortable date/time pattern.  
  
More information: [The universal sortable (“u”) format specifier](https://docs.microsoft.com/en-us/dotnet/standard/base-types/standard-date-and-time-format-strings#UniversalSortable).

With a [DateTime](https://docs.microsoft.com/en-us/dotnet/api/system.datetime) value: 2009-06-15T13:45:30 -> 2009-06-15 13:45:30Z  
  
With a [DateTimeOffset](https://docs.microsoft.com/en-us/dotnet/api/system.datetimeoffset) value: 2009-06-15T13:45:30 -> 2009-06-15 20:45:30Z

“U”

Universal full date/time pattern.  
  
More information: [The universal full (“U”) format specifier](https://docs.microsoft.com/en-us/dotnet/standard/base-types/standard-date-and-time-format-strings#UniversalFull).

2009-06-15T13:45:30 -> Monday, June 15, 2009 8:45:30 PM (en-US)  
  
2009-06-15T13:45:30 -> den 15 juni 2009 20:45:30 (sv-SE)  
  
2009-06-15T13:45:30 -> Δευτέρα, 15 Ιουνίου 2009 8:45:30 μμ (el-GR)

“Y”, “y”

Year month pattern.  
  
More information: [The year month (“Y”) format specifier](https://docs.microsoft.com/en-us/dotnet/standard/base-types/standard-date-and-time-format-strings#YearMonth).

2009-06-15T13:45:30 -> June 2009 (en-US)  
  
2009-06-15T13:45:30 -> juni 2009 (da-DK)  
  
2009-06-15T13:45:30 -> Juni 2009 (id-ID)