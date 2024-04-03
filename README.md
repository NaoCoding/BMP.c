## BMP C Library 

#### Author : NaoCoding

#### Function Lists
```c
int READBMP(BMP * target);                    // return 0 = not BMP , return 1 = success (only headers)

void showBMPInfo(BMP * target);               // show info

void setupBMP(BMP * target, BMP * from);      // copy all header to target

void writeInHeader(BMP *target);              // write in target.source (only headers)

void BMPFree(BMP * target);                   // useless

void CallocBMP(BMP * target);                 // for callocing BMP pointer
```
#### BMP Structure ( All are pointer )
```c
file                                          // file header

info                                          // info header

path                                          // file path

source                                        // FILE * pointer

```

#### Example Code
```c
BMP *file = calloc(5,sizeof(BMP));             // calloc 5 BMP structure

for(int i=0;i<5;i++) CallocBMP(file+i)        // calloc all 5 BMP's structures' pointer

file[i].source = fopen(file[i].path,'rb')     // setup file[i].source, the path is file[i].path

READBMP(&file[i])                             // read file[i].source and copy all header information

showBMPInfo(&file[i])                         // show file[i].file and file[i].info all elements

writeInHeader(&file[i])                       // write file[i].file and file[i].info into file[i].source 
```


