# Marisa Kawakami Week 5: Lab Report 3 - Researching Commands 

## `grep` 
- `grep` takes a string and a file, then prints out all the lines that exist in the file that match the inputed string. 
    - `grep "Bahamas" *.txt` will print out all the .txt files that contains Bahamas
- `man grep` another built-in command that can help by displaying more information about different commands. 

```
grep -R "Lucayans"

written_2/travel_guides/berlitz2/Bahamas-History.txt:Centuries before the arrival of Columbus, a peaceful Amerindian people who called themselves the Luccucairi had settled in the Bahamas. Originally from South America, they had traveled up through the Caribbean islands, surviving by cultivating modest crops and from what they caught from sea and shore. Nothing in the experience of these gentle people could have prepared them for the arrival of the Pinta, the Niña, and the Santa Maria at San Salvador on 12 October 1492. Columbus believed that he had reached the East Indies and mistakenly called these people Indians. We know them today as the Lucayans. Columbus claimed the island and others in the Bahamas for his royal Spanish patrons, but not finding the gold and other riches he was seeking, he stayed for only two weeks before sailing towards Cuba.
written_2/travel_guides/berlitz2/Bahamas-History.txt:The Spaniards never bothered to settle in the Bahamas, but the number of shipwrecks attest that their galleons frequently passed through the archipelago en route to and from the Caribbean, Florida, Bermuda, and their home ports. On Eleuthera the explorers dug a fresh-water well — at a spot now known as “Spanish Wells” — which was used to replenish the supplies of water on their ships before they began the long journey back to Europe with their cargoes of South American gold. As for the Lucayans, within 25 years all of them, perhaps some 30,000 people, were removed from the Bahamas to work — and die — in Spanish gold mines and on farms and pearl fisheries on Hispaniola (Haiti), Cuba, and elsewhere in the Caribbean.
```

```
grep -R -l "Lucayans"

written_2/travel_guides/berlitz2/Bahamas-History.txt
```
- `-R` is recursively reading through each of the .txt files and finding all of them that contain the string Lucayans in the data of the file. When you combine `-R` with `-l` is recusively going through the data in the directory and finding the file that contains the string. As shown in the second code block it will just return the file that has the string in it rather than the file and the sections of the daat that contains the string. This is useful when you needs to check whether a file contains a word or subject and be able to find it quickly.
[-R](https://stackoverflow.com/questions/1987926/how-do-i-recursively-grep-all-directories-and-subdirectories)

```
grep -vn "Bahamas" grep-results.txt

221:written_2/travel_guides/berlitz2/PuertoRico-WhereToGo.txt
222:written_2/travel_guides/berlitz2/Vallarta-History.txt
223:written_2/travel_guides/berlitz2/Vallarta-WhatToDo.txt
224:written_2/travel_guides/berlitz2/Vallarta-WhereToGo.txt
```
```
grep -vn "Lucayans" grep-results.txt

220:written_2/travel_guides/berlitz2/PuertoRico-WhatToDo.txt
221:written_2/travel_guides/berlitz2/PuertoRico-WhereToGo.txt
222:written_2/travel_guides/berlitz2/Vallarta-History.txt
223:written_2/travel_guides/berlitz2/Vallarta-WhatToDo.txt
224:written_2/travel_guides/berlitz2/Vallarta-WhereToGo.txt
```

- This command printed out hundreds of files that do not match the search string "Bahamas". The command `-n` is useful for returning which line the string is in. By adding the `-vn` printed all the negative results. It prints every single line that does not match the string that is being searched. By using both it will also display the line number of all the lines that do not contain the string. 
[-vn](https://qpeng.org/computer/grep.htm#:~:text=The%20%2Dc%20option%20tells%20grep,of%20%22boo%22%20in%20a_file.&text=An%20option%20more%20useful%20for,is%20%2Di%2C%20ignore%20case.)

```
grep -c "Bahamas" grep-results.txt
4
```

```
grep -c "bahamas" grep-results.txt
0
```
- `-c` This command prints the number of matching lines that the string is in. It is helpful to know how many of the lines contain the specific string. 
[-c](https://qpeng.org/computer/grep.htm#:~:text=The%20%2Dc%20option%20tells%20grep,of%20%22boo%22%20in%20a_file.&text=An%20option%20more%20useful%20for,is%20%2Di%2C%20ignore%20case.)

```
grep -i "bahamas" grep-results.txt
written_2/travel_guides/berlitz2/Bahamas-History.txt
written_2/travel_guides/berlitz2/Bahamas-Intro.txt
written_2/travel_guides/berlitz2/Bahamas-WhatToDo.txt
written_2/travel_guides/berlitz2/Bahamas-WhereToGo.txt
```
```
grep -i "BAHAMAS" grep-results.txt
written_2/travel_guides/berlitz2/Bahamas-History.txt
written_2/travel_guides/berlitz2/Bahamas-Intro.txt
written_2/travel_guides/berlitz2/Bahamas-WhatToDo.txt
written_2/travel_guides/berlitz2/Bahamas-WhereToGo.txt
```
```
grep -i "baham" grep-results.txt
written_2/travel_guides/berlitz2/Bahamas-History.txt
written_2/travel_guides/berlitz2/Bahamas-Intro.txt
written_2/travel_guides/berlitz2/Bahamas-WhatToDo.txt
written_2/travel_guides/berlitz2/Bahamas-WhereToGo.txt
```
- `-i` This command searches through which fiels contain the string. It treats both upper and lower case letters equal so it will return the files without being case sensitive. It also will return the files if the string is only parts of the entire word. This is very helpful if you are not exactly sure how the names are types out. 
[-i](https://qpeng.org/computer/grep.htm#:~:text=The%20%2Dc%20option%20tells%20grep,of%20%22boo%22%20in%20a_file.&text=An%20option%20more%20useful%20for,is%20%2Di%2C%20ignore%20case.)

```
grep -c -i "HAM" grep-results.txt
4
```
- This one finds the files that have the string in them without being case sensitive. Instead of returning the specific path files it returns the number of files that exist. This is helpful if you need to find the number of possible files that the string occurs in without worrying about upper or lower case letters. 
[-c -i](https://qpeng.org/computer/grep.htm#:~:text=The%20%2Dc%20option%20tells%20grep,of%20%22boo%22%20in%20a_file.&text=An%20option%20more%20useful%20for,is%20%2Di%2C%20ignore%20case.)






