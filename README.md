# Peace Corps Languages

The Peace Corps Languages API has languages that Peace Corps teaches (and has taught in the past), as well as the country where that language is taught. This data is also available as a [CSV file](https://github.com/PeaceCorps/peacecorpslanguages/raw/master/data/peacecorpslanguages.csv).  

*Please note that the inclusion of any geographical area in this data set is based solely on data availability and convenience for possible users. Our choice of names for any of the included countries and territories is likewise made solely for the convenience of users. Neither this nor the inclusion/exclusion of a specific country or territory implies a stated opinion of Peace Corps regarding the legal or political status of the geographical area in question. Neither do the names imply a stated opinion of Peace Corps or the U.S. Government on the correct naming of an entity.*

####Data Definitions
`Region` Peace Corps Region code (AF, EMA, IAP)  
`Post` Name of the Country  
`Language Name` Name of Language

###API Approach
As a proof-of-concept for the value of APIs - it is far easier to use existing public spreadsheet data (XLS or CSV) in its existing form than to build machine translators. The approach here has been to use [Project Open Data](http://project-open-data.github.io/)'s '[csv-to-api](https://github.com/project-open-data/csv-to-api)' to generate a RESTful API from the static OBS CSV data.

###Using the PeaceCorpsLanguages API

####Arguments

* `source`: the URL to the source CSV
* `source_format`: if the url does not end in `.csv`, you should specify 'csv' here (to facilitate future functionality)
* `format`: the requested return format, either `json`, `xml`, or `html` (default `json`)
* `callback`: if JSON, an optional JSONP callback
* `sort`: field to sort by (optional)
* `sort_dir`: direction to sort, either `asc` or `desc` (default `asc`)
* any field(s): may pass any fields as a key/value pair to filter by that field

####Example Usage

**Get CSV as JSON** (default behavior)  
http://labs.data.gov/csv-to-api/?source=https://raw.github.com/PeaceCorps/peacecorpslanguages/master/data/peacecorpslanguages.csv

**Get results as XML**  
http://labs.data.gov/csv-to-api/?source=https://raw.github.com/PeaceCorps/peacecorpslanguages/master/data/peacecorpslanguages.csv&format=xml

**Get results as JSONP**  
http://labs.data.gov/csv-to-api/?source=https://raw.github.com/PeaceCorps/peacecorpslanguages/master/data/peacecorpslanguages.csv&format=json&callback=parse_results

**Get results as HTML**  
http://labs.data.gov/csv-to-api/?source=https://raw.github.com/PeaceCorps/peacecorpslanguages/master/data/peacecorpslanguages.csv&format=html


##### Sort by a field
 * Sort by Region (HTML) (ascending)  
http://labs.data.gov/csv-to-api/?source=https://raw.github.com/PeaceCorps/peacecorpslanguages/master/data/peacecorpslanguages.csv&format=html&sort=Region&sort_dir=asc

 * Sort by Language Name (HTML) (descending)  
http://labs.data.gov/csv-to-api/?source=https://raw.github.com/PeaceCorps/peacecorpslanguages/master/data/peacecorpslanguages.csv&format=html&sort=Language%20Name&sort_dir=desc

##### Filter by a field
 * [Filter by Country - Madagascar (HTML)  
http://labs.data.gov/csv-to-api/?source=https://raw.github.com/PeaceCorps/peacecorpslanguages/master/data/peacecorpslanguages.csv&format=html&Post=Madagascar

###Usage
License is GPLv3 or later.
