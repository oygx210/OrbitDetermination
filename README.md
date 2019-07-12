# OrbitDetermination
Orbit Determination with optical observations
#####################################################################
Instructions
#####################################################################

Download SpaceGuidance.zip and extract it to your drive
Open matlab and locate the folder SpaceGuidance
SpaceGuidance contains some common, valadoo’s functions from
celestrack and required TLE and EOP dataset.

You have two problems
1.	Simulated Problem
	a.	Run TLE_Simulate.m to generate observables
		i.	This file propagates tle for desired time add noise and
		saves observables in file data.txt
	b.	Run TLE_Opt.m 
		i.	Here you start with some unknown TLE (close to simulated
		TLE)
		ii.	Read observation from data.txt
		iii.	Solve using preferred optimization method
		iv.	Compare the results

#####################################################################
2.	Real problem from Photos
	a.	Process FITs images in astrometry.net
	b.	Find RA and DEC from SAOds9 and their time of observation
	c.	Save Ra and DEC to observationsAll.txt
	d.	Run SGN_OptimisationProblem_day1.m (This is solver for day 1
	observations)
		i.	Read data from observationsAll.txt 
		ii.	Start with initial TLE
		iii.	Use preferred optimization method to find correct
		solution 
		iv.	Compare the results
	e.	Similarly run  Run SGN_OptimisationProblem_day2.m and
	SGN_OptimisationProblem_day3.m for later days
 
#####################################################################
Important scripts
1. TLE_Simulate.m
2. TLE_Opt.m (requires observation from file data.txt)
3. SGN_OptimisationProblem_day1.m (requres observation from file
		observationsAll.txt)
4. SGN_OptimisationProblem_day2.m (requres observation from file
		observationsAll.txt)
5. SGN_OptimisationProblem_day3.m (requres observation from file
		observationsAll.txt)
#####################################################################
Important files
data.txt -- data generated throug simulated problem,
	contains  [julian date : RA (rad) : DEC(rad)]
observationsAll.txt -- data taken from processed images, contains 
	contains  [julian date : RA (rad) : DEC(rad)]

