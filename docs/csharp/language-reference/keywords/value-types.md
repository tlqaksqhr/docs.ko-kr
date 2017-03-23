---
title: "값 형식(C# 참조) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "cs.valuetypes"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "C# 언어, 값 형식"
  - "형식[C#], 값 형식"
  - "값 형식[C#]"
ms.assetid: 471eb994-2958-49d5-a6be-19b4313f80a3
caps.latest.revision: 18
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 18
---
# 값 형식(C# 참조)
값 형식은 다음과 같은 두 개의 기본 범주로 구성됩니다.  
  
-   [Structs](../../../csharp/language-reference/keywords/struct.md)  
  
-   [열거형](../../../csharp/language-reference/keywords/enum.md)  
  
 구조체는 다음과 같은 범주로 구분할 수 있습니다.  
  
-   숫자 형식  
  
    -   [정수 계열 형식 표](../../../csharp/language-reference/keywords/integral-types-table.md)  
  
    -   [부동 소수점 형식 표](../../../csharp/language-reference/keywords/floating-point-types-table.md)  
  
    -   [decimal](../../../csharp/language-reference/keywords/decimal.md)  
  
-   [bool](../../../csharp/language-reference/keywords/bool.md)  
  
-   사용자 정의 구조체  
  
## 값 형식의 기본 기능  
 값 형식을 기반으로 한 변수에는 값이 직접 포함됩니다.  값 형식 변수 하나를 다른 변수에 대입하면 변수에 포함된 값이 복사됩니다.  이는 참조 형식 변수를 대입하는 경우와 다릅니다. 참조 형식 변수의 경우 개체 자체가 아니라 개체에 대한 참조가 복사됩니다.  
  
 모든 값 형식은 암시적으로 <xref:System.ValueType?displayProperty=fullName>에서 파생됩니다.  
  
 참조 형식과 달리 값 형식에서는 새 형식을 파생시킬 수 없습니다.  그러나 구조체는 참조 형식과 마찬가지로 인터페이스를 구현할 수 있습니다.  
  
 참조 형식과 달리 값 형식에는 `null` 값이 포함될 수 없습니다.  그러나의  [nullable 형식](../../../csharp/programming-guide/nullable-types/index.md) 은 기능에 할당 될 값 형식에 대해 허용 하지 `null`.  
  
 각 값 형식에는 해당 형식의 기본값을 초기화하는 암시적 기본 생성자가 있습니다.  값 형식의 기본값에 대한 자세한 내용은 [기본값 표](../../../csharp/language-reference/keywords/default-values-table.md)를 참조하십시오.  
  
## 단순 형식의 기본 기능  
 C\# 언어에서 중요한 부분을 차지하는 모든 단순 형식은 .NET Framework 시스템 형식의 별칭입니다.  예를 들어, [int](../../../csharp/language-reference/keywords/int.md)는 <xref:System.Int32?displayProperty=fullName>의 별칭입니다.  전체 별칭 목록은 [기본 제공 형식 표](../../../csharp/language-reference/keywords/built-in-types-table.md)를 참조하십시오.  
  
 상수 식의 피연산자가 모두 단순 형식 상수인 경우 컴파일할 때 해당 상수 식이 계산됩니다.  
  
 단순 형식은 리터럴을 사용하여 초기화할 수 있습니다.  예를 들어, 'A'는 `char` 형식의 리터럴이며 2001은 `int` 형식의 리터럴입니다.  
  
## 값 형식 초기화  
 C\#의 지역 변수는 사용하기 전에 초기화해야 합니다.  예를 들어 다음 예제와 같이 지역 변수를 초기화하지 않고 선언한 경우  
  
```  
int myInt;  
```  
  
 이 지역 변수는 초기화하기 전에는 사용할 수 없습니다.  다음 문을 사용하여 이 지역 변수를 초기화할 수 있습니다.  
  
```  
myInt = new int();  // Invoke default constructor for int type.  
```  
  
 이 문은 다음 문과 동일한 결과를 가져옵니다.  
  
```  
myInt = 0;         // Assign an initial value, 0 in this example.  
```  
  
 물론 다음 예제와 같이 하나의 문으로 선언과 초기화를 수행할 수도 있습니다.  
  
```  
int myInt = new int();  
```  
  
 – 또는 –  
  
```  
int myInt = 0;  
```  
  
 [new](../../../csharp/language-reference/keywords/new.md) 연산자를 사용하면 특정 형식의 기본 생성자를 호출하여 해당 변수에 기본값을 할당할 수 있습니다.  앞의 예제에서 기본 생성자는 `myInt`에 `0` 값을 할당합니다.  기본 생성자를 호출하여 할당되는 값에 대한 자세한 내용은 [기본값 표](../../../csharp/language-reference/keywords/default-values-table.md)를 참조하십시오.  
  
 사용자 정의 형식에 [new](../../../csharp/language-reference/keywords/new.md)를 사용하여 기본 생성자를 호출할 수 있습니다.  예를 들어, 다음 문은 `Point` 구조체의 기본 생성자를 호출합니다.  
  
```  
Point p = new Point(); // Invoke default constructor for the struct.  
```  
  
 이 호출 후 구조체는 명확하게 할당됩니다. 즉, 구조체의 모든 멤버가 기본값으로 초기화됩니다.  
  
 new 연산자에 대한 자세한 내용은 [new](../../../csharp/language-reference/keywords/new.md)를 참조하십시오.  
  
 숫자 형식 출력의 형식 지정에 대한 자세한 내용은 [숫자 결과 형식 지정 표](../../../csharp/language-reference/keywords/formatting-numeric-results-table.md)를 참조하십시오.  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\# 키워드](../../../csharp/language-reference/keywords/index.md)   
 [형식](../../../csharp/language-reference/keywords/types.md)   
 [형식 참조 테이블](../../../csharp/language-reference/keywords/reference-tables-for-types.md)   
 [참조 형식](../../../csharp/language-reference/keywords/reference-types.md)