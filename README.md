# UNIVERSAL-MER
  This is a command line tool for k-mer counting with all possible sizes of k at once.
# OVERVIEW
<p>Universal-Mer is a k-mer counting tool for all possible size of k at once. More than typical k-mer counting tools, the program can summarize the exact counting result of  1-mers to  l-mers at once where l = the length of longest repeated substring in an input sequence where the maximum length now is set to 100000-mers. In the case k > l, all of k-mers surely occur only once in the input so the number of them  can be computed by L-k+1. The program can  report exactly the number of all repeat (freq>1) and unique(freq = 1) mers , and the number of all possible substrings of the sequences without cutting off any low frequency mers. </p>  
<p>Input files can be text or fasta format.The input alphabet now is only {A, C, G, T}. The text file input will be concerned as fasta format without description line. After counting and building the database of all possible length k of k-mer completed, User can choose a size of k in the menu to count a histogram, dump k-mers, query substrings, and summarize all possible k.</p>
<p>The program count k-mers regardless canonical form. However, the option of canonical form counting is available in the program menu. The canonical k-mers counting may require a quite more time than the ordinary form. The time and memory for building a database depend on the length of input sequences (m) and  the longest repeated substring in the sequences (n), which are in O(mn).  If the memory is insufficient, the program will run slower. In the experiment of a very long sequence (~200 millions bp from Fragaria Vesca), with CPU apple M1, RAM 16 GB, the program need approximately 30 GB of memory (insufficient memory) and use 2000 - 2500 seconds for building the database. With this database, the program can summarize the number of the distinct repeat and unique substrings of 1-mer to 4715-mer(longest repeated substring) within 30 seconds.</p>
<p>The program is suitable for works that want to count several large k of k-mers and suitable for to see the overview of the number of distinct repeat and unique for all possible size of k-mers at once.</p>

# REQUIREMENT
  **OS:** Windows10, MacOS_ARM64, MacOS_X64 <br>
  **RAM:** 8-64 GB, depend on the large size of the input sequence, approximately 32 GB for 200 million bp up. <br>
  
# NAME :
  UniversalMer  - A k-mer counting tool for all possible size of k at once. 

# SYNOPSIS: 
  UniversalMer [OPTIONS][FILE]

# DESCRIPTION:
        -b FILE : to build new Universal-mer database with an input file (FILE).
        -l  FILE : to load Universal-mer database from FILE. (xxx.Umer) or (xxx.umer) 
        -h : to see how to use the program

  If option is -b  FILE must be a text file or a fasta format file.<br>
  If option is -l  FILE must be a universal-mer database file with the extension '.umer' or '.Umer'. <br>
  If there is no argument, program will search for a database file (Universal_merDB.umer) in the same folder with the program.<br>
  After already building or loading a database, you can follow the instruction of the program to choose menu. <br>

# HOW TO USE THE PROGRAM
   Go to the directory of the executable file at  /bin/MacOs/UniversalMer.  <br>
   If there is no database file, run the program to count all possible k-mers first by.
   
       % ./UniversalMer -b  /input/xxx.fasta
      
   The program will build the database of all possible size k-mer.
   After building database completed, you can choose the menu of the program. If the database already exist, you can run the program with it for the next time by
   
       % ./UniversalMer -l  Universal_merDB.umer

  ! Please don't forget to backup the database file for using in the next time. If not, the database file will be deleted when you create a new one.
# OUTPUT
  * Universal_merDB.Umer is the default database file generated in the same folder of the executable file.
  * xxxmerHisto.txt is the report of histogram of xxx-mer
  * xxxmerCanonicalHisto.txt is the report of histogram of xxx-mer reducing canonical form.
  * xxx_mersData.txt is the xxx-mers text file with ordinary form.
  * xxx_mersCanodata.txt is the xxx-mers text file reducing canonical form.
  * allKsummarize.txt is the report of the number of distinct repeat and unique 1-mers to l-mers (the length of longest repeated substring).
    
# EXAMPLE
  * The running program pics place in the folder /Output/ <br>
  * The example of a database file and of input sequence files place in the folder /Example/ <br>
  * The DNA input sequences used in the experiments of our work place in the folder /input/ <br>

# BASIC OF UNIVERSAL MER CODING
  If you want to study the basic of Universal mer please visit at..<br>
  ..coming soon..
  
# LICENSE
  ! YOU may install and use an unlimited number of copies for personal and education use.<br>
  ! YOU may not sell, decompile, disassemble, reverse engineer or modify this program.<br>

# AUTHOR

  **Jittakorn Pullpothong**<br> Department of computer engineering, Faculty of engineering, Ramkhamhaeng University, Thailand.<br>
  Email: <jittakorn.p@rumail.ru.ac.th>


   
