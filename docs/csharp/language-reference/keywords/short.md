---
title: "short(C# 참조) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "short"
  - "short_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "short 키워드[C#]"
ms.assetid: 04c10688-e51a-4a87-bfec-83f7fb42ff11
caps.latest.revision: 17
caps.handback.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# short(C# 참조)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

`short` 키워드는 다음 표에 표시된 크기와 범위에 따라 값을 저장하는 정수 계열 데이터 형식을 나타냅니다.  
  
|형식|범위|크기|.NET Framework 형식|  
|--------|--------|--------|-----------------------|  
|`short`|\-32,768 ~ 32,767|부호 있는 16비트 정수|<xref:System.Int16?displayProperty=fullName>|  
  
## 리터럴  
 다음 예제에서와 같이 `short` 변수를 선언하고 초기화할 수 있습니다.  
  
```  
  
short x = 32767;  
```  
  
 앞의 선언에서 정수 리터럴 `32767`은 암시적으로 [int](../../../csharp/language-reference/keywords/int.md)에서 `short`로 변환됩니다.  정수 리터럴이 `short` 저장소 위치에 맞지 않는 경우 컴파일 오류가 발생합니다.  
  
 오버로드된 메서드를 호출하는 경우 캐스트를 사용해야 합니다.  예를 들어 다음과 같이 `short` 및 [int](../../../csharp/language-reference/keywords/int.md) 매개 변수를 사용하는 오버로드된 메서드가 있습니다.  
  
```  
public static void SampleMethod(int i) {}  
public static void SampleMethod(short s) {}  
```  
  
 이 경우, `short` 캐스트를 사용하면 올바른 형식이 호출됩니다. 예를 들면 다음과 같습니다.  
  
```  
SampleMethod(5);         // Calling the method with the int parameter  
SampleMethod((short)5);  // Calling the method with the short parameter  
```  
  
## 변환  
 `short`에서 [int](../../../csharp/language-reference/keywords/int.md), [long](../../../csharp/language-reference/keywords/long.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) 또는 [decimal](../../../csharp/language-reference/keywords/decimal.md)로의 미리 정의된 암시적 변환이 있습니다.  
  
 저장 크기가 더 큰 비 리터럴 숫자 형식은 암시적으로 `short`로 변환할 수 없습니다. 정수 계열 형식의 저장 크기에 대해서는 [정수 계열 형식 표](../../../csharp/language-reference/keywords/integral-types-table.md)를 참조하십시오.  예를 들어, 다음과 같은 두 개의 `short` 변수 `x` 및 `y`가 있습니다.  
  
```  
  
short x = 5, y = 12;  
```  
  
 이 경우, 다음 대입문에서는 컴파일 오류가 발생합니다. 그 이유는 대입 연산자의 오른쪽에 있는 산술식이 기본적으로 [int](../../../csharp/language-reference/keywords/int.md)로 계산되기 때문입니다.  
  
 `short`   `z = x + y;   // Error: no conversion from int to short`  
  
 이 문제를 해결하려면 캐스트를 사용하십시오.  
  
 `short`   `z = (`  `short`  `)(x + y);   // OK: explicit conversion`  
  
 대상 변수의 저장소 크기가 같거나 더 클 경우에는 다음과 같은 문을 사용할 수 있습니다.  
  
```  
int m = x + y;  
long n = x + y;  
```  
  
 부동 소수점 형식에서 `short`로의 암시적 변환은 없습니다.  예를 들어, 다음 문에서 명시적 캐스트를 사용하지 않으면 컴파일러 오류가 발생합니다.  
  
```  
  
        short x = 3.0;          // Error: no implicit conversion from double  
short y = (short)3.0;   // OK: explicit conversion  
```  
  
 부동 소수점 형식 및 정수 계열 형식이 함께 사용되는 산술식에 대한 내용은 [double](../../../csharp/language-reference/keywords/double.md) 및 [float](../../../csharp/language-reference/keywords/float.md)을 참조하십시오.  
  
 암시적 숫자 변환 규칙에 대한 자세한 내용은 [암시적 숫자 변환 표](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)를 참조하십시오.  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## 참고 항목  
 <xref:System.Int16>   
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\# 키워드](../../../csharp/language-reference/keywords/index.md)   
 [정수 계열 형식 표](../../../csharp/language-reference/keywords/integral-types-table.md)   
 [기본 제공 형식 표](../../../csharp/language-reference/keywords/built-in-types-table.md)   
 [암시적 숫자 변환 표](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)   
 [명시적 숫자 변환 표](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)