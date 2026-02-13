# bugckettraps
We collected insects at light traps in Eastern MA, USA along an urban-to-rural gradient in Summer 2025. We are investigating the impacts of urbanization and light pollution on flight-to-light behavior. I suggest starting at Step 2. 

**Our hypotheses are:**

F2L (flight to light) bx (behavior) decreases at higher moon illumination levels.

F2L bx slope decreases as twilight length increases.

Different orders/sizes have different F2L bx. 
  Small bugs are being sucked up from immediate environment.
  Moths come out later.
  Large bugs will be more prevalent at rural traps relative to urban, small bugs    will be less impacted.
  
*What's the effect of moon phase on relative abundance in areas with open vs. closed canopy/degree of forestation?  
  F2L bx will be less affected by moon phase and urban lighting in urban areas.
  
F2L bx is higher in rural sites than urban sites (more concentrated light increases their bx, because urban spp are either less abundant or are selected against for having high F2L bx while this isn't something rural insects have had to select as hard for). Rural sites are more sensitive to all of these changes.

F2L bx is higher at sites with higher canopy cover (more canopy == more habitat AND more concentration of light). 

F2L bx is higher at sites with higher water % cover (more water == more habitat, but  maybe something about water reflectance too?).
  Can compare aquatic vs. terrestrial orders (trichoptera vs. lepidoptera)

**Step 1. Data cleaning in R (can skip this and go to step 2).**
We used data from our fieldwork in Summer 2025 that describes how many insects were caught in light traps for approximately 2 hours after sunset. We also measured canopy cover, percent developed land in a surrounding area, and several other environmental variables. We combined these sheets and also added data for several solar/lunar variables (e.g. twilight illumination and moon phase from msmielak's moonlit package.

  1a: Use the lat/lon coordinates to calculate some land cover characteristics from NLCD (National Land Cover Database) -> make a site.information.csv
  1b: Take the site.information.csv, bucketdata csv, canopy cover csv, environmental csv and clean and merge it in bucketcleaning rmd, as well as adding other variables re: twilight and moonlight using msmielak's moonlit pkg and suncalc.

**Step 2. Data analysis in R (start here)**
  2a. Create dfs to analyze abundance data regardless of order/size (abundance.data)
  2b. Create dfs to analyze diversity of insects based on their "morphotype". Because we only identified by order and size, we will consider each order/size combo a morphotype which represents insect diversity. You can do this by day of year (total diversity on a particular night) or time of sample (diversity at each sample time in a particular bucket).
  2c. Feel free to look at other things such as 
After step 1 where we merge all of the data into a single spreadsheet, we can begin to process our data in data.longer.csv to analyze it in R and assess the difference in flight-to-light behavior along our gradient and how it is altered by different environmental conditions.
