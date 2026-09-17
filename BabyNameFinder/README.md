# BabyNameFinder

A console tool that loads 176,000+ Ontario baby name records (1914–2023, split by sex) from CSV and lets you search, rank, and chart them.

## Build and run

```bash
gcc -Wall project.c projectmain.c -o babynames
./babynames
```

Needs `femalebabynames.csv` and `malebabynames.csv` in the same directory (both are included).

## What it does

```
Baby Name Data Viewer
1. number of babies
2. top 5 names
3. histogram
4. exit
```

1. **Number of babies** — look up a name and see a year-by-year count.
2. **Top 5 names** — for a given year, the 5 most popular names among girls, boys, and combined.
3. **Histogram** — a name's popularity charted in 5-year cohorts from 1914–2023:

```
Histogram for Olivia
1994-1998 |*********************************
1999-2003 |*****************************************************
2004-2008 |***********************************************************************
2009-2013 |********************************************************************************
2014-2018 |****************************************************************************
2019-2023 |***************************************************************
```

On exit, it also writes `combined.txt` — both CSVs merged into one file.

## Notes

Records are held in a fixed-size static array (`MAX_RECORDS 180000`) rather than allocated dynamically, since the two input files are a known, bounded size. Name matching is case-insensitive — input and stored names are both uppercased before comparison.
