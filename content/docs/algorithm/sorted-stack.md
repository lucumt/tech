---
title: "单调栈"
weight: 1
# bookFlatSection: false
# bookToc: true
# bookHidden: false
# bookCollapseSection: false
# bookComments: false
# bookSearchExclude: false
---

* **单调递增**，从栈顶到栈底依次递增

  ```java
  public static void sortStackIncrease() {
      int[] data = {2, 7, 5, 4, 6, 3, 4, 2};
      Stack<Integer> stack = new Stack<>();
      for (Integer val : data) {
          while (!stack.isEmpty() && stack.peek() <= val) {
              stack.pop();
          }
          stack.push(val);
      }
      System.out.println(stack);
  }
  ```

* **单调递减**，从栈顶到栈底依次递减

  ```java
  public static void sortStackDecrease() {
      int[] data = {4, 3, 2, 5, 7, 4, 6, 8};
      Stack<Integer> stack = new Stack<>();
      for (Integer val : data) {
          while (!stack.isEmpty() && stack.peek() >= val) {
              stack.pop();
          }
          stack.push(val);
      }
      System.out.println(stack);
  }
  ```

---

* 找到数组右边第一个比它大的元素，第1种实现，基于倒序号，自己有些看不懂

  ```java
  public static void nextGreaterElement() {
      int[] data = {2, 7, 5, 4, 6, 3, 4, 2};
      int[] result = new int[data.length];
      Stack<Integer> stack = new Stack<>();
      // 单调递增
      for (int i = data.length - 1; i >= 0; i--) {
          int val = data[i];
          while (!stack.isEmpty() && stack.peek() <= val) {
              stack.pop();
          }
          result[i] = stack.empty() ? -1 : stack.peek();
          stack.push(val);
      }
      System.out.println(stack);
      System.out.println(StringUtils.join(ArrayUtils.toObject(result), ","));
  }
  ```

  符合常规思维的从左到右的实现，此时记录的是下标值
  
  ```java
  public static void nextGreaterElement() {
      int[] data = {2, 7, 5, 4, 6, 3, 4, 2};
      int[] result = new int[data.length];
      Arrays.fill(result, -1);
      Stack<Integer> stack = new Stack<>();
      // 单调递增
      for (int i = 0; i < data.length; i++) {
          int val = data[i];
          while (!stack.isEmpty() && data[stack.peek()] < val) {
              result[stack.pop()] = val;
          }
          stack.push(i);
      }
      System.out.println(stack);
      System.out.println(StringUtils.join(ArrayUtils.toObject(result), ","));
  }
  ```
  
  