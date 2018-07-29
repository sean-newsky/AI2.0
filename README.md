# Build Instructions

Step 0: Download snort-2.9.11.1 tarball from snort.org and unzip the tarball

```bash
tar xzvf snort-2.9.11.1.tar.gz
```

Step 1: Enter the extracted snort source directory
```bash
cd snort-2.9.11.1
```

Step 2: build the snort
```bash
./configure
./make
./make install
```

Step 3: copy minipiggy folder into snort-2.9.11.1/src/ and unizip it
```bash
cp minipiggy.zip snort-2.9.11.1/src
unzip minipyggy.zip
```

Step 4: enter the minipiggy directory
```bash
cd src/minipiggy
```

Step 5: build and install the library
```bash
make
make install
```

## Generate SO rules

Step 1: edit snort.conf to uncomment dynamicdetection directory
Step 2  change directory into the lib path where the snort binary is installed
Step 3: snort -c ~/opt/config/etc/snort.conf --dump-dynamic-rules=/so_rules_path
Step 4: add the following line to snort.conf

#dynamic library rules
include $SO_RULE_PATH/Newsky_AI_LIB.rules

## Ruuning

Now you're ready to run the snort with the newsky plugin library.


