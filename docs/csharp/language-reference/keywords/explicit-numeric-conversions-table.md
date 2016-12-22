---
title: "명시적 숫자 변환 표(C# 참조) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "변환[C#], 명시적 숫자"
  - "명시적 숫자 변환[C#]"
  - "숫자 변환[C#], explicit"
  - "숫자 데이터 형식[C#]"
  - "형식 변환[C#], 명시적 숫자"
  - "형식[C#], 명시적 숫자 변환"
ms.assetid: f3bb9e76-6b92-4df7-bc36-f866c24e1dfd
caps.latest.revision: 14
caps.handback.revision: 14
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 명시적 숫자 변환 표(C# 참조)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

숫자 형식 간에 암시적 변환이 없는 경우, 임의의 숫자 형식을 다른 숫자 형식으로 변환하기 위해 캐스트 식을 사용하여 명시적 숫자 변환을 수행합니다.  다음 표에서는 이러한 변환을 보여 줍니다.  
  
 변환에 대한 자세한 내용은 [캐스팅 및 형식 변환\(C\#\)](../../../csharp/programming-guide/types/casting-and-type-conversions.md)를 참조하십시오.  
  
|From|To|  
|----------|--------|  
|[sbyte](../../../csharp/language-reference/keywords/sbyte.md)|`byte`, `ushort`, `uint`, `ulong` 또는 `char`|  
|[byte](../../../csharp/language-reference/keywords/byte.md)|`Sbyte` 또는 `char`|  
|[short](../../../csharp/language-reference/keywords/short.md)|`sbyte`, `byte`, `ushort`, `uint`, `ulong` 또는 `char`|  
|[ushort](../../../csharp/language-reference/keywords/ushort.md)|`sbyte`,  `byte`,  `short` 또는  `char`|  
|[int](../../../csharp/language-reference/keywords/int.md)|`sbyte`, `byte`, `short`, `ushort`, `uint`, `ulong` ``  또는 `char`|  
|[uint](../../../csharp/language-reference/keywords/uint.md)|`sbyte`, `byte`, `short`, `ushort`, `int` 또는 `char`|  
|[long](../../../csharp/language-reference/keywords/long.md)|`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `ulong` 또는 `char`|  
|[ulong](../../../csharp/language-reference/keywords/ulong.md)|`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long` 또는 `char`|  
|[char](../../../csharp/language-reference/keywords/char.md)|`sbyte`, `byte` 또는  `short`|  
|[float](../../../csharp/language-reference/keywords/float.md)|`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char` ``  또는 `decimal`|  
|[double](../../../csharp/language-reference/keywords/double.md)|`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`, `float`  ``  또는 `decimal`|  
|[decimal](../../../csharp/language-reference/keywords/decimal.md)|`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`, `float` 또는 `double`|  
  
## 설명  
  
-   명시적 숫자 변환으로 정밀도가 손실되거나 예외가 throw될 수 있습니다.  
  
-   `decimal` 값을 정수 계열 형식으로 변환할 경우 이 값은 0에 가장 가까운 정수 계열 값으로 반올림됩니다.  결과로 나타난 정수 계열 값이 대상 형식의 범위를 초과하는 경우 <xref:System.OverflowException>이 throw됩니다.  
  
-   `double` 또는 `float` 값을 정수 계열 형식으로 변환하면 값이 잘립니다.  결과 정수 계열 값이 대상 값의 범위를 벗어나는 경우 오버플로 검사 컨텍스트에 따라 결과가 다릅니다.  검사된 컨텍스트에서는 `OverflowException`이 throw되지만 검사되지 않은 컨텍스트에서는 결과가 대상 형식의 지정되지 않은 값입니다.  
  
-   `double`을 `float`로 변환하는 경우 `double` 값은 가장 근사치의 `float` 값으로 반올림됩니다.  `double` 값이 너무 작거나 커서 대상 형식에 맞지 않는 경우 결과는 0이 되거나 무한대가 됩니다.  
  
-   `float` 또는 `double`을 `decimal`로 변환하는 경우 소스 값은 `decimal` 형식으로 변환되며 필요한 경우 28번째 소수 자리수 아래는 가장 가까운 수로 반올림됩니다.  원본 값의 값에 따라 다음과 같은 결과가 발생할 수 있습니다.  
  
    -   원본 값이 너무 작아 `decimal`로 나타낼 수 없는 경우 결과는 0이 됩니다.  
  
    -   원본 값이 NaN\(숫자 아님\) 또는 무한대이거나 너무 커서 `decimal`로 나타낼 수 없는 경우 `OverflowException`이 throw됩니다.  
  
-   `decimal`을 `float` 또는 `double`로 변환하는 경우 `decimal` 값은 가장 가까운 `double` 또는 `float` 값으로 반올림됩니다.  
  
 명시적 변환에 대한 자세한 내용은 C\# 언어 사양의 명시적 변환을 참조하십시오.  사양에 액세스하는 방법에 대한 자세한 내용은 [C\# 언어 사양](../../../visual-basic/reference/language-specification.md)을 참조하십시오.  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [캐스팅 및 형식 변환\(C\#\)](../../../csharp/programming-guide/types/casting-and-type-conversions.md)   
 [\(\) 연산자](../../../csharp/language-reference/operators/invocation-operator.md)   
 [정수 계열 형식 표](../../../csharp/language-reference/keywords/integral-types-table.md)   
 [기본 제공 형식 표](../../../csharp/language-reference/keywords/built-in-types-table.md)   
 [암시적 숫자 변환 표](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)