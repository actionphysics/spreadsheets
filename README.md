This repository contains spreadsheets associated with topics on my website actionphysics.uk

Files in this repository actionphysics/spreadsheets are usually CSV files containing formulas rather than calculated results, unless noted otherwise in the per-file descriptions below. This means that you can review for correctness (open-source principle) and/or make changes to your local copy to do different calculations - not just see the results of my calculation. To load the CSV file
into a LibreOffice Calc spreadsheet, follow this sequence:

     (a) open a new LibreOffice Calc spreadsheet
     (b) Sheet > Insert sheet from file...
     (c) Select the downloaded .csv file in the chooser pop-up, and click "Insert"
     (d) In the Text Import pop-up, tick the "Evaluate formulas" box, and click "OK"
     (e) In the Insert Sheet pop-up, click "OK"

Individual spreadsheets are referenced from the website.

DayLength_2TermFourierApprox_Formulas.csv
=========================================
This file was produced from LibreOffice Calc (version 24.2.5.2). It should be compatible with MS Excel (not tested).

The spreadsheet calculates the variation in the time of solar noon through the year, based on an empirical description of the variation of the Earth's orbital angular velocity through the year. There are two principal causes of the variation in the time of solar noon:

(1) the variation in the Earth's orbital angular velocity around the Sun, leading to a variation in the time of solar noon with a period of 1 year. This is the *only* cause modelled in the spreadsheet.

(2) the tilt of the Earth's axis of rotation which leads to a variation in the time of solar noon with a period of half a year (and to the seasons, of course). This cause of variation is *not* modelled in the spreadsheet.

The spreadsheet was created only to illustrate that the variation in the Earth's orbital angular velocity around the Sun affects the time of solar noon. It does *not* calculate the variation in orbital angular 
velocity using any first-principles method based on the Earth's slightly elliptical orbit around the Sun. Instead it assumes that the annually-varying angular velocity W can be expressed using a two-term partial Fourier series,

W = A_0 + A_1 cos (2 pi t/P)

where A_0 is the constant term of the Fourier series, A_1 is the first cosine coefficient, t is time, P is the period (1 year = 365.25 days = 31557600 seconds), and pi = 3.14159...

The time unit in the spreadsheet is 1 day, in line with usual spreadsheet practice.

Values for all constants are provided in the spreadsheet. In particular A_0 = 0.01720242 radian/day gives one complete revolution per year as required, and A_1 = 5.7024E-4 radian/day gives approximately the peak amplitude of 
about 450 s for the once-per-year term in the equation of time. 

Orbit_RK4_Formulas.csv
======================
This file was produced from LibreOffice Calc (version 24.2.5.2). It should be compatible with MS Excel (not tested).

The single-tab spreadsheet implements a fourth order Runge-Kutta integration of the coupled radial and angular equations for the Earth's orbit around the Sun, solving for r(t) and \theta(t).

Values of the required constants are supplied in the spreadsheet. These are:

Universal gravitational constant G = 6.6743E-11 m^3 kg^-1 s^-2
Solar mass M = 1.989E30 kg
Perihelion distance 147098075000 m (https://www.astropixels.com/ephemeris/perap2001.html)
Perihelion speed 30292.37 m/s

The perihelion speed was modified slightly from
