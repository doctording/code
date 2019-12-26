---
title: "152 之字形打印矩阵"
layout: page
date: 2019-12-26 14:29
---

[TOC]

# ac

```java
import java.io.BufferedReader;
import java.io.InputStreamReader;
import java.util.*;

public class Main {
    public static Scanner sc = new Scanner(System.in);

    public static BufferedReader reader = new BufferedReader(new InputStreamReader(System.in));

    public static long mod = (long)Math.pow(2,29);

    static boolean rightPos(int n, int m, int i, int j){
        if(i >=0 && i < n && j >= 0 && j < m){
            return true;
        }
        return false;
    }

    public static void main(String[] args) throws Exception {
        int n = sc.nextInt();
        int m = sc.nextInt();
        int[][] arr = new int[n][m];
        for(int i=0;i<n;i++){
            for(int j=0;j<m;j++) {
                int val = sc.nextInt();
                arr[i][j] = val;
            }
        }
        boolean order = true; // true 斜向上, false 是斜向下
        int staI = 0;
        int staJ = 0;
        while (staI < n && staJ < m){
            int tmpI = staI;
            int tmpJ = staJ;
            if(order){
                while (rightPos(n,m,tmpI, tmpJ)){
                    System.out.print(arr[tmpI][tmpJ] + " ");
                    tmpI--;
                    tmpJ++;
                }
                int lastRightI = tmpI + 1;
                int lastRightJ = tmpJ - 1;
                staI = lastRightI;
                staJ = lastRightJ + 1;
                if(!rightPos(n,m,staI,staJ)){
                    staI = lastRightI + 1;
                    staJ = lastRightJ;
                }
            }else {
                while (rightPos(n,m,tmpI, tmpJ)){
                    System.out.print(arr[tmpI][tmpJ] + " ");
                    tmpI++;
                    tmpJ--;
                }
                int lastRightI = tmpI - 1;
                int lastRightJ = tmpJ + 1;
                staI = lastRightI + 1;
                staJ = lastRightJ;
                if(!rightPos(n,m,staI,staJ)){
                    staI = lastRightI;
                    staJ = lastRightJ + 1;
                }
            }
            order = !order; // 顺序变了
        }
//        System.out.println();
    }

}
/*
4 4
1 2 3 4
5 6 7 8
9 10 11 12
13 14 15 16

1 2 5 9 6 3 4 7 10 13 14 11 8 12 15 16

4 3
1  2  3
4  5  6
7  8  9
10 11 12

1 2 4 7 5 3 6 8 10 11 9 12


3 4
1  2  3  4
5  6  7  8
9  10 11 12
*/
```
