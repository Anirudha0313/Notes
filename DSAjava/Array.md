🧱 1️⃣ What Is an Array?

An array is a collection of elements stored under one name.

Instead of writing:

int a = 10;
int b = 20;
int c = 30;


We write:

int[] arr = {10, 20, 30};


Now:

arr stores 3 values.

Each value has a position (index).

🧱 2️⃣ How Array Is Stored in Memory (Very Important)

When you write:

int[] arr = {10, 20, 30};


Java does:

Creates array somewhere in memory

Stores values in that memory

Stores the location of that memory inside arr

So:

arr  →  [10, 20, 30]


Important:

arr does NOT store all values directly.
It stores the address of the array.

This is why arrays behave differently in methods.

🧱 3️⃣ Indexing Rule (MOST IMPORTANT RULE)

Array index always starts from 0.

If array size = n
Valid index range = 0 to n-1

Example:

int[] arr = {5, 8, 2};

Index	Value
0	5
1	8
2	2

If you try:

arr[3];


You get:

❌ ArrayIndexOutOfBoundsException

Because size = 3
Valid indexes = 0,1,2

🧱 4️⃣ Ways to Create Arrays
🔹 Method 1 — Direct Initialization
int[] arr = {1,2,3};


Size decided automatically.

🔹 Method 2 — Using new Keyword
int[] arr = new int[3];


This creates:

[0,0,0]


Why?

Default value of int = 0.

Default values:

Type	Default
int	0
double	0.0
boolean	false
String	null
🧱 5️⃣ Accessing Elements
arr[0];
arr[1];


Example:

System.out.println(arr[1]);


Prints value at index 1.

🧱 6️⃣ Array Length

Every array has a property:

arr.length


Example:

System.out.println(arr.length);


If arr = {5,8,2}
Output = 3

Important:
length is NOT a method.
No brackets.

Correct:

arr.length


Wrong:

arr.length()

🧱 7️⃣ Traversing an Array (Very Important for DSA)

To visit every element:

for(int i = 0; i < arr.length; i++) {
    System.out.println(arr[i]);
}


Structure explanation:

i starts at 0

i goes until last index

i increases by 1

arr[i] accesses element

This pattern is used in almost every DSA problem.

🧱 8️⃣ Common Array Patterns (DSA Foundation)
🔹 1. Sum of Array
int sum = 0;

for(int i = 0; i < arr.length; i++) {
    sum = sum + arr[i];
}


Pattern name: Accumulator pattern

🔹 2. Find Maximum
int max = arr[0];

for(int i = 1; i < arr.length; i++) {
    if(arr[i] > max) {
        max = arr[i];
    }
}


Important:
Start from index 1.
Because index 0 already stored in max.

🔹 3. Count Elements

Example: count even numbers

int count = 0;

for(int i = 0; i < arr.length; i++) {
    if(arr[i] % 2 == 0) {
        count++;
    }
}

🧱 9️⃣ Printing Entire Array
❌ Wrong Way
System.out.println(arr);


Prints memory info.

✅ Using Loop
for(int i = 0; i < arr.length; i++) {
    System.out.print(arr[i] + " ");
}

✅ Using Arrays Utility (Shortcut)
import java.util.Arrays;
System.out.println(Arrays.toString(arr));


This internally uses loop.

🧱 🔟 Arrays in Methods (VERY IMPORTANT)
Case 1 — Modify Elements
public static void change(int[] arr) {
    arr[0] = 100;
}


Original array WILL change.

Because both refer to same array.

Case 2 — Reassign Array
public static void change(int[] arr) {
    arr = new int[]{9,9,9};
}


Original array will NOT change.

Because only local reference changed.

🧠 Key Concept — Primitive vs Array

Primitive:

int a = 5;


Method receives copy of value.

Array:

int[] arr = {1,2,3};


Method receives copy of address.

Both variables point to same array.

🧱 1️⃣1️⃣ Common Beginner Mistakes

❌ Using <= arr.length in loop
Correct: < arr.length

❌ Forgetting update in loop
Leads to infinite loop

❌ Accessing invalid index
Leads to exception

❌ Printing array directly
Prints memory info

🧱 1️⃣2️⃣ Big-O Thinking with Arrays

If array size = n

Traversing once:
O(n)

Finding max:
O(n)

Accessing arr[i]:
O(1)

Access by index is constant time.

This is why arrays are powerful.