# Simple-27c1001-dumper
Very simple Arduino based 27C1001 EPROM dumper, based on [kesrut/simple-27C512-dumper](https://github.com/kesrut/simple-27C512-dumper)

## Pin connections
This connections are for the M27C1001 from ST Microelectronics. Other variations of the 27c1001 should be compatible, but cross reference the datasheet of your exact model before blaming me ;)

|Arduino|27c1001|Comments|
|-------|-------|--------|
|22|A0|Address 0|
|23|A1|Address 1|
|24|A2|Address 2|
|25|A3|Address 3|
|26|A4|Address 4|
|27|A5|Address 5|
|28|A6|Address 6|
|29|A7|Address 7|
|30|A8|Address 8|
|31|A9|Address 9|
|32|A10|Address 10|
|33|A11|Address 11|
|34|A12|Address 12|
|35|A13|Address 13|
|36|A14|Address 14|
|37|A15|Address 15|
|38|A16|Address 16|
|40|Q0|Data 0|
|41|Q1|Data 1|
|42|Q2|Data 2|
|43|Q3|Data 3|
|44|Q4|Data 4|
|45|Q5|Data 5|
|46|Q6|Data 6|
|47|Q7|Data 7|
|52|E (CE)|Chip Enable|
|53|G (OE)|Output Enable|
|GND|Vpp|Program Supply|
|GND|Vss|Ground|
|+5V|Vcc|Power|

## Instructions
- Upload sketch to an Arduino Mega
- Connect as stated above
- Execute `python dump.py COMX dump.bin` (being COMX your COM port, like COM2, COM3...)

Dump should take about 10 minutes. The `delay()` between setting the address and reading the data could be much shorter (datasheet states 100ns, and I'm waiting 5 whole ms), but slow and steady wins the race. Feel free to tweak it :)
