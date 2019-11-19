---
title: "50 分金条的最小花费"
layout: page
date: 2019-11-19 23:22
---

[TOC]

# ac

* 经典哈夫曼编码题

```java
import java.util.PriorityQueue;
import java.util.Scanner;

public class Main {

    public static Scanner sc = new Scanner(System.in);

    static int mod = 1_000_000_000 + 7;

    static int N = 100_000;
    static int[] cost = new int[N];
    static int[] profit = new int[N];
    /**
     *
     * @param args
     */
    public static void main(String[] args) {
        int n = sc.nextInt();

        // profit 按从大到小排列
        PriorityQueue<Long> priorityQueue = new PriorityQueue<>((a,b)->{
            if(a < b){
                return -1;
            }else if(a > b){
                return 1;
            }
            return 0;
        });
        for(int i=0;i<n;i++){
            long var = sc.nextInt();
            priorityQueue.add(var);
        }
        long w = 0;
        while (!priorityQueue.isEmpty()){
            if(priorityQueue.size() > 1){
                long p1 = priorityQueue.poll();
                long p2 = priorityQueue.poll();
                long p = p1 + p2;
                w += p;
                priorityQueue.add(p);
            }else {
                break;
            }
        }
        System.out.println(w);
    }


}
/*
3
10 30 20

90

6
3 9 5 2 4 4

67
*/


```
