README
# numerical_analysis

Contact Sarah Flanagan (spflanagan.phd@gmail.com) for more information.

It assumes a population size of 1000 individuals per deme, 2000 replications (genes), and 5000 generations.
50 individuals are sampled from each sampled populations.
Sampling either occurs as a certain number of samples per population or by randomly-sampling populations (a single population could be sampled multiple times).

### Input

#### Required parameters
* Base output file name, including the path
* Nm (population size = 1000 times the migration rate)
* The number of demes
* The number of populations to sample

#### Optional parameters
* Whether random sampling is turned on or off. (Default: random sampling turned on)
* If you want to run it with overdominance, and the overdominance selection coefficient (default: no overdominance)
* If you want to run it with directional selection, and the selection coefficient (default: no directional selection)


#### Arguments:
-o	base file name (include path). Example: N1000_s10_
-p	Population size (N). This number is set to 1000 if not specified and is constant among all populations.
-n	Nm
-d	number of demes
-r	random sample? In interactive mode, use Y to turn on and N to turn off. In command-line mode, use 1 to turn on.
-s	number of populations to sample
-v	Overdominance? Follow -v with the selection coefficient (s)
-ds	Directional Selection?  Follow -ds with the selection coefficient (s)
-h	Prints the arguments list
no arguments:	interactive mode

### Output
* Average Allele frequencies, Fsts, etc. for each generation (*.freqs.txt).
* Heterozygosities, Fsts, and average allele frequency for all demes (not the sampled populations) for each locus at the end of the 5000 generations (*.output.txt).
* Heterozygosities, Fsts, and average allele frequency calculated from the sampled populations (whether populations were randomly sampled or not) for each locus (*.sampledpops.txt).
* Genepop file for the sampled output, ready to be input to LOSITAN.


### Installation and Usage
#### Windows
Put the executable (numerical_analysis.exe) in a useful folder. It is easiest (the path you must provide is shortest) if you put it in your desired output directory.

#### Ubuntu
Put the executable in a useful folder. It is easiest (the path you must provide is shortest) if you put it in your desired output directory.
**You may need to alter file permissions for it to run:
chmod u+x numerical_analysis

To run the file in interactive mode: 
./numerical_analysis

To run the file with arguments:
./numerical_analysis -o file_name_base_ -n 0.1 -d 100 -s 10 -r y

For help:
./numerical_analysis -h 

#### Other operating systems
Compile the source code using the g++ compiler.
For example:
g++ numerical_analysis.cpp -o numerical_analysis -std=c++0x
Note: This program has not been tested on any platforms other than Windows and Ubuntu.


