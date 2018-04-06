# TV Mosaic PVR
TV Mosaic PVR client addon for [MrMC] (http://mrmc.tv)

## Build instructions

### Linux

1. `git clone https://github.com/mrmc/mrmc.git`
2. `git clone https://github.com/mrmc/pvr.tvmosaic.git`
3. `cd pvr.tvmosaic && mkdir build && cd build`
4. `cmake -DADDONS_TO_BUILD=pvr.tvmosaic -DADDON_SRC_PREFIX=../.. -DCMAKE_BUILD_TYPE=Debug -DCMAKE_INSTALL_PREFIX=../../xbmc/addons -DPACKAGE_ZIP=1 ../../xbmc/project/cmake/addons`
5. `make`

##### Useful links

* [MrMC's PVR user support] (http://forum.mrmc.tv)
* [MrMC's PVR development support] (http://forum.mrmc.tv)
