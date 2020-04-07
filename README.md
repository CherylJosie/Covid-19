# Covid-19

This repository contains a Libre Office .ods spreadsheet to graph and model the Johns Hopkins global Covid-19 time series database.

Deaths/day/100K are scaled off the raw database using the Wikipedia estimate of global population, or scaled off the filtered-by-nation data using the Wikipedia estimate of national population, and then modeled with:

https://en.wikipedia.org/wiki/Gaussian_function.

Total estimated deaths per 100K are summed (integrated) across the modeled deaths/day/100K Gaussian and then rescaled back up to the total estimated deaths in the entire world or in the selected nation.

The Gaussian function constants
1) A=height
2) B=center
3) C=width

are indexed and selectable by nation for display over the filtered by-nation deaths/day/100K processed time series.

Another set of these three constants A, B, C is reserved for the entire world.

Two more sets of these three constants are reserved for visually replicated renditions of the worst-case models for the UK and US in the Imperial College of London's Covid-19 Response Team publication:

https://www.imperial.ac.uk/media/imperial-college/medicine/sph/ide/gida-fellowships/Imperial-College-COVID19-NPI-modelling-16-03-2020.pdf.

There are three sets of charts:
1)  Entire world
2)  Filtered-by-nation, some with two nations comparable side-by-side on independent axes
3)  Filtered-by-nation, with two nations comparable side-by-side on the same axis, deaths/day/100K only, with Gaussian function models by nation, and with Imperial College of London Covid-19 Response Team's worst-case Guassian function models (UK and US) included for reference.

There are three types of charts:
1)  Raw time series data (entire world and filtered-by-nation)
    1)  Confirmed cases
    2)  Deaths
    3)  Recovered cases
2)  Processed data (entire world and filtered-by-nation)
    1)  Active cases/day
    2)  New cases/day
    3)  Deaths/day
    4)  Deaths%/confirmed cases
    5)  Deaths%/recovered cases
    6)  Deaths/day/100K
    7)  Gaussian function model of deaths/day/100K (visual fit)
3)  Processed data (filtered-by-nation only)
    1)  Confirmed cases/100K
    2)  Recovered/100K
    3)  Deaths/100K
    4)  New cases/day/100K
    5)  Active cases/day/100K
    6)  Km/active case
        (spacing between infected neighbors, square uniform grid model)
        (requires the population density estimate from the Wikipedia article for the nation)
  
Filtered-by-nation charts include an optional time shift to separate the filtered-by-nation time series traces from each other for better clarity. The world deaths/day/100K chart with Gaussian model includes an optional time shift to separate the model trace from the time series trace for better clarity.

One trace can be suppressed on the two-nation graphs by deleting the name of one nation from the selector field.

If the recovered cases data is suspected of inaccuracy, all traces that are dependent on recovered cases data can be suppressed by selecting the 'recovered data good' field to FALSE.

Updating the Johns Hopkins data:
1)  The spreadsheet is structured as three sets of overlaid sheets, with one sheet
    1)  -data for the respective time series
        1)  C(onfirmed)
        2)  D(eaths)
        3)  R(ecovered)
    and four more sheets
    2)  -detector
    3)  -adjusted
    4)  -filtered
    5)  -filtered_2
under each time series to process and filter the data.
2)  There is a separate sheet for each time series
    1)  C-data
    2)  D-data
    3)  R-data
and all that is required is to
        1)  select all
        2)  delete
        3)  paste special unformatted comma-delimited into cell A10.
3)  All functions and graphs update immediately with no further user input required. The spreadsheet detects (-detector) non-monotonically increasing time series data and substitutes (-adjusted) a copy of the previous value (assumes it's an error or omission).
4)  This also means that the last date and time series data point copies indefinitely (through the initialized range of cells) at the right end of the sheet so that all empty/copied fields at the end of the sheet automatically map to the same point on the XY charts. If the time series grows in length, the sheet detects that the additional points are monotonically increasing and the chart traces extend automatically with no additional user input required.

Instructions for use are included on the 'Instructions' sheet.

The Gaussian models are curve fit visually/manually to death/day/100K. There's no least squares math or fancy inputs.
  
Since no experts are coming out with any predictive models, I figured that visually modeling to the deaths/day/100K per the example from the Imperial College of London Covid-19 Response Team was the only way we were going to have any advance information at all. It's up to us.

The spreadsheet is a little rough around the edges but I've debugged it and it seems to work as advertised.

I am using LibreOffice from the Ubuntu 18.04 Linux distribution. Sometimes the charts stop updating after changes to the spreadsheet. When that happens, save your work and restart the software. It's buggy.

Future project might be to adapt a copy of this spreadsheet to the US time series that were recently published by Johns Hopkins, but I don't see the point at this time unless someone is trying to decide whether to travel inside the US, and I'm not.

Cheryl
