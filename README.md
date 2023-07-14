# Universal-Mer
  This is a command line k-mer counting tool for all possible sizes of k at once.
# Overview
  Universal-Mer is a k-mer counting tool for all possible size of k at once. It can summarize the counting result of 1-mer to l-mer where l = the length of longest repeated substring occuring in the input sequence. The Input file can be .txt or fasta format. The input alphabet now is only {A, C, G, T}. After counting and building database of all possible length k of k-mer completed, users can choose any size of k to count histogram, or dump k-mer as they want. The canonical k-mer form may require a quite more time to count than ordinary form. The time for building database depends on the longest repeated substring in the sequence.
  
# NAME :
  UniversalMer -The k-mer counting tool for all possible size of k at once. 

# SYNOPSIS: 
  UniversalMer [OPTIONS][FILE]

# DESCRIPTION:
        -b FILE : to build new Universal-mer database with an input file (FILE).
        -l  FILE : to load Universal-mer database from FILE. (xxx.Umer) or (xxx.umer) 
        -h : to see how to use the program

  If option is -b  FILE must be a text file or a fasta format file.
  If option is -l  FILE must be a universal-mer database file with the extension '.umer' or '.Umer'. 
  If there is no argument, program will search for database file (Universal_merDB.umer) in the same folder with the program.
  After already build or load database, you can follow the instruction of the program to choose menu. 

# HOW TO USE THE PROGRAM:
   Go to the directory of a file  /bin/MacOs/UniversalMer.  
   If there is no database file, run the program. 
      -% ./UniversalMer -b  /input/xxx.fasta
   The program will build the database of all possible size k-mer as shown by a pic in the directory output.Then a user can choose a menu of program.
   After a database already exist in the same folder of the program, a user can run a program by
     -% ./UniversalMer -l Universal_merDB.umer

   
