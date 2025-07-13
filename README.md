# UniversalMer
  A k-mer counting tool for multiple sizes of k at once.
# OVERVIEW
UniversalMer is a k-mer counting tool for multiple size of k at once.The program counts and summarizes the exact frequency of all k-mers from 1-mer to a user-defined maximum length (kmax). This kmax can be specified as any length or can be automatically determined by the longest repeated patterns found in the input sequence.
The available sequence alphabets support are DNA, RNA, and protein. The Input file must be fasta format with .txt or .fasta or .fna. 

## The program offers several output options:
 * Dumping all k-mers: Outputs a complete list of every k-mer found.
 * Dumping chosen k-mer patterns: Provides lists of repeated or singleton k-mers.
 * Dumping the k-mer spectrum: Generates a summary of k-mer frequencies.
 * Note: The program does not support canonical k-mer counting. You can use the output files with other programs to find canonical patterns. 

## The efficiency of the program depends on the sequence length (in base pairs) and the number of unique patterns.

## Memory Usage:
 * For an input sequence of 6 million base pairs, generating 1 billion patterns with a maximum k-mer length of 20,000, the memory usage is approximately 70-80 GB.
 * For shorter input lengths ranging from 20,000 to 1 million base pairs, the memory usage is much lower, from 8 MB to 150 MB, for 20 thousand to 1.5 million patterns with a maximum k-mer length of 30 to 300.    
    
## Running Time:
 * Based on our experiments, for an input length of 6 million base pairs, which yields 1 billion patterns with a maximum k-mer size of 20,000, the running time is approximately 4500-5000 seconds.
 * For smaller inputs (20,000 to 1 million base pairs) generating 20 thousand to 1.5 million patterns with the maximum k-mer sizes of 30 to 300, the running time ranges from 100 milliseconds to 6 seconds.

# REQUIREMENT
  **OS:** Windows10, MacOS_ARM64, MacOS_X64 <br>
  **RAM:** 8-64 GB, depend on the large size of the input sequence and output patterns. We recommend RAM 32 GB for 200 million bp up. <br>
  
# NAME :
  UniversalMer -The k-mer counting tool for multiple sizes of k at once. 

# SYNOPSIS: 
   universalmer [OPTIONS][FILE][DUMP][K-SIZE]

# DESCRIPTION:

 [OPTIONS]: For specifying maximum k and alphabet

        -k<maximum lenght> : Example: -k100 for maximum k length = 100 (counting 1-mers to 100-mers)
        -a<alphabet> : -ad for DNA alphabet = {A,C,G,T}
                       -ar for RNA alphabet = {A,C,G,U}
                       -ap for protein alphabet =  {A,C,D,E,F,G,H,I,K,L,M,N,P,Q,R,S,T,V,W,Y}
        -n : For not saving output file 
        -t : For count and saving spectrum file
        -m<minimum frequency>: Example: -m100 for minimum frequency = 100

    [FILE]: To specify an input path, use a file with  .fasta, .fna, or .txt extension that is in FASTA format.

    [DUMP]: For specifying whether or not to dump singleton patterns.
            -d<type>:   
                  -d  :  Dump repeats and singleton k-mers
                  -dx :  Dump only repeats k-mer, excluding singleton k-mers

    [K-SIZE]:Here is how to specify the size of k for dumping:
          Range of k's: Use a hyphen to define a range (e.g., 10-100).
          Multiple k's: Separate each size with a space (e.g., 28 38 55 65).
          Single k: Simply enter one value (e.g., 55).

## EXAMPLE:   
 * universalmer -k250 -ad dna1.fasta -dx 28-100 
 * universalmer -k250 -ap protein1.fasta -d 28 55 100 230 
 * universalmer -k150 -ar rna1.fasta -dx 55
 * universalmer -k100 -n dna2.fasta -d 55
 * universalmer -k55 dna3.fasta
 * universalmer -k55 -m20 dna3.fasta

## NOTE: 
 * Output Location: All output files will be created in the same folder as the executable file.
 * Alphabet: The default alphabet is DNA. To specify a different one, use the -a flag (e.g., -ap).
 * Spectrum Dumping: By default, the program will dump the spectrum for all k-mer sizes up to the maximum. This is equivalent to using the -dx 1-maximumk command.
 * Minimum Frequency: The default minimum frequency is 2. If you set this to a higher value, singleton patterns will not be included in the output.
 * Saving Spectrum Files: To save a spectrum file, you must use the -t flag in conjunction with the -d flag to select the k-mer spectrum.
 * Help: For more information and a full list of commands, use -h or -help.

# HOW TO USE THE PROGRAM

 * Go to the directory of the executable file at  /bin/MacOs/UniversalMer
 * Assume that the input file is in directory /input/xxx.fasta
 * run command
   
       % ./UniversalMer -k1000 -n /input/xxx.fasta

   The program will count k-mers of k = 1 to 1000 from xxx.fasta without save patterns file.
   
   CAUTION: Please be mindful of the number of singleton patterns before proceeding with the dump. For some chosen values of k, the output file size could exceed 10 GB.

# OUTPUT

Your program will save the output files in the same folder as the executable file.  The output files are:
 * Allrepeatspattern.csv: Contains all patterns of 1-mers to the maximum k-mer size (kmax).
 * repeatsPatterns.csv: Contains repeat patterns for the user-specified range of m-mers to n-mers.
 * singletonPatterns.csv: Contains singleton patterns for the user-specified range of m-mers to n-mers.
 * kmersspectrum.csv: Contains spectrum information for the user-specified range of m-mers to n-mers.
 * Note: If you use the -m flag to define a minimum frequency greater than 2, the singleton pattern dumping will not be active.
    
# EXAMPLE
 * The running program pics place in the folder /Output/ 
 * The list of DNA input sequence used in the experiment of our work place in the folder /Example/input/ 

# BASIC OF UNIVERSALMER CODING
  If you want to study the basic of Universal mer please visit at..<br>
  ..coming soon..
  
# LICENSE
  ! YOU may install and use an unlimited number of copies for personal and education use.<br>
  ! YOU may not sell, decompile, disassemble, reverse engineer or modify this program.<br>

# AUTHOR

  **Jittakorn Pullpothong**<br> Department of computer engineering, Faculty of engineering, Ramkhamhaeng University, Thailand.<br>
  Email: <jittakorn.p@rumail.ru.ac.th>
