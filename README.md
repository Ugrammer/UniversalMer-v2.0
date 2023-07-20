# Universal-Mer
  This is a command line tool for k-mer counting with all possible sizes of k at once.
# Overview
<p>Universal-Mer is the k-mer counting tool for all possible size of k at once. The program can summarize the counting result of  1-mer to l-mer exactly where l = the length of longest repeated substring in the input sequence which now is set the maximum length to 100000-mers. The program exactly report the number of all repeat (freq>1) and unique(freq = 1) mers without cutting off any low frequency mers. </p>  
<p>The Input file can be text or fasta format.The input alphabet now is only {A, C, G, T}. After counting and building database of all possible length k of k-mer completed, A user can choose any size of k to count histogram, dump k-mer, query a substring, and summarize all possible k.</p>
<p>The option of canonical form counting can be chosen in the program menu. The canonical k-mer form counting may require a quite more time than the ordinary form. The time and memory for building database depend on the length of input sequence (m) and  the longest repeated substring in the sequence (n), which are in O(mn). In the experiment of our work, with CPU apple M1, RAM 16 GB, the program used 30 GB of memory and 2000 - 2500 seconds for building the database from the input sequence 200 million bp(Fragaria vesca). From this database, the program can summarize the number of distinct repeat and unique substrings of 1-mer to 4715-mer in 24 seconds.</p>
<p>The program is suitable for the work that want to count several large k of k-mers and see the overview of the number of distinct repeat and unique for all possible size of k-mers.</p>

# REQUIREMENT
  **OS:** Windows10, MacOS_ARM64, MacOS_X64 <br>
  **RAM:** 8-64 GB, depend on the large size of the input sequence, approximately 32 GB for 200 million bp up. <br>
  
# NAME :
  UniversalMer -The k-mer counting tool for all possible size of k at once. 

# SYNOPSIS: 
  UniversalMer [OPTIONS][FILE]

# DESCRIPTION:
        -b FILE : to build new Universal-mer database with an input file (FILE).
        -l  FILE : to load Universal-mer database from FILE. (xxx.Umer) or (xxx.umer) 
        -h : to see how to use the program

  If option is -b  FILE must be a text file or a fasta format file.<br>
  If option is -l  FILE must be a universal-mer database file with the extension '.umer' or '.Umer'. <br>
  If there is no argument, program will search for database file (Universal_merDB.umer) in the same folder with the program.<br>
  After already build or load database, you can follow the instruction of the program to choose menu. <br>

# HOW TO USE THE PROGRAM:
   Go to the directory of the executable file at  /bin/MacOs/UniversalMer.  <br>
   If there is no database file, run the program to first count all possible k-mers by.
   
       % ./UniversalMer -b  /input/xxx.fasta
      
   The program will build the database of all possible size k-mer.
   After building database completed, you can choose the menu of the program. If the database already exist, you can run the program for the next time by
   
       % ./UniversalMer -l  Universal_merDB.umer

  ! Please don't forget to backup the database file for using in the next time. If not, the file will be deleted when you create a new one.

# Example
  * The running program pics place in the folder /Output/ <br>
  * The example of database file and input sequence file place in the folder /Example/ <br>
  * The DNA input sequence used in the experiment of our work place in the folder /input/ <br>

# BASIC OF UNIVERSAL MER CODING
  If you want to study the basic of Universal mer please visit at
  
  coming soon

# Author
   Jittakorn Pullpothong, Department of computer engineering, Faculty of engineering, Ramkhamhaeng University, Thailand.


   
