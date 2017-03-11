---
title: "방법: 연산자 오버로딩을 사용하여 복소수 클래스 만들기(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "클래스[C#], 연산자 오버로드"
  - "복소수[C#]"
  - "연산자 오버로드[C#], 복소수"
  - "연산자 오버로드[C#], 클래스를 만드는 데 사용"
  - "연산자[C#], 복소수 클래스를 만들기 위해 오버로드"
ms.assetid: c9b8d982-5112-413f-bae3-b42ae3248ddf
caps.latest.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 15
---
# 방법: 연산자 오버로딩을 사용하여 복소수 클래스 만들기(C# 프로그래밍 가이드)
다음 예제에서는 연산자 오버로드를 사용하여 복잡한 더하기를 정의하는 복잡한 수 클래스 `Complex`를 만드는 방법을 보여 줍니다.  프로그램에서는 `ToString` 메서드를 재정의하여 수의 실제 부분과 가상 부분 및 더하기 결과를 표시합니다.  
  
## 예제  
 [!code-cs[csProgGuideStatements#16](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/how-to-use-operator-over_1.cs)]  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\# 연산자](../../../csharp/language-reference/operators/index.md)   
 [operator](../../../csharp/language-reference/keywords/operator.md)   
 [Why are overloaded operators always static in C\#?](http://go.microsoft.com/fwlink/?LinkId=112383)