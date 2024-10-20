This repository contains spreadsheets associated with topics on my website actionphysics.uk

Individual spreadsheets are referenced from the website.

DayLength_2TermFourierApprox_Formulas.csv
=========================================
This file was produced from LibreOffice Calc (version 24.2.5.2). It should be compatible with MS Excel (not tested).

The file is a CSV file containing formulas rather than calculated results, so that you can review for correctness (open-source principle) and/or make changes to your local copy if you wish. To load the CSV file
into a LibreOffice Calc spreadsheet, follow this sequence:

     (a) open a new LibreOffice Calc spreadsheet
     (b) Sheet > Insert sheet from file...
     (c) Select the downloaded .csv file in the chooser pop-up, and click "Insert"
     (d) In the Text Import pop-up, tick the "Evaluate formulas" box, and click "OK"
     (e) In the Insert Sheet pop-up, click "OK"

The spreadsheet calculates the variation in the time of solar noon through the year. There are two principal causes of the variation in the time of solar noon:

(1) the variation in the Earth's orbital angular velocity around the Sun, leading to a variation in the time of solar noon with a period of 1 year. This is the *only* cause modelled in the spreadsheet.

(2) the tilt of the Earth's axis of rotation which leads to a variation in the time of solar noon with a period of half a year (and to the seasons, of course). This cause of variation is *not* modelled in the spreadsheet.

The spreadsheet was created only to illustrate that the variation in the Earth's orbital angular velocity around the Sun affects the time of solar noon. It does *not* calculate the variation in orbital angular 
velocity using any first-principles method based on the Earth's slightly elliptical orbit around the Sun. Instead it assumes that the annually-varying angular velocity W can be expressed using a two-term partial Fourier series,

W = A_0 + A_1 cos (2 pi t/P)

where A_0 is the constant term of the Fourier series, A_1 is the first cosine coefficient, t is time, P is the period (1 year = 365.25 days = 31557600 seconds), and pi = 3.14159...
