# recursion-examples
**Recursion in DSA (Data Structures & Algorithms)** is a fundamental concept where a function calls itself to solve a problem. It breaks the problem into smaller subproblems until a base condition is met.

---

### 🔁 **Basic Structure**

```js
function recurse(params) {
  if (base condition) {
    return result;
  }
  // smaller subproblem
  return recurse(smaller params);
}
```

---

### 🧠 **Key Terms**

* **Base Case** – The stopping condition.
* **Recursive Case** – The part where the function calls itself.
* **Stack** – Each recursive call is pushed onto the call stack.

---

### 🔨 **Use Cases**

* Factorial, Fibonacci
* Backtracking (N-Queens, Sudoku)
* Divide & Conquer (Merge Sort, Quick Sort)
* Tree/Graph Traversal (DFS)
* Dynamic Programming (with memoization)

---

### ✅ **Pros**

* Elegant & clean solutions.
* Reduces complex problems to simple ones.

### ❌ **Cons**

* High memory usage (due to stack).
* Risk of stack overflow if not handled properly.

---

### 📌 Example: Factorial

```js
function factorial(n) {
  if (n === 0 || n === 1) return 1;
  return n * factorial(n - 1);
}
```

**Recursion in DSA (Data Structures & Algorithms)** is a fundamental concept where a function calls itself to solve a problem. It breaks the problem into smaller subproblems until a base condition is met.

---

### 🔁 **Basic Structure**

```js
function recurse(params) {
  if (base condition) {
    return result;
  }
  // smaller subproblem
  return recurse(smaller params);
}
```

---

### 🧠 **Key Terms**

* **Base Case** – The stopping condition.
* **Recursive Case** – The part where the function calls itself.
* **Stack** – Each recursive call is pushed onto the call stack.

---

### 🔨 **Use Cases**

* Factorial, Fibonacci
* Backtracking (N-Queens, Sudoku)
* Divide & Conquer (Merge Sort, Quick Sort)
* Tree/Graph Traversal (DFS)
* Dynamic Programming (with memoization)

---

### ✅ **Pros**

* Elegant & clean solutions.
* Reduces complex problems to simple ones.

### ❌ **Cons**

* High memory usage (due to stack).
* Risk of stack overflow if not handled properly.

---

### 📌 Example: Factorial

```js
function factorial(n) {
  if (n === 0 || n === 1) return 1;
  return n * factorial(n - 1);
}
```

Let’s go **deep into recursion in DSA**, including concept, mechanics, real-world use cases, and advanced examples like backtracking and divide & conquer.

---

## 🔁 What is Recursion?

**Recursion** is a technique where a function calls itself to break down a larger problem into smaller subproblems.

### 🔧 Anatomy of a Recursive Function

Every recursive function has:

1. **Base Case** – Terminates recursion.
2. **Recursive Case** – Breaks the problem and calls itself.

Example:

```js
function countdown(n) {
  if (n === 0) return;
  console.log(n);
  countdown(n - 1); // recursive call
}
```

---

## 🧠 How Recursion Works – Call Stack

Each recursive call is pushed to the **call stack**. When a base case is hit, functions start **resolving in reverse** (LIFO).

### Stack Trace (Example: `factorial(3)`)

```
factorial(3)
=> 3 * factorial(2)
       => 2 * factorial(1)
              => 1 (base case)
```

Stack unwinds:

```
factorial(1) → 1
factorial(2) → 2 * 1 = 2
factorial(3) → 3 * 2 = 6
```

---

## ⚙️ Common Recursive Patterns

### 1. **Mathematical Recursion**

* Factorial
* Fibonacci
* Power

```js
function factorial(n) {
  if (n === 0) return 1;
  return n * factorial(n - 1);
}
```

---

### 2. **Array Recursion**

* Sum of array
* Reverse array
* Max/min search

```js
function arraySum(arr, n) {
  if (n === 0) return 0;
  return arr[n - 1] + arraySum(arr, n - 1);
}
```

---

### 3. **Divide and Conquer**

Break problem into subproblems, solve them recursively.

* Merge Sort
* Quick Sort
* Binary Search

```js
function binarySearch(arr, target, low = 0, high = arr.length - 1) {
  if (low > high) return -1;
  const mid = Math.floor((low + high) / 2);
  if (arr[mid] === target) return mid;
  if (target < arr[mid]) return binarySearch(arr, target, low, mid - 1);
  return binarySearch(arr, target, mid + 1, high);
}
```

---

### 4. **Backtracking (Advanced Recursion)**

Explore all possible options. If one path fails, **backtrack** and try another.

#### Example: Subsets

```js
function subsets(nums) {
  const res = [];

  function backtrack(start = 0, path = []) {
    res.push([...path]);
    for (let i = start; i < nums.length; i++) {
      path.push(nums[i]);
      backtrack(i + 1, path);
      path.pop(); // backtrack
    }
  }

  backtrack();
  return res;
}
```

---

### 5. **Tree Traversal (Recursive)**

Trees are naturally recursive structures.

```js
function inorder(node) {
  if (!node) return;
  inorder(node.left);
  console.log(node.val);
  inorder(node.right);
}
```

---

## 🔍 Time & Space Complexity in Recursion

| Problem           | Time Complexity | Space (Stack) |
| ----------------- | --------------- | ------------- |
| Factorial         | O(n)            | O(n)          |
| Fibonacci (naive) | O(2^n)          | O(n)          |
| Fibonacci (memo)  | O(n)            | O(n)          |
| Merge Sort        | O(n log n)      | O(log n)      |

---

## ⚠️ Common Pitfalls

* **No Base Case → Stack Overflow**
* **Too many calls → Exponential time**
* **Missing backtracking step → Wrong results**
