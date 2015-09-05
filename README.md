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

> library (ggplot2)

> library(rgeos)
