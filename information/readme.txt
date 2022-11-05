Dear WWLLN Hosts,
These AE files constitute a daily reprocessing of all the raw WWLLN toga data
with the same stroke_B algorithm, but this time, AFTER the loction is
determined, then the Energy per stroke is determined (see
wwlln.net/publications #52 for details on the method)

These files should be considered the BETA version, with final production
version coming probably this summer.  The main final version will have a
slightly improved stroke_B version for location, and the raw data files used
will include some extra data, which were not available in real time for the
Afiles.

The format of these files is similar to Afiles, with the addition of three
extra parameters on each line the Energy in Joules, Energy uncertainty and
Nstations used for energy:
:
The format for the A files is:

YYYY/MM/DD, hh:mm:ss, lat, long, uncertainty (micro-s), nstn, power (J), power
uncertainty (J), nstn_power
These files are located in the directory AEyear (AE2012) directory, and they
flat ascii files,one line per stroke.

Format of data files:
  Files are ascii text files labeled with the date and time of the data such
as
  A20100203.loc  for data from 2010/02/03.  All data in UTC
  sample:
  2012/4/4,00:00:01.369657,  14.9924, -091.3758, 25.1, 8, 1109.25, 295.14, 6
  2012/4/4,00:00:01.479687,  14.7209, -087.7137, 10.1, 5, 1243.98, 431.82, 5
  2012/4/4,00:00:01.444158,  06.0155,  097.2494, 03.9, 5, 1004.87, 249.15, 3
  2012/4/4,00:00:01.534491, -17.6947,  040.8280, 16.2, 6, 5534.23, 4172.98, 3
  ...
  Year/Mo/Da,Hr:Mn:Sec.fract, Lat    , Long    ,Resid, Nsta, power (kW), power uncertainty (kW), nstn_power

  where:
  Date and time are in UTC
  Lat, long in Fractional Degrees
  Resid is the residual fit error in micrfoseconds (always < 30 microseconds)
  Nsta is the number of WWLLN stations which detected the stroke (alway >5)
  Energy (J)  - RMS energy from 7 to 17 kHz in 1.3 ms sample time
  energy uncertainty (J) 
  nstn_power - subset of Nsta within the range 1000 to 8000 km distant from strok and used for power estimate




In addition, every hour we determine the Relative Detection Efficiency
for the entire globe, on a 5x5 degree or 1x1 degree grid.  These 
deMaps are located in  in matlab files. Each matlab
file has 3 variables:

de_map - relative detection efficiency map in 5 bin
de_map_high - de_map that has been smoothed to 1 resolution
de_time - time of the 24 maps in matlab datenum format

The de_map file are centered so that the first entry, de_map(1,1,1), gives the
detection efficiency for the bin that
spans -180 E to -175 E, 85N to 90N for UTC hour 00:00 to 00:59.

The first index is increasing longitude (1 = -180 to -175, 2 = -175 to -170,
etc) , the second index is decreasing
latitude (1 = 90 to 85, 2 = 85 to 80, etc) and the third index is the UTC hour
plus one (1 = 00:00 to 00:59, 2 =
01:00 to 01:59, etc). 


As always, please contact me with any problems or requests.
I am able to temporarily re-post data from previously in the year if you have
lost something.



More Questions?  
  Contact Prof. Robert Holzworth, Director of WWLLN, and Professor of Earth and Space Sciences
  University of Washington, Box 351310, Seattle, WA 98195   (bobholz@uw.edu)


