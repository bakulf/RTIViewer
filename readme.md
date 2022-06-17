# RTIViewer

This software is available under the Gnu General Public License version 3.

This tool, designed for cultural heritage and natural science application, was
primarily developed by the Italian National Research Council's (CNR) Institute
for Information Science and Technology's (ISTI) Visual Computing Laboratory
(http://vcg.isti.cnr.it). The work was financed by Cultural Heritage Imaging
with majority funding from the US Institute of Museum and Library Services'
(IMLS) and National Leadership Grant Program (award number LG-25-06-010706).
RTIViewer also contains significant software and design contributions from the
University of California at Santa Cruz; the Universities do Minho in Portugal;
Tom Malzbender, formerly of HP Labs; and Cultural Heritage Imaging.

The updated 1.1 version of the RTIViewer software and User Guide was partially
funded by a 21st Century Museum Professionals grant from the IMLS, along with
volunter efforts and private contributions. The Bookmarks feature added in the
1.1 release is based on work done by Leif Isaksen of the University of
Southampton, UK. We would especially like to acknowledge the work of Ronald
Bourret and Gianpaolo Palma for the development work for this release.

[More Info](http://culturalheritageimaging.org/What_We_Offer/Downloads/View/)

## How to compile RTIViewer

To compile RTIViewer you need a C++ compiling environment and the following
libraries:

- Qt 5
- QtHttp Addon
- the VCG libraries

The compiling steps depends on the compiling environment. The following instruction is based on Ubuntu 20.04 LTS.

### Step 1: Install Qt 5
```bash
sudo apt install qt5-default
```
you can check [the official website instructions](https://wiki.qt.io/Install_Qt_5_on_Ubuntu) for more info.

### Step 2: Install QtHttp Addon
The QtHttp class is not public in Qt 5. Thus it must be installed as an addon.

```bash
git clone https://code.qt.io/cgit/qt/qthttp.git/
cd qthttp/
qmake
make -j8
sudo make install
```
### Step 3: Build RTIViewer
```bash
git clone https://github.com/mobinseven/RTIViewer.git
git submodule init
git submodule update
qmake -recursive rtiviewerv10.pro
make release -j8
```
If all goes well the RTIViewer can run with this command:
```
./rtiviewer/src/bin/RTIViewer
```
