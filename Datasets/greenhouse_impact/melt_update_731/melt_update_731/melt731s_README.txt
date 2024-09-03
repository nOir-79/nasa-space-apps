Readme for melt / freeze products

FLAT BINARY:
4 files per year:

YYYYVVVVearlymelt.int.304.448.c	-	earliest observed melt
YYYYVVVVmelt.int.304.448.c			-	permanent melt, should be melt conditions always after this
YYYYVVVVfreeze.int.304.448.c		-	earliest observed freeze
YYYYVVVVlatefreeze.int.304.448.c	-	permanent freeze, should be all freeze conditions after this

YYYY - year
VVVV - version, currently 731s.

Integer arrays, 304 x 448, big endian (windows and mac will need to
byteswap). Values are the day of year where the event described in the filename occurs (in 'melt', a value of 175 means melt
conditions are present on June 24 in a non-leap year).

NETCDF:
1 file per year:
YYYYVVVVmeltfreeze.nc
YYYY - year
VVVV - version, currently 731s.

Four datafields: earlymelt, melt, earlyfreeze, freeze

There is a sample routine on our site called ncdftest.py that reads
and plots the data.

Data Flags:
-3		- land
0 		- open water
75-410	- valid data 
All negative values represent pixels where melt or freeze could not be
determined; the different negative values correspond to different
criteria in the algorithm and should not be considered for analysis. The earliest melt possible due to the
algorithm is day 75.

Contact info -
Linette Boisvert, linette.n.boisvert@nasa.gov, 301-614-5710
Jeff Miller, jeffrey.a.miller@nasa.gov, 301-614-6611

README last updated 03/01/2018
