# gdalwheels
Because we all want to just
```bash
pip install gdal
```

But there are no GDAL binary wheels on pypi.

This repo is a collection of GDAL binary wheels. The files are from different sources so Windows and Linux wheels may for instance not exist for the same GDAL versions and they may have different drivers compiled in.

## Howto

Go to [releases](//github.com/AsgerPetersen/gdalwheels/releases) and find the file which fits your python version and operating system.

The naming convention is as follows:
`GDAL-{GDAL-version}-{python tag}-{abi tag}-{platform tag}.whl`

So, if you are using Python 2.7 32bit on windows, you are looking for files ending in `cp27-cp27m-win32.whl`.

When you have found a suitable file (let's say it is `GDAL-2.2.4-cp27-cp27m-win32.whl`), then you can install it directly with pip using the URL:
```bash
pip install https://github.com/AsgerPetersen/gdalwheels/releases/download/2.2.4_1/GDAL-2.2.4-cp27-cp27m-win32.whl
```
Please see platform specific notes below.

## Linux
I have made linux wheels using the project [gdalmanylinux](https://github.com/youngpm/gdalmanylinux).

## Windows
All wheels are taken from Christoph Gohlke's excellent [collection](https://www.lfd.uci.edu/~gohlke/pythonlibs/) of python packages compiled for windows. As such all Christoph's comments applies to the windows wheels in this repository:

> This distribution includes a complete GDAL installation. Do not use together with OSGeo4W or gdalwin32.
Built with KML, HDF5, NetCDF, SpatiaLite, PostGIS, GEOS, PROJ.4 etc.
The FileGDB plugin requires Esri's FileGDB API 1.3 or FileGDB 1.5 VS2015 or VS2010.
Requires VCredist SP1 on Python 2.7.

And

> Many binaries depend on numpy-1.15+mkl and the Microsoft Visual C++ 2008 ([x64](https://www.microsoft.com/en-us/download/details.aspx?id=15336), [x86](https://www.microsoft.com/en-us/download/details.aspx?id=29), and [SP1](https://www.microsoft.com/en-us/download/details.aspx?id=26368) for Python 2.7) or the Visual C++ 2017 ([x64 or x86](https://support.microsoft.com/en-us/help/2977003/the-latest-supported-visual-c-downloads) for Python 3.x) redistributable packages.

> The binaries are compatible with the most recent official CPython distributions on Windows >=6.0. Chances are they do not work with custom Python distributions included with Blender, Maya, ArcGIS, OSGeo4W, ABAQUS, Cygwin, Pythonxy, Canopy, EPD, Anaconda, WinPython etc. Many binaries are not compatible with Windows XP or Wine.

The reason for copying the wheels from Christophs site to this repository is that Christoph states: _"Please only download files manually as needed."_

## OSX
Haven't figured this one out yet.

