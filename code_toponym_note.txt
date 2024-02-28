# Installation
install.packages("devtools")  # installs package “devtools”
library ("devtools")  # loads package “devtools”
install_github("Lennart05/toponym")  # installs package “toponym”
library("toponym")  # loads package “toponym”

# Create a simple map
country("DE")
country("country table")
help(regex)  # to get an introduction to regular expressions
top("by$", c("GB", "IE"))  # creates Figure 1
# verify that the name Baldersby but not Dunbyrne are among the hits
sort(data_by$name)
top("by", c("GB", "IE"))  # remove the dollar sign
# verify that both of the names Baldersby and Dunbyrne are among the hits
grep("Baldersby", data_ham$name)
grep("Dunbyrne", data_ham$name)
top("by$", "IE")  # trailing string -by in Ireland only

# More on the top() function
top(countries=c("GB", "IE"), strings="by$")  # other order of parameters
help(top)  # get info on the top() function
top("by$", c("GB", "IE"), color="blue", regions=1, csv=TRUE)
top(strings="^Влад", countries="RU")
top(strings="^Vlad", countries="RU", column="alternatenames")

# Finding frequent toponym strings
topFreq(countries="US", len=5, limit=24, type="$", feat.class="H")
topFreq(countries="BE", len=5, type="^", limit=8, polygon=flanders_polygon)

# Defining a polygon
p <- createPolygon("ID")  # this will require defining a polygon through clicks
country("MX", regions = 1)
Chi <- createPolygon(countries="MX", region_name="Chihuahua", retrieve=TRUE)

# Strings specific to a region
topComp(countries="GB", len=2, rat=.7, limit=100, polygon=danelaw_polygon)
topCompOut(countries="GB", len=2, rat=.7, limit=100, polygon=danelaw_polygon)
# exloring cases of -thorpe
length(data_pe$name)
length(grep("thorpe", data_pe$name))
thorpe <- data_pe[grep("thorpe", data_pe$name),]
mapper(thorpe)
topComp(countries="GB", limit=100, len=5, rat=.5, polygon=danelaw_polygon)
topZtest(strings="stead$", countries="GB",polygon=danelaw_polygon)

# Other functions
getData(countries=c("DE", "GB"))  # example of updating downloaded data
# examples of lists of symbols and their frequencies, here for Thailand
ortho(countries="TH", column="name")  # 
ortho(countries="TH", column="alternatenames")  # 
