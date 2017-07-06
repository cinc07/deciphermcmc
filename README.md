Code written for Paper "Decrypting Classical Cipher Text Using Markov Chain Monte Carlo"

Link to the paper:
http://probability.ca/jeff/ftpdir/decipherart.pdf

Original page for the software:
http://probability.ca/decipher/


MCMC Decryption Software


This directory contains the software used for the simulations in the paper Decrypting Classical Cipher Text Using Markov Chain Monte Carlo by Jian Chen and Jeffrey S. Rosenthal (May 2010).


This software is licensed for general copying, distribution and modification according to the GNU General Public License.

The software is most easily run on a Unix-like computer (such as Sun, or Linux, or Mac OS X), as we now describe (though a method to run it on a Windows machine is described in the README file). You will need to have "cc" and "wget" installed. ("cc" or "gcc" is the C compiler; on Linux/Unix it should come pre-loaded, but for Mac you might need to install the Xcode package. "wget" is a simple program for downloading web files, available from e.g. here; for Mac see here and here; or you can forget wget and just use your usual web browser to download the files directly instead.)


To run the code, on Unix systems, move into that directory and compile the programs, by typing:
```
cd code
make 
cc -lm simplify.c -o simplify
```


Then download relevant texts, such as War and Peace and Oliver Twist, by typing e.g.:
```
wget http://www.gutenberg.org/files/2600/2600-0.txt -O warnpc12.txt 
wget http://www.gutenberg.org/files/730/730.txt -O olivertwist.txt
```
(or by downloading them directly using your web browser, and saving them as "warnpc12.txt" and "olivertwist.txt" respectively).


Next simplify them (remove punctures, capitalize all letters), by typing e.g.:
```
./simplify < warnpc12.txt > warorig 
./simplify < olivertwist.txt > oliverorig
```

You can then run the program, to use MCMC algorithms to repeatedly attempt to decrypt Oliver Twist (using War and Peace as the reference text), by typing:
```
./deciphermcmc
```


To learn how to modify the MCMC parameters, change the testing configuration, use different text samples, run the program on Microsoft Windows machines, and more, please see the README file in the code folder.



