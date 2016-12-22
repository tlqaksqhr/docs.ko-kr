---
title: "암시적 숫자 변환 표(C# 참조) | Microsoft Docs"
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
  - "변환[C#], 암시적 숫자"
  - "암시적 숫자 변환[C#]"
  - "숫자 변환[C#], implicit"
  - "형식[C#], 암시적 숫자 변환"
ms.assetid: 72eb5a94-0491-48bf-8032-d7ebfdfeb8d8
caps.latest.revision: 12
caps.handback.revision: 12
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 암시적 숫자 변환 표(C# 참조)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

다음 표에서는 미리 정의된 암시적 숫자 변환을 보여 줍니다.  메서드 호출, 할당문 등 많은 경우에 암시적 변환이 발생할 수 있습니다.  
  
|From|To|  
|----------|--------|  
|[sbyte](../../../csharp/language-reference/keywords/sbyte.md)|`short`, `int`, `long`, `float`, `double` 또는 `decimal`|  
|[byte](../../../csharp/language-reference/keywords/byte.md)|`short`, `ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double` 또는 `decimal`|  
|[short](../../../csharp/language-reference/keywords/short.md)|`int`, `long`, `float`, `double` 또는 `decimal`|  
|[ushort](../../../csharp/language-reference/keywords/ushort.md)|`int`, `uint`, `long`, `ulong`, `float`, `double` 또는 `decimal`|  
|[int](../../../csharp/language-reference/keywords/int.md)|`long`, `float`, `double` 또는 `decimal`|  
|[uint](../../../csharp/language-reference/keywords/uint.md)|`long`, `ulong`, `float`, `double` 또는 `decimal`|  
|[long](../../../csharp/language-reference/keywords/long.md)|`float`, `double` 또는 `decimal`|  
|[char](../../../csharp/language-reference/keywords/char.md)|`ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double` 또는 `decimal`|  
|[float](../../../csharp/language-reference/keywords/float.md)|`double`|  
|[ulong](../../../csharp/language-reference/keywords/ulong.md)|`float`,  `double` 또는 `decimal`|  
  
## 설명  
  
-   정밀도 있지만 않은 강도 있습니다 수 손실에서 변환에 `int`, `uint`, `long`, 또는 `ulong` 에 `float` 에서 `long` 또는 `ulong` 에 `double`.  
  
-   `char` 형식으로의 암시적 변환은 없습니다.  
  
-   부동 소수점 형식과 `decimal` 형식 사이의 암시적 변환은 없습니다.  
  
-   상수 식의 값이 대상 형식의 범위에 있는 경우 `int` 형식의 상수 식을 `sbyte`, `byte`, `short`, `ushort`, `uint` 또는 `ulong`으로 변환할 수 있습니다.  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [정수 계열 형식 표](../../../csharp/language-reference/keywords/integral-types-table.md)   
 [기본 제공 형식 표](../../../csharp/language-reference/keywords/built-in-types-table.md)   
 [명시적 숫자 변환 표](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)   
 [캐스팅 및 형식 변환\(C\#\)](../../../csharp/programming-guide/types/casting-and-type-conversions.md)