📘 PHASE 1 — ARRAYS
🟢 MODULE 1 — TRAVERSAL PATTERN
1️⃣ What Is Traversal?

Traversal means:

👉 Visiting every element of an array one by one.

Core loop:

for (int i = 0; i < arr.length; i++) {
    // access arr[i]
}


Key Rule:

Index starts from 0

Last index = arr.length - 1

Loop runs n times (if size = n)

Time Complexity:

O(n)

2️⃣ Index Rules (Very Important)

If:

int[] arr = {4, 7, 1};


Then:

arr.length = 3

Valid indexes = 0, 1, 2

Last index = arr.length - 1

Common mistake:

❌ i <= arr.length → causes crash
✅ i < arr.length

3️⃣ Accumulator Pattern

An accumulator is a variable that builds result step-by-step.

Example — Sum:

int sum = 0;

for (int i = 0; i < arr.length; i++) {
    sum += arr[i];
}

return sum;


Rules:

Initialize before loop

Update inside loop

Return after loop

Used for:

Sum

Count

Product

4️⃣ Counting Pattern

Used when counting elements satisfying condition.

Example — Count Even Numbers:

int count = 0;

for (int i = 0; i < arr.length; i++) {
    if (arr[i] % 2 == 0) {
        count++;
    }
}

return count;


Time Complexity:

O(n)

5️⃣ Linear Search (Early Return Pattern)

Find index of target.

public static int linearSearch(int[] arr, int target) {

    for (int i = 0; i < arr.length; i++) {
        if (arr[i] == target) {
            return i;
        }
    }

    return -1;
}


Key Idea:

Stop immediately when found

Return -1 if not found

6️⃣ Comparison Pattern (Max / Min)

Used to track best value while traversing.

Example — Find Maximum:

int max = arr[0];

for (int i = 1; i < arr.length; i++) {
    if (arr[i] > max) {
        max = arr[i];
    }
}

return max;


Important:
❌ Never initialize max = 0
✅ Always initialize max = arr[0]

Handles negative numbers safely.

7️⃣ Multiple Accumulator Pattern (Second Maximum)

Used when tracking more than one value.

int max = arr[0];
int secondMax = Integer.MIN_VALUE;

for (int i = 1; i < arr.length; i++) {

    if (arr[i] > max) {
        secondMax = max;
        max = arr[i];
    }
    else if (arr[i] > secondMax && arr[i] != max) {
        secondMax = arr[i];
    }
}

return secondMax;


Concepts Learned:

Order of conditions matters

Duplicate handling

Edge case awareness

8️⃣ Adjacent Comparison Pattern

Used when comparing neighbors.

Example — Check If Sorted:

public static boolean isSorted(int[] arr) {

    for (int i = 0; i < arr.length - 1; i++) {
        if (arr[i] > arr[i + 1]) {
            return false;
        }
    }

    return true;
}


Key Rule:

Loop runs n - 1 times

Use arr.length - 1 in condition

9️⃣ Time Complexity Summary

All Module 1 problems:

O(n)


Because we traverse array once.

🔟 Common Beginner Mistakes

❌ Using <= arr.length
❌ Initializing max with 0
❌ Returning inside loop incorrectly
❌ Modifying array accidentally when only checking
❌ Forgetting edge cases (duplicates, small size)

🧠 Mental Model Summary

Before solving any array problem, ask:

1️⃣ Do I need to visit all elements? → Traversal
2️⃣ Do I need to build result? → Accumulator
3️⃣ Do I need best value? → Comparison
4️⃣ Can I stop early? → Early return
5️⃣ Am I comparing neighbors? → Use length - 1

🟢 What You Can Solve After Module 1

Linear Search

Count Occurrences

Count condition-based problems

Find max / min

Find second max

Check if sorted

Basic LeetCode Easy array problems

📌 Module 1 Status

You now understand:

✔ Traversal
✔ Accumulator
✔ Comparison
✔ Multiple accumulators
✔ Boundary conditions
✔ Early return
✔ O(n) complexity

This is foundational DSA thinking.