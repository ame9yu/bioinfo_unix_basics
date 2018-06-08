## Some basic bioinformatics commands in linux
----- Yutong Qiu, 07.11.2017 ----

A. BAM <-> SAM conversion
	
	1. BAM -> SAM :`samtools view <bamfile>`
	2. SAM -> BAM: `samtools view -bS <samfile> [-T ref.fa if sam does not have header]`

B. Get first few lines of a file

	head -n <number of lines> <file>
	cat <file> | head -n <number of lines>
	
C. Get last few lines of a file
	`tail -n <number of lines> <file`
	
    * a negative number gives you all the lines except the last x lines	

D. Concatenate two or more files `cat <file1> <file2> ...`

E. Get word count/line count
	`wc <file>`
		or
	`cat <file> | wc -l (line count)`

F. Get certain columns of bed file
	`cat <file> | cut -f <1-based column index> -d <delimiter character>`
	
	example: cat example.csv | cut -f 1,3 -d ','

G. Compare files
	`diff <file1> <file2>`
	
	example: diff diff.a diff.b

F. Search
	`cat <file> | grep <keyword>`

G. Search in less
  - In less, type `/<keyword>` . Hit enter. Hit n for the next pattern.
	
### Some Exercises
* try to concatenate example_first500.bed and example_last500.bed and see if there is any differences with example.bed

### others
* Command I used to convert tab to comma:  `sed 's/\t/,/g' example.bed > example.csv`
	* I can never learn how to use 'sed' but google can always help me ;)
	* 'sed' is a stream editor that is used to perform basic text transformation. In my opinion it is itself a specialized language for text processing. 
	
* `awk` is also a very usefual tool for text processing. 

* default output to standard out. Remember to use '>' to redirect output to file

* some more useful commands:

	```shell
	ls -ltrh <directory, default: current working directory(wd)>
		option meaning: Long, Timely, Reversed, Humanreadable
	top
		see what program is currently running
	cd ~
		get back to home directory
	cp [-r if copying directory]
		copy
	mv  
		move files. Often used to rename things
	zcat
		cat gziped file
	gzip/gunzip 
		zip/unzip files
	chmod
		change permission
	```
