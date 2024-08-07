---
created: 2024-08-07 10:50
tags:
  - Arrays
  - "#search"
  - "#matrices"
Parent Topic:
  - "[[Arrays]]"
Related Topics:
---

***
```java
public class findNuminMatrix {  
  
  
    public static boolean search(int[][] a,int n, int x) {  
        int i = 0;  
        int j = n - 1;  
  
  
        while(i < n && j > 0) {  
  
            if(a[i][j] == x) {  
                return true;  
            }  
            if(a[i][j] > x) {  
                j--;  
            } else {  
                i++;  
            }  
        }  
        return false;  
    }  
    public static void main(String[] args) {  
        int[][] a = {{1,2,3},  
                {4,5,6},  
                {7,8,9}};  
  
        System.out.println(search(a,3,9));  
    }  
}
```

