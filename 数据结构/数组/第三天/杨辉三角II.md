
给定一个非负索引 `rowIndex`，返回「杨辉三角」的第 `rowIndex` 行。

在「杨辉三角」中，每个数是它左上方和右上方的数的和。

**示例1：**

```
输入: rowIndex = 3
输出: [1,3,3,1]
```

**示例 2:**

```
输入: rowIndex = 0
输出: [1]
```

**示例 3:**

```
输入: rowIndex = 1
输出: [1,1]
```

> 方法一

```java
class Solution {
    public List<Integer> getRow(int rowIndex) {
        int a [][] = new int[rowIndex+1][rowIndex+1];

        for (int i = 0; i < a.length; i++) {
            for (int j = 0; j < a.length; j++) {
                if (i == 0 || j == 0 || i == j) {
                    a[i][j] = 1;
                } else {
                    a[i][j] = a[i - 1][j] + a[i - 1][j - 1];
                }
            }
        }

        for (int t [] : a) {
            for (int s : t) {
                System.out.print(s+" ");
            }
            System.out.println();
        }

        List<Integer> list = new ArrayList<>();
        for (int i = 0; i < a.length; i++) {
            list.add(a[a.length - 1][i]);
        }

        return list;
    }
}
```