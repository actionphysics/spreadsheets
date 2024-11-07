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
This file was produced from LibreOffice Calc (version 24.2.5.2). It should be compatible with MS Excel (not tested) and Google Sheets.

The single-tab spreadsheet implements a fourth order Runge-Kutta integration of the coupled radial and angular equations for the Earth's orbit around the Sun, solving for r(t) and \theta(t).

Values of the required constants are supplied in the spreadsheet. These are:

Universal gravitational constant G = 6.6743E-11 m^3 kg^-1 s^-2 (https://en.wikipedia.org/wiki/Gravitational_constant)
Solar mass M = 1.988416E30 kg (https://en.wikipedia.org/wiki/Solar_mass)
Perihelion distance 147098074000 m (https://www.astropixels.com/ephemeris/perap2001.html)
Perihelion speed 30286.5033 m/s (https://en.wikipedia.org/wiki/Earth%27s_orbit modified to give exactly 4 revolutions in 4*365.25=1461 days)
Timestep h = 86400 s (can be modified for higher/lower precision)

The perihelion speed was modified slightly from the value 30.29 km/s given on the Wikipedia page, to give exactly 4 complete revolutions in 4*365.25 days.

See https://www.actionphysics.uk/index.php/solving-the-orbital-equations/ for more details including the meaning of each column in the calculation.

SolarNoon_NewtonRaphson.csv
===========================
This file was produced from LibreOffice Calc (version 24.2.5.2). It should be compatible with MS Excel (not tested) and Google Sheets.

The single-tab spreadsheet includes a table of values for the Earth's angle \theta in its orbit around the Sun, with \theta=0 at perihelion. These values were
found by solution of the orbital equations using the spreadsheet Orbit_RK4_formulas.csv (above).

Based on the tabulated values for \theta and a value for the Earth's angular velocity of rotation on its axis \omega, the spreadsheet calculates the deviations of the clock times of solar noon
where the deviations are due only to the effect of variation in the Earth's orbital angular velocity (ignoring the effect of the tilt of the Earth's axis of rotation).

See https://www.actionphysics.uk/index.php/at-last-the-first-term/ for more details including the meaning of each column in the calculation.

Cambridge_SolarNoon_Fourier_Formulas.csv
========================================
This file was produced from LibreOffice Calc (version 24.2.5.2). It should be compatible with MS Excel (not tested) and Google Sheets.

The single-tab spreadsheet includes a column of values for the time of solar noon from https://gml.noaa.gov/grad/solcalc/

The spreadsheet calculates the Fourier coefficients for a 3-term Fourier series (constant, once-per-year cycle, twice-per-year cycle) fitted to the deviation of solar noon from clock noon.

See https://www.actionphysics.uk/index.php/at-last-the-first-term/ for more details including the meaning of each column in the calculation.

TiltTerm_NewtonRaphson_Formulas.csv
===================================
This file was produced from LibreOffice Calc (version 24.2.5.2). It should be compatible with MS Excel (not tested) and Google Sheets.

The single-tab spreadsheet calculates the twice-per-year cyclical variation term in the variation of solar noon (equation of time). This term is due to the tilt of the Earth's axis
by about 23.5 degrees with respect to the perpendicular to the plane of the Earth's orbit around the Sun. The calculation isolates the twice-per-year variation by assuming that the Earth's 
orbit around the Sun is at constant angular velocity, as if the Earth's orbit were exactly circular. The spreadsheet uses the Newton-Raphson method to solve for each solar noon.

See https://www.actionphysics.uk/index.php/effect-of-tilt/ for more details including the meaning of each column in the calculation.

