---
layout: post
title:  "[코드트리 후기] 2회차 - 시뮬레이션 연습"
date:   2026-05-18 23:23:10 +0900
categories: 알고리즘
tags: ["코드트리", "코딩테스트", "코테공부", "시뮬레이션", "알고리즘공부", "코드기초"]
---
코드트리 청약 챌린지 2주차에 대한 후기를 남겨보려고 한다.

먼저, Trail2 시뮬레이션부터 차근차근 학습하려고 했다. 이번주에는 날짜와 시간 계산 레슨을 해결했다
![코드트리 날짜와 시간 계산 레슨](/assets/img/blog/codetree2-1.png)

코드트리 문제를 풀며 가장 좋았던 것은 개념에 대한 설명이 있고 해설이 나와있다는 것이다.
다른 문제 풀이 사이트를 보면 문제만 나와있을 뿐 해설이 없어 어떤 해설이 가장 좋은 것인지 궁금할 때가 많았는데 
코드트리에서는 정해를 제공해줘서 좋은 것 같다. 

이번주 레슨에서 가장 어려웠던 것은 난이도 "Hard"로 측정된 요일 맞추기 문제였다. 
요일과 하루 차이나는게 전날일 수도 있고 그 다음날일 수도 있어 계산을 어떻게 해야 하는지 헷갈렸다. 
날짜 차이가 음수로 나왔을 때 인덱스를 어떻게 처리해야 하는지에 대한 고민이 가장 컸던 것 같다. 
```java
import java.util.*;

public class Main {
    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);
        int m1 = sc.nextInt();
        int d1 = sc.nextInt();
        int m2 = sc.nextInt();
        int d2 = sc.nextInt();

        int[] days = new int[]{
            31, 28, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31
        };

        int startDays = 0;
        // 날짜 수 계산 
        for (int i = 0; i < m1 - 1; i++) {
            startDays += days[i];
        }
        startDays += d1;

        int endDays = 0;
        for (int i = 0; i < m2 - 1; i++) {
            endDays += days[i];
        }
        endDays += d2;

        int dateDiff = endDays - startDays;

        String[] dayPrint = new String[]{
            "Mon",
            "Tue",
            "Wed",
            "Thu",
            "Fri",
            "Sat",
            "Sun",
        };
        String answer = "";
        int index = ((dateDiff % 7) + 7) % 7;
        answer = dayPrint[index];
        System.out.println(answer);
    }
}
```

이 문제에 대한 코드다. 확실히 개념, 연습, 테스트까지 하니 이 유형에 대해 정확히 짚고 넘어갔다는 생각이 든다. 
그 전에는, 내가 문제를 많이 풀어도 효율적으로 푸는 것일까에 대한 고민이 있었는데 코드트리를 계속 학습하다 보면 
빠르게 성장할 수 있을 거라고 생각한다.

	
[코드트리](https://www.codetree.ai/ko/trail-info).