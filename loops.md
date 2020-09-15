# Java Loops  
[Home](./README.md)  
[Reference](https://www.baeldung.com/java-loops)  


## For Loop
A for loop is a control structure that allows us to repeat certain operations by incrementing and evaluating a loop counter.

For a detailed example, have a look at the dedicated post: [Java For Loop](https://www.baeldung.com/java-for-loop).  

#### labeled for loops  
```
aa: for (int i = 1; i <= 3; i++) {
    if (i == 1)
      continue;
    bb: for (int j = 1; j <= 3; j++) {
        if (i == 2 && j == 2) {
            break aa;
        }
        System.out.println(i + " " + j);
    }
}
```
#### Enhanced for loops  
```
int[] intArr = { 0,1,2,3,4 }; 
for (int num : intArr) {
    System.out.println("Enhanced for-each loop: i = " + num);
}
```
```
for (Entry<String, Integer> entry : map.entrySet()) {
    System.out.println(
      "Key: " + entry.getKey() + 
      " - " + 
      "Value: " + entry.getValue());
}
```
#### For each
```
default void forEach(Consumer<? super T> action) {
    Objects.requireNonNull(action);
    for (T t : this) {
        action.accept(t);
    }
}
```

## While Loop
The while loop is Java's most fundamental loop statement. It repeats a statement or a block of statements while its controlling Boolean-expression is true.

For a detailed example, have a look at the dedicated post: [Java While Loop](https://www.baeldung.com/java-while-loop).  

## Do-While Loop
The do-while loop works just like the while loop except for the fact that the first condition evaluation happens after the first iteration of the loop.

For a detailed example, have a look at the dedicated post: Java [Do-While Loop](https://www.baeldung.com/java-do-while-loop).  

```
int i = 0;
do {
    System.out.println("Do-While loop: i = " + i++);
} while (i < 5);
```
