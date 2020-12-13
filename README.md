# Lab1_AK
# Протокол: Hevelencko_IV-82_Lab1.odt

Граф:  
![Screenshot from 2020-12-13 15-39-43](https://user-images.githubusercontent.com/31134655/102013777-d849d380-3d5a-11eb-998b-6d5b34c3ea1b.png)  

Лістинг фалів:

calcalator.cpp
```
#include "calculator.h"

int Calculator::Add (double a, double b)
{
	return a + b + 0.5;
}

int Calculator::Sub (double a, double b)
{
    return Add (a, -b);
}

int Calculator::Mul (double a, double b)
{
    return a * b + 0.5;
}
```
calculator.h
```
#ifndef CALCULATOR_H
#define CALCULATOR_H

class Calculator
{
    public:
        int Add (double, double);
        int Sub (double, double);
        int Mul (double, double);
        //Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
        //Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
        //Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
        //Excepteur sint occaecat cupidatat non proident, 
        //sunt in culpa qui officia deserunt mollit anim id est laborum.
};

#endif//CALCULATOR_H
```
Патчі: 

0001-fix-truncation-error-rebased.patch
```
From 5aa1d6c584d629ee60f63bf476c3ed2fea398b85 Mon Sep 17 00:00:00 2001
From: Sergii Piatakov <sergii.piatakov@globallogic.com>
Date: Thu, 15 Nov 2018 15:28:04 +0200
Subject: [PATCH] fix truncation error(rebased)

To convert float to integer the truncation is performed, but the
rounding is expected.

Test: Add (4.9, 4.9) should return 10.
Signed-off-by: Nazar Hevelencko
---
 calculator.cpp | 2 +-
 1 file changed, 1 insertion(+), 1 deletion(-)

diff --git a/calculator.cpp b/calculator.cpp
index b91afea..d93e35b 100644
--- a/calculator.cpp
+++ b/calculator.cpp
@@ -2,7 +2,7 @@
 
 int Calculator::Add (double a, double b)
 {
-    return a + b;
+	return a + b + 0.5;
 }
 
 int Calculator::Sub (double a, double b)
-- 
2.25.1
```
0001-formatting-use-tabs-instead-of-spaces-rebased.patch
```
From 048f5c5f5f4b50bc03ef7832f869f24fc0c76457 Mon Sep 17 00:00:00 2001
From: Sergii Piatakov <sergii.piatakov@globallogic.com>
Date: Thu, 15 Nov 2018 15:26:35 +0200
Subject: [PATCH] formatting: use tabs instead of spaces(rebased)

Signed-off-by: Nazar Hevelencko
---
 calculator.cpp | 4 ++--
 calculator.h   | 6 +++---
 2 files changed, 5 insertions(+), 5 deletions(-)

diff --git a/calculator.cpp b/calculator.cpp
index d93e35b..f323e14 100644
--- a/calculator.cpp
+++ b/calculator.cpp
@@ -2,10 +2,10 @@
 
 int Calculator::Add (double a, double b)
 {
-	return a + b + 0.5;
+	return a + b;
 }
 
 int Calculator::Sub (double a, double b)
 {
-    return Add (a, -b);
+	return Add (a, -b);
 }
diff --git a/calculator.h b/calculator.h
index 3740907..d59d596 100644
--- a/calculator.h
+++ b/calculator.h
@@ -3,9 +3,9 @@
 
 class Calculator
 {
-    public:
-        int Add (double, double);
-        int Sub (double, double);
+	public:
+		int Add (double, double);
+		int Sub (double, double);
 };
 
 #endif//CALCULATOR_H
-- 
2.25.1
```
