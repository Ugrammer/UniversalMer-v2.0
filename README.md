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

    [FILE]: For specifying an input path
            Use a filename.fasta or .fna or .txt with fasta format

    [DUMP]: For specifying dumping with singletons or not
            -d<type>:   
                  -d  :  Dump repeats and singleton k-mers
                  -dx :  Dump only repeats k-mer without singleton k-mers

    [K-SIZE]:For specifying the size of k for dumping
             Range of k's : Use '-' for a range of k such as 10-100
             Multiple k's : Use space between each size such as 28 38 55 65 
             A Single k   : Use only one k for a single size such as 55

## EXAMPLE:   
 * universalmer -k250 -ad dna1.fasta -dx 28-100 
 * universalmer -k250 -ap protein1.fasta -d 28 55 100 230 
 * universalmer -k150 -ar rna1.fasta -dx 55
 * universalmer -k100 -n dna2.fasta -d 55
 * universalmer -k55 dna3.fasta
 * universalmer -k55 -m20 dna3.fasta

## NOTE: 
 * The output will be created in the same folder of the executable file
 * If -a<alphabet> is not specified, the default alphabet will be DNA alphabet  
 * If -d, -dx is not specified,  the default will be as -dx 1-maximumk
 * Minimum frequency is 2 by default. If it is more than 2 the singletons won't be counted
 * Save spectrum file -t must be used together with -d to choose k spectrum
 * Use universal -h or -help for help

# HOW TO USE THE PROGRAM

 * Go to the directory of the executable file at  /bin/MacOs/UniversalMer. 
 *  Assume that the input file is in directory /input/xxx.fasta
 *  run command
   
       % ./UniversalMer -k1000 -n /input/xxx.fasta
      
   The program will count k-mers of k = 1 to 1000 from xxx.fasta without save patterns file. 
   CAUTION: Please concern the number of singleton patterns before dumping. Some chosen k may consume 10 GB up.

# OUTPUT
  * The program will save output files in the same folder with the executable file.
  * Allrepeatspattern.csv is the file of all patterns of 1-mers to kmax-mers.
  * repeatsPatterns.csv is the file of repeat patterns of m-mers to n-mers as specified by user.
  * singletonPatterns.csv is the file of singleton patterns of m-mer to n-mers as specified by user.
  * kmersspectrum.csv is the file of spectrum information of m-mer to n-mers as specified by user.
  * Note: if you choose -m to define minimum frequency > 2, the singleton pattern dumping will not be active.
    
# EXAMPLE
  * The running program pics place in the folder /Output/ <br>
  * The list of DNA input sequence used in the experiment of our work place in the folder /input/ <br>

# BASIC OF UNIVERSALMER CODING
  If you want to study the basic of Universal mer please visit at..<br>
  ..coming soon..
  
# LICENSE
  ! YOU may install and use an unlimited number of copies for personal and education use.<br>
  ! YOU may not sell, decompile, disassemble, reverse engineer or modify this program.<br>

# AUTHOR

  **Jittakorn Pullpothong**<br> Department of computer engineering, Faculty of engineering, Ramkhamhaeng University, Thailand.<br>
  Email: <jittakorn.p@rumail.ru.ac.th>
