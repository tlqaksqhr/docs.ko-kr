---
title: "ushort(C# 참조) | Microsoft Docs"
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
  - "ushort"
  - "ushort_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "ushort 키워드[C#]"
ms.assetid: 1a7dbaae-b7a0-4111-872a-c88a6d3981ac
caps.latest.revision: 16
caps.handback.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# ushort(C# 참조)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

`ushort` 키워드는 다음 표에 표시된 크기와 범위에 따라 값을 저장하는 정수 계열 데이터 형식을 나타냅니다.  
  
|형식|범위|크기|.NET Framework 형식|  
|--------|--------|--------|-----------------------|  
|`ushort`|0 ~ 65,535|부호 없는 16비트 정수|<xref:System.UInt16?displayProperty=fullName>|  
  
## 리터럴  
 다음 예제와 같이 `ushort` 변수를 선언하고 초기화할 수 있습니다.  
  
```  
  
ushort myShort = 65535;  
```  
  
 앞의 선언에서 정수 리터럴 `65535`는 암시적으로 [int](../../../csharp/language-reference/keywords/int.md)에서 `ushort`로 변환됩니다.  정수 리터럴이 `ushort` 범위를 초과하면 컴파일 오류가 발생합니다.  
  
 오버로드된 메서드를 호출할 경우 캐스트를 사용해야 합니다.  예를 들어 다음과 같이 `ushort` 및 [int](../../../csharp/language-reference/keywords/int.md) 매개 변수를 사용하는 오버로드된 메서드가 있습니다.  
  
```  
public static void SampleMethod(int i) {}  
public static void SampleMethod(ushort s) {}  
```  
  
 이 경우, `ushort` 캐스트를 사용하면 올바른 형식이 호출됩니다. 예를 들면 다음과 같습니다.  
  
```  
// Calls the method with the int parameter:  
SampleMethod(5);  
// Calls the method with the ushort parameter:  
SampleMethod((ushort)5);    
```  
  
## 변환  
 `ushort`에서 [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) 또는 [decimal](../../../csharp/language-reference/keywords/decimal.md)로의 미리 정의된 암시적 변환이 있습니다.  
  
 또한 [byte](../../../csharp/language-reference/keywords/byte.md)나 [char](../../../csharp/language-reference/keywords/char.md)에서 `ushort`로의 미리 정의된 암시적 변환이 있습니다.  그 외의 다른 경우에는 캐스트를 사용하여 명시적 변환을 수행해야 합니다.  예를 들어, 다음과 같은 두 개의 `ushort` 변수 `x` 및 `y`가 있습니다.  
  
```  
  
ushort x = 5, y = 12;  
```  
  
 다음 할당문의 경우 할당 연산자의 오른쪽에 있는 산술식이 기본적으로 `int`로 계산되므로 컴파일 오류가 발생합니다.  
  
```  
  
ushort z = x + y;   // Error: conversion from int to ushort  
```  
  
 이 문제를 해결하려면 캐스트를 사용하십시오.  
  
```  
  
ushort z = (ushort)(x + y);   // OK: explicit conversion   
```  
  
 대상 변수의 저장소 크기가 같거나 더 클 경우에는 다음과 같은 문을 사용할 수 있습니다.  
  
```  
int m = x + y;  
long n = x + y;  
```  
  
 또한 부동 소수점 형식에서 `ushort`로의 암시적 변환은 없습니다.  예를 들어, 다음 문에서 명시적 캐스트를 사용하지 않으면 컴파일러 오류가 발생합니다.  
  
```  
// Error -- no implicit conversion from double:  
ushort x = 3.0;   
// OK -- explicit conversion:  
ushort y = (ushort)3.0;  
```  
  
 부동 소수점 형식 및 정수 계열 형식이 함께 사용되는 산술식에 대한 자세한 내용은 [float](../../../csharp/language-reference/keywords/float.md) 및 [double](../../../csharp/language-reference/keywords/double.md)을 참조하십시오.  
  
 암시적 숫자 변환 규칙에 대한 자세한 내용은 [암시적 숫자 변환 표](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)를 참조하십시오.  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## 참고 항목  
 <xref:System.UInt16>   
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\# 키워드](../../../csharp/language-reference/keywords/index.md)   
 [정수 계열 형식 표](../../../csharp/language-reference/keywords/integral-types-table.md)   
 [기본 제공 형식 표](../../../csharp/language-reference/keywords/built-in-types-table.md)   
 [암시적 숫자 변환 표](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)   
 [명시적 숫자 변환 표](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)