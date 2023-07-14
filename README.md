# Universal-Mer
  This is a command line k-mer counting tool for all possible sizes of k at once.
# Overview
  Universal-Mer is a k-mer counting tool for all possible size of k at once. It can summarize the counting result of 1-mer to l-mer where l = the length of longest repeated substring occuring in the input sequence. The Input file can be .txt or fasta format. The input alphabet now is only {A, C, G, T}. After counting and building database of all possible length k of k-mer completed, users can choose any size of k to count histogram, or dump k-mer as they want. The canonical k-mer form may require a quite more time to count than ordinary form. The time complexity depends on the longest repeated substring in the sequence.
  
# NAME :
  UniversalMer -The k-mer counting tool for all possible size of k at once. 

# SYNOPSIS: 
  UniversalMer [OPTIONS][FILE]

# DESCRIPTION:
        -b FILE : to build new Universal-mer database with an input file (FILE).
        -l  FILE : to load Universal-mer database from FILE. (xxx.Umer) or (xxx.umer) 

  If option is -b  FILE must be a text file or a fasta format file.
  If option is -l  FILE must be a universal-mer database file with the extension '.umer' or '.Umer' 
  If there is no argument, program will search for database file (Universal_merDB.umer) in the same folder with the program.
  After already build or load database, you can follow the instruction of the program to choose menu. 

 
# NOTE:
  This program is suitable for a single complete sequence with fasta format.
  A text file will be concern as fasta format without a description of the sequence.
  The program now concern only alphabet {A, C, G, T}. However,undetermine characters 'N' will be deleted and split the rest to  a new string, for example   xxxNNNNyyy will be replaced by  xxx and yyy 
  The universal-mer database store k-mers for all possible size k.
  For convenient, after building database completed, user can use option -l xxx.umer instead of -b xxx.fasta 

  The default database name is Universal_merDB.umer. If you want to use it later, please rename or backup it before building a new database  The program convert a FASTA format file to a single length string before processing
  If you want to use the program for multiple strings and  multiple files, we suggest that: combine them to a single file using description sign < for each string

  EXAMPLE:
   FILE1:
   <
   ACGCCTGTGCCCACG
   FILE2:
   <
   CCGGGTTTATC
   
   NEWFILE1_2: 
   <
   ACGCCTGTGCCCACG 
   <
   CCGGGTTTATC 


#LIMITATION:
   The maximum size of repeat substrings is set to 500000
   The maximum size of database is set to 4294967295 records.
   If the maximum size database is not enough, we recommend to split the file into shorter size   The maximum length of input is set to 4294967295 bp including newline character 
   The memory usage can varied upon the length of input sequence and the length of their repeated substrings.
   The time usage can varied upon sufficient memory and cpu speed
