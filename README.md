# Covid-19

This repository contains a Libre Office .ods spreadsheet for use in displaying the Johns Hopkins global database graphically.
It includes Guassian customizable models that are curve-fitted visually to the deaths/day/100K
like the Imperial College of London's Covid-19 Response Team published
(a visual copy of their worst-case models is included for reference but it seems useless at this time).

Two nations can be independently selected and graphically compared on separate axes
with an optional time shift to separate the traces/models for better clarity.

The spreadsheet calculates deaths%/confirmed cases and deaths%/resolved cases
with an option to ignore resolved cases and blank all traces related to this input.

The spreadsheet also calculates deaths/day/100K like Imperial College of London and
all models are expressed in these terms. Total estimated deaths are calculated from the Gaussian models.

A separate set of plots is created for the entire world.

Updating the Johns Hopkins data is simple.
Instructions for use are included on the 'Instructions' sheet.

The Gaussian models are curve fit visually/manually. There's no least squares math or fancy inputs.
