# C Programming Projects

![C](https://img.shields.io/badge/C-00599C?logo=c&logoColor=white)
![IPC144](https://img.shields.io/badge/IPC144-Intro%20to%20C-orange)

A collection of C projects from my Intro to C coursework — structs, file I/O, dynamic data processing, input validation, and ASCII rendering.

---

## BabyNameFinder

A data analysis tool that processes 176,000+ baby name records spanning 110 years of Ontario data (1914–2023). Reads from CSV files and provides interactive search, ranking, and visualization features.

### Features
- **Name Search** — find how many babies had a given name each year, with male/female/combined totals
- **Top 5 Rankings** — find the 5 most popular names for any given year, split by gender
- **ASCII Histogram** — visualize a name's popularity trend across 5-year cohorts from 1914 to 2023
- **CSV Parsing** — loads two separate datasets (female + male) and merges them into a unified record array

### Technical Implementation
- `struct BabyNameRecord` — models each record with year, name, and frequency
- `loadData()` — parses CSV files with `fopen`/`fscanf` into a flat array of up to 180,000 records
- `writeCombinedFile()` — merges both datasets and writes to a combined output file
- Case-insensitive search via `convertToUppercase()` before string comparison
- Input validation loop for year range (1914–2023) and menu choices

### How to Run
```bash
cd BabyNameFinder
gcc -Wall project.c projectmain.c -o babynames
./babynames
```

Requires `femalebabynames.csv` and `malebabynames.csv` in the same directory (both included).

---

## TrainSystem

An interactive ASCII art generator that draws a train based on user input — see [its own README](TrainSystem/README.md) for details on how the rendering handles direction and car count.

### How to Run
```bash
cd TrainSystem
gcc -Wall -o trainsystem *.c
./trainsystem
```

---
*Xenofon Gkioka*
