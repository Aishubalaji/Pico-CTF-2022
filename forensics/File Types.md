### THE CHALlENGE:
```
This file was found among some files marked confidential but my pdf reader cannot read it, maybe yours can. 
You can download the file from here(https://artifacts.picoctf.net/c/329/Flag.pdf) .
```

We are given a pdf named Flag.pdf.

First let's check the file type
```
$ file Flag.pdf 
Flag.pdf: shell archive text
```
It is a shell archive text

After googling about shell archive text, it seems we can execute it like a shell script
```
$ chmod +x Flag.pdf 
$ ./Flag.pdf 
x - created lock directory _sh00046.
x - extracting flag (text)
./Flag.pdf: 119: uudecode: not found
restore of flag failed
flag: MD5 check failed
x - removed lock directory _sh00046.
```
We get an error: `uudecode: not found`

After googling about uudecode, uudecode is a tool that is present in **sharutils**.

So let's install sharutils

`sudo apt-get install sharutils`

We can now run the file without any errors
```
$ ./Flag.pdf 
x - created lock directory _sh00046.
x - extracting flag (text)
x - removed lock directory _sh00046.
```
The shell archive text has created a file **flag**

Let's check its file type
```
$ file flag 
flag: current ar archive
```
It is an ar archive

In this challenge you will encounter many types of archive. Google on how to decompress the archive and proceed

Dont forget to check the file type at each step

Good Luck!!

At last you will get a text file that contains the flag in hex encoded

**Flag:** picoCTF{f1len@m3_m@n1pul@t10n_f0r_0b2cur17y_278f1a18}

Challenge link in Pico Gym: https://play.picoctf.org/practice/challenge/265?category=4&originalEvent=70&page=1&search
