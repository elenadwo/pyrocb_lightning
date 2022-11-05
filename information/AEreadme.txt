Dear WWLLN Hosts,
These AE files constitute a daily reprocessing of all the raw WWLLN toga data
with the same stroke_B algorithm, but this time, AFTER the loction is
determined, then the Energy per stroke is determined (see
wwlln.net/publications #52 for details on the method)

These files should be considered the BETA version, with final production
version coming by Jan 2014.  The main final version will have a
slightly improved stroke_B version for location, and the raw data files used
will include some extra data, which were not available in real time for the
Afiles.

If the data are in compressed format *.tgz:
then unpack with
tar -zxvf AE2009.tgz  
Or you can also extract individual .loc files with:
tar -xvf AE2009.tgz AE20090515.loc

The format of these AE files is similar to Afiles, with the addition of three
extra parameters on each line the Energy in Joules, Energy uncertainty and
Nstations used for energy:
:
The format for the AE files is:

YYYY/MM/DD, hh:mm:ss, lat, lon, resid, nstn, Energy (J), Energy uncertainty (J), nstn_energy
Where: Date/time in UTC
Lat, Lon in fractional degrees (geographic coordinated)
resid is the residual fit error in Microseconds (always <30)
nstn is the number of WWLLN stations participarting in the location fit
energy is the RMS energy (in Joules) of the stroke (from 1.3 ms waveform sampling between 7 and 18 kHz)
energy uncertainty (energy error of the fit in Joules)
nstn_eneregy is the subset of nstn stations between 1000 and 8000 km from the stroke whose energy data were used in the energy estimate.

Format of data files:
  AE Files are ascii text files labeled with the date and time of the data such
as
2012/4/23,00:00:00.149517,  26.5463,  135.4961, 13.2, 9, 2741.38, 332.49, 5
2012/4/23,00:00:00.834707,  10.7970,  125.8763, 06.2, 7, 1744.95, 131.47, 6
2012/4/23,00:00:00.943868,  19.4564, -070.9303, 17.2, 6, 298.00, 118.10, 4
2012/4/23,00:00:00.922768,  14.1879, -090.7451, 24.0, 16, 507.86, 136.14, 13
2012/4/23,00:00:00.943845,  19.3481, -070.9295, 16.4, 5, 212.37, 48.31, 4
2012/4/23,00:00:01.205949,  14.2636, -090.4189, 14.0, 11, 140.89, 33.33, 9

  where (as above):
  Date and time are in UTC
  Lat, lon in Fractional Degrees
  Resid is the residual fit error in micrfoseconds (always < 30 microseconds)
  Nsta is the number of WWLLN stations which detected the stroke (alway >=5)
  Energy (J)  - RMS energy from 7 to 18 kHz in 1.3 ms sample time
  energy uncertainty (J) 
  nstn_energy - subset of Nsta within the range 1000 to 8000 km distant from strok and used for power estimate

NOTE: if the energy =0 it means we have NO ENERGY data for that stroke
Also, if the energy error is more than 1/2 of the energy, it means that the energy 
is not well constrained, so you  should use those energy values with extra care.
nstn_energy is always a subset of Nsta.



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


