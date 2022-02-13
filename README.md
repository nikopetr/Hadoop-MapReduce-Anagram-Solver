# Hadoop-MapReduce-Anagram-Solver

<p align="center">
  <img src="https://github.com/nikopetr/Hadoop-MapReduce-Anagram-Solver/blob/main/hadoop_img.png" width="700" height="300"/>
</p>

The implementation consists of a program that utilizes the Hadoop Map-Reduce framework to identify the anagrams of the words of a file.

**Author**: Nikolas Petrou, MSc in Data Science


## But what is an anagram?
An anagram is a word or phrase formed by rearranging the letters of a different word, by using all the original characters/letters exactly once.

For example:
- Refills→fillers
- Relayed→layered
- Rentals→antlers
- Rebuild→builder


## Data 
Specifically this task focuses on finding the anagrams of the words of the following file: https://raw.githubusercontent.com/pmichaud/rpbench/master/files/unixdict.txt

You can download & upload the aforementioned UNIX dictionary file to your own HDFS filesystem using the following commands:
- wget https://raw.githubusercontent.com/pmichaud/rpbench/master/files/unixdict.txt
- hadoop fs -copyFromLocal unixdict.txt filename_of_input_file


## Implementation
Examples of desired output:
- 2 hasn't,shan't
- 2 cascara,caracas
- 2 ramada,armada

The main idea of this problem's solution is to use the same Key for every word that can be rearranged together. Thus, the ideal Key for each read word to use during the mapping phase, is a Text object with the **sorted letters-characters (alphabetically)** of the read word. For example, both _declaim_ and _decimal_ words will be using the key _acdeilm_.

The desired output of the program is located in the [part-r-00000](https://github.com/nikopetr/Hadoop-MapReduce-Anagram-Solver/blob/main/Anagram/part-r-00000) file, while the code file is located in the [Anagram.java](https://github.com/nikopetr/Hadoop-MapReduce-Anagram-Solver/blob/main/Anagram/src/Anagram.java) file. There are more than enough comments which explain the whole implementation very analytically.


## Helpful Material-Links
If you are not very familiar with the Hadoop Map-Reduce framework, the following sites provide useful information for understanding some basic concepts, as well as some of the ideas of this task:

[Fundamentals of MapReduce with MapReduce Example](https://medium.com/edureka/mapreduce-tutorial-3d9535ddbe7c)

[Creating Custom Hadoop Writable Data Type](http://hadooptutorial.info/creating-custom-hadoop-writable-data-type/)

[MSc in Data Science Programme](https://datascience.cy/)
