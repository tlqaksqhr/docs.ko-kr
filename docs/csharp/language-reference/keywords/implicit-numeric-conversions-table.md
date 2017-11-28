---
title: "암시적 숫자 변환 표(C# 참조)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- conversions [C#], implicit numeric
- implicit numeric conversions [C#]
- numeric conversions [C#], implicit
- types [C#], implicit numeric conversions
ms.assetid: 72eb5a94-0491-48bf-8032-d7ebfdfeb8d8
caps.latest.revision: "12"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: f6b1705dca357fd2a155fc1ea9c7fe0f65bad8a7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="implicit-numeric-conversions-table-c-reference"></a>암시적 숫자 변환 표(C# 참조)
다음 표에서는 미리 정의된 암시적 숫자 변환을 보여 줍니다. 암시적 변환은 메서드 호출, 할당 문을 비롯한 대부분의 경우에서 발생할 수 있습니다.  
  
|시작|대상|  
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
|[ulong](../../../csharp/language-reference/keywords/ulong.md)|`float`, `double` 또는 `decimal`|  
  
## <a name="remarks"></a>주의  
  
-   `int`, `uint`, `long` 또는 `ulong`에서 `float`로 변환하고 `long` 또는 `ulong`에서 `double`로 변환하는 동안 전체 자릿수가 손실될 수도 있지만 크기는 손실되지 않습니다.  
  
-   `char` 형식으로의 암시적 변환은 없습니다.  
  
-   부동 소수점 형식과 `decimal` 형식 간의 암시적 변환은 없습니다.  
  
-   상수 식의 값이 대상 형식의 범위 내에 있는 경우 `int` 형식의 상수 식을 `sbyte`, `byte`, `short`, `ushort`, `uint` 또는 `ulong`으로 변환할 수 있습니다.  
  
## <a name="c-language-specification"></a>C# 언어 사양  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [C# 참조](../../../csharp/language-reference/index.md)  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
 [정수 계열 형식 표](../../../csharp/language-reference/keywords/integral-types-table.md)  
 [기본 제공 형식 표](../../../csharp/language-reference/keywords/built-in-types-table.md)  
 [명시적 숫자 변환 표](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)  
 [캐스팅 및 형식 변환](../../../csharp/programming-guide/types/casting-and-type-conversions.md)
