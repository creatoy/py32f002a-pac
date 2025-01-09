# Scripts for py32-rs
These scripts are used during development of the py32f0 crates

## comparesvd.py
Compares 2 svd's by peripheral memory address.
```
usage: comparesvd.py svdfile1 svdfile2
```

## group.py [NOT WORKING]
Generate sets of devices with peripherals in common
```
usage: group.py [-h] devices output
```

## htmlcomparesvdall.sh
Runs `htmlcomparesvd.py` on all patched svd files in svd directory. Generates a `html/comparisons.html` file.
```
usage: htmlcomparesvdall.sh
```

## htmlcomparesvd.py
Creates html pages that compare peripherals, registers, and fields given a set of svd's.
```
usage: htmlcomparesvd.py [-h] htmldir [svdfiles ...]
```

## interrupts.py
Outputs peripheral vector number, interrupt name, and description from a svd
```
usage: interrupts.py [-h] outdir [svdfiles ...]
```

## makecrates.py
Script that builds the rust crates.
```
usage: makecrates.py [-h] [-y] [--families FAMILY [FAMILY ...]] devices
```

## makehtml.py
Generates a webpage for a given SVD file containing details on every
peripheral and register and their level of coverage.
```
usage: makehtml.py [-h] htmldir [svdfiles ...]
```

## makejson.py [NOT WORKING]
Transforms the given SVD files into a JSON format more suited for
web pages.
```
usage: makejson.py [-h] htmldir [svdfiles ...]
```

## matchperipherals.py [NOT WORKING]

## periphtemplate.py
Prints out a basic yaml template of a peripheral in svdfile.
```
usage: periphtemplate.py [-h] svdfile peripheral yamlfile
```

## svdmmap.py
Outputs a peripheral memory map of the device in a svd file
usage:
```
python3 svdmmap.py <svd_file>
```
Example output (partial)
```
0x40000000 A PERIPHERAL TIM2
0x40000000 B  REGISTER CR1: desc CR1
0x40000000 C   FIELD 00w01 CEN: desc CEN
0x40000000 C   FIELD 01w01 UDIS: desc UDIS
0x40000000 C   FIELD 02w01 URS: desc URS
0x40000000 C   FIELD 03w01 OPM: desc OPM
0x40000000 C   FIELD 04w01 DIR: desc DIR
0x40000000 C   FIELD 05w02 CMS: desc CMS
0x40000000 C   FIELD 07w01 ARPE: desc ARPE
0x40000000 C   FIELD 08w02 CKD: desc CKD
0x40000004 B  REGISTER CR2: desc CR2
0x40000004 C   FIELD 03w01 CCDS: desc CCDS
0x40000004 C   FIELD 04w03 MMS: desc MMS
0x40000004 C   FIELD 07w01 TI1S: desc TI1S
...
```

## timer_hierarchy.py
Prints the timer peripherals common registers and fields for the device in a svd file
```
usage: timer_hierarchy.py [-h] svdfile
```

## tool_install.sh
Installs the tools required to generate the rust crates for this device family. The script will download and install
the specific version of the tools needed.

## HTML Templates
Used in `makehtml.py` and `makejson.py`

 - makehtml.index.template.html
 - makehtml.template.html
 - viewgroups.html
