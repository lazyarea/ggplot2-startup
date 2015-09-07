ggplot2-startup

#---------------------------------------------
# install packeges
#---------------------------------------------

yum install -y epel-release

yum install -y R gdal-devel gdal-libs proj-* libxml2-devel geos-devel


#---------------------------------------------
# load plugin with R
#---------------------------------------------

$ R

> library(raster)

> library(maptools)

> library(rgdal)

> library(animation)

> library(RColorBrewer)

> library(ggplot2)

> library(rgeos)

> library(maptools)

#---------------------------------------------
# Drow Map(JPN)
#---------------------------------------------

> library(raster)

> library(maptools)

> library(ggplot2)

> ja_shp <- getData('GADM', country='JPN', level=1)

> ja_map <- fortify(ja_shp)

> ggplot(ja_map, aes(x=long, y=lat, group=group)) + geom_path(lwd=0.5)

> ggsave(filename = "ja.png", plot = last_plot())

#---------------------------------------------
# Drow Map(United Kingdom)
#---------------------------------------------

> library(raster)

> library(maptools)

> library(ggplot2)

> uk_shp <- getData('GADM', country='United Kingdom', level=1)

> uk_map <- fortify(uk_shp)

> ggplot(uk_map, aes(x=long, y=lat, group=group)) + geom_path(lwd=0.5)


#---------------------------------------------
# Height Weight
#---------------------------------------------

> install.packages("gcookbook")

> library(gcookbook)

> heightweight[, c("ageYear","heightIn")]

> ggplot(heightweight, aes(x=ageYear, y=heightIn)) + geom_point()

#---------------------------------------------
# Geo Life Data to 2D
#---------------------------------------------

1. Latitude in decimal degrees

2. Longitude in decimal degrees

3. All set to 0 for this dataset

4. Altitude in feet (-777 if not valid)

5. Date -number of days (with fractional part) that have passed since 12/30/1899.

6. Date as string.

7. Time as string.

> data <- read.csv("./data/Geolife\ Trajectories\ 1.3/Data/001/Trajectory/20081214235553.plt", skip=6)

> names(data) <- c("Latitude","Longitude","All0","feet","Date-number","Date","Time")

> ggplot(data, aes(x=Latitude, y=Longitude)) + geom_point()

#---------------------------------------------
# Geo Life Data to 3D
#---------------------------------------------

$ sudo yum install freeglut-devel -y

> install.packages("rgl")

> library(rgl)

> plot3d(data$Latitude, data$Longitude, data$feet, type="s", size=1.75, lit=FALSE)

#---------------------------------------------
# install packeges jpeg
#---------------------------------------------

$ sudo yum install -y libjpeg-turbo-devel 

> install.packages("jpeg")

> library(jpeg)



#---------------------------------------------
# install packages png
#---------------------------------------------

$ sudo yum install -y libpng12-devel libpng-devel

> install.packages("png")

> library(png)

#---------------------------------------------
# gridExtra
#---------------------------------------------

> install.package(gridExtra)

> library(ggplot2)

> library(gridExtra)

> p1 <- ggplot(ja_map, aes(x=long, y=lat, group=group)) + geom_path(lwd=0.1)

> p2 <- ggplot(data, aes(x=X,y=Y)) +  geom_point()

> grid.arrange(p1, p2, ncol = 2)

#---------------------------------------------
# 表とグラフの同時描画
#---------------------------------------------

http://stackoverflow.com/questions/11603262/outputting-a-textplot-and-qplot-in-same-pdf-or-png-in-r
