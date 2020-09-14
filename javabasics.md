# Java Basics
### [Home](README.md)

## Primitive values and their data size
They are special data types that are built into the language.  They are not objects created from a class.

| Data type       | bit    | 
| :------------- | :----------: | 
|  byte | 8   | 
| short  | 16 | 
|  int | 32   | 
| long   | 64 | 
|  float | 32   | 
| double   | 64 | 
|  char | 16  | 


## Default values


| Data Type      | Default Value     |
| :------------- | :----------: | 
|  byte | 0   | 
| short   | 0 | 
|  int | 0   | 
| long   | 0L | 
|  float  | 0.0f   | 
| double   | 0.0d | 
|  char | '\u0000'   | 
| String    | null | 
|  boolean  | false   | 

## Literals  
A __literal__ is the source code representation of a fixed value

The Java programming language also supports a few special escape sequences for char and String literals: 
```
\b (backspace), 
\t (tab), 
\n (line feed), 
\f (form feed), 
\r (carriage return), 
\" (double quote), 
\' (single quote), and 
\\ (backslash)
```

There's also a special kind of literal called a __class literal__, formed by taking a type name and appending ".class"; for example, String.class. This refers to the object (of type Class) that represents the type itself.

## Arrays 
``` 
int[] anArrayOfIntegers;
byte[] anArrayOfBytes;
short[] anArrayOfShorts;
long[] anArrayOfLongs;
float[] anArrayOfFloats;
double[] anArrayOfDoubles;
boolean[] anArrayOfBooleans;
char[] anArrayOfChars;
String[] anArrayOfStrings;
```

The code to initialize an array:
```
// declares an array of integers
int[] anArray;  
// create an array of integers
anArray = new int[10];  
anArray[0]=......
```
OR you can also do
```
int[] anArray = {100, 200, 300, ...};
```

An array of arrays is declared like this:
```
String[][] names = {
            {"Mr. ", "Mrs. ", "Ms. "},
            {"Smith", "Jones"}
        };
```

### Copy arrays  
```
public static void arraycopy(Object src, int srcPos,
                             Object dest, int destPos, int length)
```

### Array manipulation to copy array instead of arraycopy
```
char[] copyTo = java.util.Arrays.copyOfRange(copyFrom, 2, 9);
```
Other array manipulations are:
```
Searching an array for a specific value to get the index at which it is placed (the binarySearch method).
Comparing two arrays to determine if they are equal or not (the equals method).
Filling an array to place a specific value at each index (the fill method).
Sorting an array into ascending order. This can be done either sequentially, using the sort method, or concurrently, using the parallelSort method introduced in Java SE 8. Parallel sorting of large arrays on multiprocessor systems is faster than sequential array sorting.
```

                            

