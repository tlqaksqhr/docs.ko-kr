---
title: long(C# 참조)
ms.date: 03/14/2017
f1_keywords:
- long_CSharpKeyword
- long
helpviewer_keywords:
- long keyword [C#]
ms.assetid: f9b24319-1f39-48be-a42b-d528ee28a7fd
ms.openlocfilehash: 106b832801a373ca387be455ef1c0df4233621d0
ms.sourcegitcommit: 60645077dc4b62178403145f8ef691b13ffec28e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37961341"
---
# <a name="long-c-reference"></a>long(C# 참조)

`long`은 다음 표에 나와 있는 크기와 범위에 따라 값을 저장하는 정수 형식을 나타냅니다.  
  
|형식|범위|크기|.NET 형식|  
|----------|-----------|----------|-------------------------|  
|`long`|–9,223,372,036,854,775,808 ~ 9,223,372,036,854,775,807|부호 있는 64비트 정수|<xref:System.Int64?displayProperty=nameWithType>|  
  
## <a name="literals"></a>리터럴 

10진수 리터럴, 16진수 리터럴 또는 (C# 7.0부터) 이진 리터럴을 할당하여 `long` 변수를 선언하고 초기화할 수 있습니다. 

다음 예제에서는 10진수, 16진수 및 이진 리터럴로 표현된 4,294,967,296과 같은 정수가 `long` 값에 할당됩니다.  
  
[!code-csharp[long](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#Long)]  

> [!NOTE] 
> `0x` 또는 `0X` 접두사를 사용하여 16진수 리터럴을 나타내고, `0b` 또는 `0B` 접두사를 사용하여 이진 리터럴을 나타냅니다. 10진수 리터럴에는 접두사가 없습니다. 

C# 7.0부터 가독성 향상을 위해 몇 가지 기능이 추가됐습니다. 
 - C# 7.0은 숫자 구분 기호로 밑줄 문자 `_`를 사용할 수 있습니다.
 - C# 7.2는 접두사 뒤에 이진 또는 16진수 리터럴에 대한 자리 구분 기호로 `_`을 사용할 수 있습니다. 10진수 리터럴에 선행 밑줄이 있는 것이 허용되지 않습니다.

일부 예제는 다음과 같습니다.

[!code-csharp[long](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#LongS)]  
 
 형식을 나타내는 접미사가 정수 리터럴에 포함되어 있을 수도 있습니다. `L` 접미사는 `long`을 나타냅니다. 다음 예제에서는 `L` 접미사를 사용하여 정수(long)를 나타냅니다.
 
```csharp
long value = 4294967296L;  
```  

> [!NOTE]
>  소문자 "l"을 접미사로 사용할 수도 있습니다. 그러나 이렇게 하면 문자 "l"과 숫자 "1"을 혼동하기 쉬우므로 컴파일러 경고가 생성됩니다. 쉽게 구별할 수 있도록 "L"을 사용합니다.  
  
 `L` 접미사를 사용하는 경우 리터럴 정수의 형식은 해당 크기에 따라 `long` 또는 [ulong](../../../csharp/language-reference/keywords/ulong.md)으로 결정됩니다. 이 경우 [ulong](../../../csharp/language-reference/keywords/ulong.md)의 범위보다 작기 때문에 `long`입니다.  
  
 접미사는 일반적으로 오버로드된 메서드를 호출할 때 사용됩니다. 예를 들어 다음 오버로드된 메서드에는 `long` 및 [int](../../../csharp/language-reference/keywords/int.md) 형식의 매개 변수가 있습니다.  
  
```csharp
public static void SampleMethod(int i) {}  
public static void SampleMethod(long l) {}  
```  
  
 `L` 접미사를 사용하면 올바른 오버로드가 호출됩니다.  
  
```csharp  
SampleMethod(5);    // Calls the method with the int parameter  
SampleMethod(5L);   // Calls the method with the long parameter  
```  
정수 리터럴에 접미사가 없는 경우 해당 형식은 값이 표현될 수 있는 다음 형식 중 첫 번째 형식입니다. 

1. [int](int.md)
2. [uint](../../../csharp/language-reference/keywords/uint.md)
3. `long`
4. [ulong](../../../csharp/language-reference/keywords/ulong.md) 

앞의 예제에서 리터럴 4294967296은 [uint](../../../csharp/language-reference/keywords/uint.md)의 범위를 초과하기 때문에 `long` 형식입니다(정수 형식의 저장소 크기는 [정수 형식 표](../../../csharp/language-reference/keywords/integral-types-table.md) 참조).  
  
 같은 식에서 다른 정수 형식과 함께 `long` 형식을 사용하는 경우에는 식이 `long`(또는 관계형 또는 부울 식의 경우 [bool](../../../csharp/language-reference/keywords/bool.md))으로 평가됩니다. 예를 들어 다음 식은 `long`으로 계산됩니다.  
  
```csharp  
898L + 88  
```  
  
 부동 소수점 형식 및 정수 형식이 혼합된 산술 식에 대한 자세한 내용은 [float](../../../csharp/language-reference/keywords/float.md) 및 [double](../../../csharp/language-reference/keywords/double.md)을 참조하세요.  
  
## <a name="conversions"></a>변환  
 `long`에서 [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) 또는 [decimal](../../../csharp/language-reference/keywords/decimal.md)로 미리 정의된 암시적 변환이 있습니다. 없는 경우 캐스트를 사용해야 합니다. 예를 들어 다음 문은 명시적 캐스트 없이 컴파일 오류를 생성합니다.  
  
```csharp  
int x = 8L;        // Error: no implicit conversion from long to int  
int x = (int)8L;   // OK: explicit conversion to int  
```  
  
 [sbyte](../../../csharp/language-reference/keywords/sbyte.md), [byte](../../../csharp/language-reference/keywords/byte.md), [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md) 또는 [char](../../../csharp/language-reference/keywords/char.md)에서 `long`으로 미리 정의된 암시적 변환이 있습니다.  
  
 부동 소수점 형식에서 `long`로의 암시적 변환은 없습니다. 예를 들어 명시적 캐스트를 사용하지 않는 경우 다음 문은 컴파일러 오류를 일으킵니다.  
  
```csharp  
long x = 3.0;         // Error: no implicit conversion from double  
long y = (long)3.0;   // OK: explicit conversion  
```  
  
## <a name="c-language-specification"></a>C# 언어 사양  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Int64>  
 [C# 참조](../../../csharp/language-reference/index.md)  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
 [C# 키워드](../../../csharp/language-reference/keywords/index.md)  
 [정수 계열 형식 표](../../../csharp/language-reference/keywords/integral-types-table.md)  
 [기본 제공 형식 표](../../../csharp/language-reference/keywords/built-in-types-table.md)  
 [암시적 숫자 변환 표](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)  
 [명시적 숫자 변환 표](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
