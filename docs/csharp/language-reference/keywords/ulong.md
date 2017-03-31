---
title: "ulong(C# 참조) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ulong_CSharpKeyword
- ulong
dev_langs:
- CSharp
helpviewer_keywords:
- ulong keyword [C#]
ms.assetid: f2ece624-837a-40cf-92c5-343e7f33397c
caps.latest.revision: 16
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 36de0add1d7fdf58745c65d231f3789c532ab69f
ms.lasthandoff: 03/13/2017

---
# <a name="ulong-c-reference"></a>ulong(C# 참조)
`ulong` 키워드는 다음 표에 나와 있는 크기와 범위에 따라 값을 저장하는 정수 형식을 나타냅니다.  
  
|형식|범위|크기|.NET Framework 형식|  
|----------|-----------|----------|-------------------------|  
|`ulong`|0 ~ 18,446,744,073,709,551,615|부호 없는 64비트 정수|<xref:System.UInt64?displayProperty=fullName>|  
  
## <a name="literals"></a>리터럴  
 다음 예제와 같이 `ulong` 변수를 선언하고 초기화할 수 있습니다.  
  
```  
  
ulong uLong = 9223372036854775808;  
```  
  
 정수 리터럴에 접미사가 없는 경우 해당 형식은 [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), `ulong` 등 값이 표현될 수 있는 형식의 첫 번째입니다. 위의 예제에서는 `ulong` 형식입니다.  
  
 접미사를 사용하여 다음 규칙에 따라 리터럴 형식을 지정할 수도 있습니다.  
  
-   L 또는 l을 사용하는 경우 리터럴 정수 형식은 크기에 따라 [long](../../../csharp/language-reference/keywords/long.md) 또는 `ulong` 중 하나가 됩니다.  
  
    > [!NOTE]
    >  소문자 "l"을 접미사로 사용할 수 있습니다. 그러나 이렇게 하면 문자 "l"과 숫자 "1"을 혼동하기 쉬우므로 컴파일러 경고가 생성됩니다. 쉽게 구별할 수 있도록 "L"을 사용합니다.  
  
-   `U` 또는 `u`를 사용하는 경우 리터럴 정수 형식은 크기에 따라 [uint](../../../csharp/language-reference/keywords/uint.md) 또는 `ulong` 중 하나가 됩니다.  
  
-   UL, ul, Ul, uL, LU, lu, Lu 또는 lU를 사용하는 경우 리터럴 정수의 형식은 `ulong`이 됩니다.  
  
     예를 들어 다음 세 문의 출력은 별칭 `ulong`에 해당하는 시스템 형식 `UInt64`가 됩니다.  
  
    ```  
    Console.WriteLine(9223372036854775808L.GetType());  
    Console.WriteLine(123UL.GetType());  
    Console.WriteLine((123UL + 456).GetType());  
    ```  
  
 접미사는 일반적으로 오버로드된 메서드를 호출할 때 사용됩니다. 예를 들어 `ulong` 및 [int](../../../csharp/language-reference/keywords/int.md) 매개 변수를 사용하는 다음의 오버로드된 메서드를 살펴보세요.  
  
```  
public static void SampleMethod(int i) {}  
public static void SampleMethod(ulong l) {}  
```  
  
 `ulong` 매개 변수와 함께 접미사를 사용하면 올바른 형식이 호출됩니다. 예를 들면 다음과 같습니다.  
  
```  
SampleMethod(5);    // Calling the method with the int parameter  
SampleMethod(5UL);  // Calling the method with the ulong parameter  
```  
  
## <a name="conversions"></a>변환  
 `ulong`에서 [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) 또는 [decimal](../../../csharp/language-reference/keywords/decimal.md)로 미리 정의된 암시적 변환이 있습니다.  
  
 `ulong`에서 정수 형식으로의 암시적 변환은 없습니다. 예를 들어 다음 문은 명시적 캐스트 없이 컴파일 오류를 생성합니다.  
  
```  
long long1 = 8UL;   // Error: no implicit conversion from ulong  
```  
  
 [byte](../../../csharp/language-reference/keywords/byte.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [uint](../../../csharp/language-reference/keywords/uint.md) 또는 [char](../../../csharp/language-reference/keywords/char.md)에서 `ulong`으로 미리 정의된 암시적 변환이 있습니다.  
  
 또한 부동 소수점 형식에서 `ulong`로의 암시적 변환은 없습니다. 예를 들어 명시적 캐스트를 사용하지 않는 경우 다음 문은 컴파일러 오류를 일으킵니다.  
  
```  
// Error -- no implicit conversion from double:  
ulong x = 3.0;  
// OK -- explicit conversion:  
ulong y = (ulong)3.0;    
```  
  
 부동 소수점 형식 및 정수 형식이 혼합된 산술 식에 대한 자세한 내용은 [float](../../../csharp/language-reference/keywords/float.md) 및 [double](../../../csharp/language-reference/keywords/double.md)을 참조하세요.  
  
 암시적 숫자 변환 규칙에 대한 자세한 내용은 [암시적 숫자 변환 표](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)를 참조하세요.  
  
## <a name="c-language-specification"></a>C# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.UInt64>   
 [C# 참조](../../../csharp/language-reference/index.md)   
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C# 키워드](../../../csharp/language-reference/keywords/index.md)   
 [정수 형식 표](../../../csharp/language-reference/keywords/integral-types-table.md)   
 [기본 제공 형식 표](../../../csharp/language-reference/keywords/built-in-types-table.md)   
 [암시적 숫자 변환 표](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)   
 [명시적 숫자 변환 표](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
