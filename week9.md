# Marisa Kawakami Week 9: Lab Report 5

## Lab 6: Grading Script 

**File Exists**

In order to check if the file exists it with be put into an if statement. In this it will use the command `-f` to find the file name. In this case it is seraching for "student-submission/ListExamples.java". If it finds what is in the quotes then then it will echo that the file exists, and will continue on with the other tests. If it does not contain this then it will exit and echo that there is no file and the student will recieve partial credit and prompts for resubmission. 
```
if [[ -f "student-submission/ListExamples.java" ]]
then 
    echo "File exists"
else 
    echo "No file"
    echo "partial credit - resubmit"
    exit
fi 
```
![no file](test5.png)
![nested](test6.png)

**Class Checker**

First creating a variable `CLASS_CHECKER` in bash script. Then using the backticks around what the variable is equal to. In order to check if there is a class name called ListExamples, you must use grep which is searching for a string of characters "class ListExamples" in the file. Then using the bash script variable you want to use the if statements in order to find if the file contains the class name or not. I had whatever was found using grep and comparing if that was equal to an empty string. If it did equal eachother then it meant that it was missing the class and would echo that it must have theclass name. 

```
CLASS_CHECKER=`grep "class ListExamples" ListExamples.java`
if [[ $CLASS_CHECKER == "" ]]
then 
    echo "Must have a class ListExamples"
    echo "partial credit - resubmit"
    exit
fi 
```
**Method Filter**

![filtermethod](test4.png)

**Compiles**
![complies](test3.png)


**Method Merge**


**Method Passed**
![test2](test2.png)


**challenge**
![challenge](challenge.png)
