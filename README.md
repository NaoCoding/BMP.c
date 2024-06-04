## BMP C Library 

#### Author : NaoCoding

```
This library includes general useful function for C to parse BMP file.
```

#### Function Lists
```c
BMP * iniBMP()                                // initialize BMP (calloc)

int BMPLoad(BMP * t, char * p, char * m)      // read path to source , return 1 = file found, return 0 = not found

void ARR2BMP(BMP * target, uint8_t ***arr)    // writeIn arr into a BMP file

uint8_t ***BMP2ARR(BMP *target)               // Read BMP file into an arr

int READBMP(BMP * target);                    // return 0 = not BMP , return 1 = success (only headers)

void showBMPInfo(BMP * target);               // show info

void setupBMP(BMP * target, BMP * from);      // copy all header to target

void writeInHeader(BMP *target);              // write in target.source (only headers)

void BMPFree(BMP * target);                   // free BMP

void CallocBMP(BMP * target);                 // for callocing BMP pointer

int dotBMPcheck(char * target);               // check if string is .bmp or .BMP format , return 1 = true , 0 = false
```
#### BMP Structure ( All are pointers )
```c
file                                          // file header

info                                          // info header

path                                          // file path

source                                        // FILE * pointer

```

#### Example Code
```c
BMP * n = iniBMP()                            // initialize BMP n

BMPLoad(n,"a.bmp","rb")                       // read BMP file "a.bmp" as n.path and make it to n.source

READBMP(n)                                    // read BMP *n header

uint8_t ***arr = BMP2ARR(n)                   // read BMP *n to a uint8_t[][][]

showBMPInfo(n)                                // show n.file and n.info all elements

writeInHeader(n)                              // write n.file and n.info into n.source 
```


