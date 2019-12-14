Code for LZMP
-------------

Alexander Belousov and Joel Ratsaby
Contact: alex.blsv@gmail.com,    ratsaby@ariel.ac.il

This directory contains the source code for computing the Lempel Ziv complexity 
efficiently in parallel distributed processing on CUDA.

For a description of the algorithm see the web page at 
http://www.ariel.ac.il/sites/ratsaby/Publications/PDF/ieee-2014.pdf


==================================================
Please cite these two papers if you use this code:

A. Belousov, J. Ratsaby, Massively parallel computations of the LZ-complexity of strings, Proc. of the 28th  IEEE Convention of Electrical and Electronics Engineers in Israel (IEEEI'14), pp. 1-5, Eilat, Israel, Dec. 3-5, 2014.

A. Belousov , J. Ratsaby. (2015) A Parallel Distributed Processing Algorithm for Image Feature Extraction , in E. Fromont, T. De Bie, M. van Leeuwen (Eds.), Advances in Intelligent Data Analysis XIV, Proc. of the 14-th International Symposium on Intelligent Data Analysis (IDA'15), Springer LNCS Vol. 9385, Saint-Etienne, France, Oct. 22-24.


Bitex format:

@INPROCEEDINGS{7005885, 
author={A. Belousov and J. Ratsaby}, 
booktitle={2014 IEEE 28th Convention of Electrical Electronics Engineers in Israel (IEEEI)}, 
title={Massively parallel computations of the LZ-complexity of strings}, 
year={2014}, 
pages={1-5}, 
doi={10.1109/EEEI.2014.7005885}, 
month={Dec},}

@inproceedings{DBLP:conf/ida/BelousovR15,
  author    = {Alexander Belousov and
               Joel Ratsaby},
  title     = {A Parallel Distributed Processing Algorithm for Image Feature Extraction},
  booktitle = {Advances in Intelligent Data Analysis {XIV} - 14th International Symposium,
               {IDA} 2015, Saint Etienne, France, October 22-24, 2015, Proceedings},
  pages     = {61--71},
  year      = {2015},
  doi       = {10.1007/978-3-319-24465-5_6},
}

================================================


Notes
-----

Enclosed in this ZIP file is the exported project form Nsight Eclipse Edition
(the CUDA development tool of nVidia).
You just need to open this took, and import this ZIP file, and add it to our cuda-workspace. Then build it, and run the executable (binary) from a regular terminal, it is in the folder Debug to see an example running.

The project was tested with  CUDA toolkit 8.0 and runs on nVidia TESLA k20c board.

The code uses a function called  LZMP_Calculate which takes in an array of strings
and calculates their LZ-complexities.

The code currently calls from main (in main.cpp) a function LZMP_Test_Dictionary
which runs the LZMP_Calculate function on a string ABCABCDABCDEFABCABCDABCDEF
then prints out to the screen the dictionary (in the LZ 1978 paper this is called the exhaustive history of the string). It also prints the size of the dictionary = LZ-complexity of the string.

To use the code (obviously, without this example) you should
put #undef PRINT_SUBSTRING   (because printing to the screen adds processing time)
and then call LZMP_Calculate directly in your application.

Note that LZMP_Calculate runs in parallel over the nVidia card.



Licensing conditions
--------------------
See the file LICENSE.txt in this directory for conditions of use.
