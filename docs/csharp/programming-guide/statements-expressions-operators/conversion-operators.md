---
title: "변환 연산자(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "C# 언어, 변환 연산자"
  - "변환 연산자[C#]"
  - "연산자[C#], 변환"
  - "사용자 정의 변환[C#]"
ms.assetid: c5ad73a3-d57b-4d2b-b4c9-24e3c2856efc
caps.latest.revision: 22
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 22
---
# 변환 연산자(C# 프로그래밍 가이드)
C\#에서는 클래스나 구조체를 다른 클래스나 구조체 또는 기본 형식으로 변환할 수 있도록 프로그래머가 클래스나 구조체에 대한 변환을 선언할 수 있습니다.  변환은 연산자처럼 정의되며 변환될 형식으로 명명됩니다.  변환할 인수 형식이나 변환의 결과 형식 중 하나는 포함하는 형식이어야 합니다.  
  
 [!code-cs[csProgGuideStatements#10](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/conversion-operators_1.cs)]  
  
## 변환 연산자 개요  
 변환 연산자에는 다음과 같은 속성이 있습니다.  
  
-   `implicit`으로 선언된 변환은 필요 시 자동으로 수행됩니다.  
  
-   `explicit`으로 선언된 변환은 캐스팅을 사용하여 호출해야 합니다.  
  
-   모든 변환은 `static`으로 선언되어야 합니다.  
  
## 관련 단원  
 자세한 내용은 다음을 참조하십시오.  
  
-   [변환 연산자 사용](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md)  
  
-   [캐스팅 및 형식 변환\(C\#\)](../../../csharp/programming-guide/types/casting-and-type-conversions.md)  
  
-   [방법: 구조체 간의 사용자 정의 변환 구현](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)  
  
-   [explicit](../../../csharp/language-reference/keywords/explicit.md)  
  
-   [implicit](../../../csharp/language-reference/keywords/implicit.md)  
  
-   [static](../../../csharp/language-reference/keywords/static.md)  
  
## 참고 항목  
 <xref:System.Convert>   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [명시적 사용자 정의 변환 C\#에 연결 된](http://go.microsoft.com/fwlink/?LinkId=112384)