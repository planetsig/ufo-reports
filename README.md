ufo-reports
===========

NUFORC geolocated and time standardized ufo reports for close to a century of data. 80,000 plus reports.

https://medium.com/@planetsig

NUFORC Data Conversion 

A general goal of this project was to format and enhance more than a century of NUFORC data so important questions can be applied and mixed with other data sets and questions answered with reasonable accuracy. Basically the locations needed to be geocoded and the duration time normalized to seconds. 

Full acknowledgement to the NUFORC organization and its trials and tribulations to capture and present this data to the world is acknowledged here. Sadly repeated contacts with NUFORC have left a bitter ugly introverted taste leading to a no reply context. Something akin to a bow finger. This project is the exciting humble technological reply. 

As presented here converting this data is not a trivial task. The NUFORC data is considered by some to be obfuscated on purpose, regardless it is some of the most badly formatted data I personally have ever seen. Two prior conversion attempts lead to increasing frustration and major data chaos. Like any challenging project pushing through to a quality outcome makes for a cool Github worthy project. Leading to a repeatable and changeable process for all kinds of bad data. Most importantly this effort renders this important public data usable for sophisticated global analysis. 

Observations on the quality of the data. 

Many of the data records were frightening, and very disturbing leaving a sense of loss and terror even with the short amount of text. This made each record important as at least a candidate for latter resolution or cross reference. The shear amount of data lead to programmatic approaches that would render the lowest error rates. The variation of the defining time values was so great that one small change in code led to wide variations in accuracy. The second unit of time was used as the normalized time value.
The locations were almost as troubling as the time variations. Some records just had a county name others distances and locations out side of known locations. The geocode accuracy will have to be manually tested for accuracy. In general, geocode latitude and longitude resolution applies if using geocode algoritims as the geocode accuracy can vary widely and can be obscured. 

Both centuries were sorted unique as well as the consolidation. The scrubbed set has only unique records free from zero normalized time and blank locations.  The locations can still be erroneous
as even the best location services may have an additive error. 

At first glance the quality looks pretty good for the geocoded data given the number of records and the nature of the original location data. With 80,000 plus records some good probabilities can be delineated regardless of the conversion errors. There was great contemplation with respect to the errors 

The Data Set

file:> ufo-complete-geocoded-time-normalized.csv

Complete original data set containing both resolved and unresolved locations and converted and not converted normalized time to seconds.
88874 total records, 724 locations not found or blank (0.8146%), 7131 erroneous time or blank (8.0237%)

file:> ufo-scrubbed-geocode-time-normalized.csv

Scrubbed data set with only non zero resolved locations and >0 normalized time. 
81185 total records, 0 locations not found, 0 erroneous time or blank records. 

The conversion process

The NUFORC data uses two digit years on all the dates so as time progresses into the 21st century the older data may become more obscured with potential error.  Therefore the data sets are broken into two sets.  20Th century and 21st century.  Many of the early 20th century cases were added in the early 21st century. The time/data set separation can also make things easier going forward.

The whole experience was an exercise in regular expressions. A general feedback technique of scrub until the data gets to a point where what is left can be cataloged and/or converted semi manually in a catalog or dictionary for value pair lookup resolution. These files are in the time-format.txt and the leftoverlocations.csv respectivly. The remaining slurry was considered unuseable.

For the geocode conversion, the generally available files at opengeocode.org; maxmind.com/en/worldcities worldcities.csv us-citylatlng.csv, and us-state-countylatlng.csv data sets.  The left over locations were run through findlattitudelongitude.com in batch mode then used as a dictionary to match one or more locations.

For the time conversions, classic minutes, seconds and combinations of these were first converted in classic fashion.  Then a dictionary lookup based on a semi manual conversion. There were so many different combinations of numbers and formats for the the time and durations that there is a general possibility of error. The sensitivity of the time conversion regular expressions cannot be over emphasized as one simple change can render instant chaos.  The simple reason is the vast amount of diverse formats for time. In general MM:SS and HH:MM:SS were taken literally. As you will see there is an almost infinite combination of time formats. Seconds were used as a standard because of the resolution of our natural awareness.  The mathematics of seconds was fascinating in that regardless of the combinations all the second calculations came out as whole numbers.  The time-convert.awk was rewritten many different ways because of the general error factor with the latest version rendering the best result. The process was one of an increasing and decreasing ebb and flow of sophisticated regular expressions and substitutions making this a fun and rewarding project.

As our future challenges as a species may include our personal perspectives on intelligence, life, society and living on this and other worlds. An inter dimensional or inter stellar contact in this context is priceless and could change personal and societal perspectives/values. To hold down the human spirit has taught us repeatedly that truth of some kind will eventually pervade. Thank you Github!

Sigmond Axel 6/21/2014

