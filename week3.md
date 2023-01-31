# Marisa Kawakami Week 3: Lab Report 

## Part 1: Simplest Search Engine (week 2) 
![Image](StringServer.png)
---
![Image](addmessage1.png)
* The method `String handleRequest(URI url)` is called in order to 
* The relevant arguments that are used in the method are the = `add-message` if this is in the url then it split the url after the query and creating two parts. By doing this it will then take what is in the first element of the array and add it to the String `string`. This allows you to add whatever you like to the string that will be returned on the screen. In this example it is 
---
![Image](addlovesfood.png)


---
## Part 2: Syptoms of Bugs (week 3)

test that will fail 
```
@Test
  public void testReversed2(){
    int[] input = {1,2,3,4};
    assertArrayEquals(new int[]{4,3,2,1}, ArrayExamples.reversed(input));
```
test that will work accidentaly 

```@Test
  public void testReversed() {
    int[] input1 = { };
    assertArrayEquals(new int[]{ }, ArrayExamples.reversed(input1));
  }
```

buggy code
```
static int[] reversed(int[] arr) {
  int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
  }
```
fixed code
```
static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      newArray[i] = arr[arr.length -i -1];
    }
    return newArray;
  }
```
## Part 3: 
In week 2 lab I learned how to build and run the server along with having the need to have a port number. The port that is identifying the specific port tthat is being run. 
Notes:
* In order to exit out of a loop in a server you must hit control C 
* 
