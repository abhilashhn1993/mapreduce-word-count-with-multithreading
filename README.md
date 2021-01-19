# Word count with mapreduce using Multi-threading
Exploring the "Hello World" of MapReduce programming paradigm using multi-threading in python

### TABLE OF CONTENTS
* [Objective](#objective)
* [Data](#data)
* [Technologies](#technologies)
* [Implementation](#implementation)
* [Results](#results)
* [References](#references)


## OBJECTIVE
Perform processing of text and count the occurence of each word using map-reduce concept amd mimic Hadoop infrastructure with parallel processing. Multi-threading is used to execute two mapper and reducer functions.

## DATA
Data is made available [here](https://github.com/abhilashhn1993/mapreduce-word-count-with-multithreading/blob/master/Data.txt)

## TECHNOLOGIES
- Mapreduce, Python, Python - Multi-threading 

## IMPLEMENTATION

### Map-Reduce
Consider the following Text - "I am a human being. I am a Data Scientist"

MAP : Read Input and produce a set of key value pairs

(I,1) (am,1) (a,1) (human,1) (being,1) (I,1) (am,1) (a,1) (Data,1) (Scientist,1)

GroupBy : Collect all pairs with same key

(I,1),(I,1) | (am,1),(am,1) | (a,1),(a,1) | (human,1),(being,1) | (Data,1),(Scientist,1)

Reduce : Collect all values belonging to the key & output

(I,2) | (am,2) | (a,2) | (human,1) | (being,1) | (Data,1) | (Scientist,1)

Here we implement the concept of multithreading, to parallelize the process. Map Reduce is divided into sub tasks in parallel & aggregate teh results of sub-totals to final output. The process of mapping key to value and further aggregating them through reducers is achieved by the theards.


With the above concept in place, we implement the setup in the following steps:

Step1 : Map for key value pairs with multiple mappers

Step2 : Sort the values and load in to the partition holder

Step3 : Multiple Reducers to pic from the partition and aggregate them

The above steps will yield a list of outputs from the reducer, which could be concatenated and loaded into a datafram or a spreasheet

## RESULTS
The deployed model can be accessed from the url from any system to translate kannada sentences to english

![Capture](https://user-images.githubusercontent.com/9445072/105094042-44f67300-5a69-11eb-96d2-2a6d697e2e93.JPG)

## REFERENCES
- https://www.geeksforgeeks.org/hadoop-streaming-using-python-word-count-problem/
- https://freecontent.manning.com/implementing-a-mapreduce-framework-using-python-threads/
- https://nidhog.medium.com/how-to-quickly-write-a-mapreduce-framework-in-python-821a79fda554