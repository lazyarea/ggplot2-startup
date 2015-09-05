ggplot2-startup

#---------------------------------------------
# install packeges
#---------------------------------------------

yum install -y epel-release
yum install -y R
yum install -y gdal-devel gdal-libs
yum install -y proj-*
yum install -y libxml2-devel
yum install -y geos-devel


#---------------------------------------------
# load plugin with R
#---------------------------------------------

library(raster)
library(maptools)
library(rgdal)
library(animation)
library(RColorBrewer)
library (ggplot2)
library(rgeos)
