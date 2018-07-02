---
title: uint(C# 참조)
ms.date: 03/14/2017
f1_keywords:
- uint
- uint_CSharpKeyword
helpviewer_keywords:
- uint keyword [C#]
ms.assetid: e93e42c6-ec72-4b0b-89df-2fd8d36f7a7b
ms.openlocfilehash: 8ee19688ff0a6687bcf761857958aa2022fdb0c8
ms.sourcegitcommit: f9e38d31288fe5962e6be5b0cc286da633482873
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2018
ms.locfileid: "37027813"
---
# <a name="uint-c-reference"></a>uint(C# 참조)

`uint` 키워드는 다음 표에 나와 있는 크기와 범위에 따라 값을 저장하는 정수 형식을 지정합니다.  
  
|형식|범위|크기|.NET 형식|  
|----------|-----------|----------|-------------------------|  
|`uint`|0 ~ 4,294,967,295|부호 없는 32비트 정수|<xref:System.UInt32?displayProperty=nameWithType>|  
  
 **참고** `uint` 형식은 CLS 규격이 아닙니다. 가능한 경우 항상 `int`를 사용합니다.  
  
## <a name="literals"></a>리터럴  

10진수 리터럴, 16진수 리터럴 또는 (C# 7.0부터) 이진 리터럴을 할당하여 `uint` 변수를 선언하고 초기화할 수 있습니다. 정수 리터럴이 `uint` 범위를 벗어나는 경우(즉 <xref:System.UInt32.MinValue?displayProperty=nameWithType>보다 작거나 <xref:System.UInt32.MaxValue?displayProperty=nameWithType>보다 큰 경우) 컴파일 오류가 발생합니다.

다음 예제에서는 10진수, 16진수 및 이진 리터럴로 표현된 3,000,000,000과 같은 정수가 `uint` 값에 할당됩니다.  
  
[!code-csharp[uint](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#UInt)]  

> [!NOTE] 
> `0x` 또는 `0X` 접두사를 사용하여 16진수 리터럴을 나타내고, `0b` 또는 `0B` 접두사를 사용하여 이진 리터럴을 나타냅니다. 10진수 리터럴에는 접두사가 없습니다. 

C# 7.0부터 가독성 향상을 위해 몇 가지 기능이 추가됐습니다. 
 - C# 7.0은 숫자 구분 기호로 밑줄 문자 `_`를 사용할 수 있습니다.
 - C# 7.2는 접두사 뒤에 이진 또는 16진수 리터럴에 대한 자리 구분 기호로 `_`을 사용할 수 있습니다. 10진수 리터럴에 선행 밑줄이 있는 것이 허용되지 않습니다.

일부 예제는 다음과 같습니다.

[!code-csharp[uint](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#UIntS)]  
 
 형식을 나타내는 접미사가 정수 리터럴에 포함되어 있을 수도 있습니다. `U` 또는 'u' 접미사는 리터럴의 숫자 값에 따라 `uint` 또는 `ulong`을 나타냅니다. 다음 예제에서는 `u` 접미사를 사용하여 두 형식의 부호 없는 정수를 나타냅니다. 첫 번째 리터럴은 해당 값이 <xref:System.UInt32.MaxValue?displayProperty=nameWithType>보다 작기 때문에 `uint`인 반면, 두 번째 리터럴은 해당 값이 <xref:System.UInt32.MaxValue?displayProperty=nameWithType>보다 크기 때문에 `ulong`입니다.

[!code-csharp[usuffix](../../../../samples/snippets/csharp/language-reference/keywords/numeric-suffixes.cs#1)]  
 
정수 리터럴에 접미사가 없는 경우 해당 형식은 값이 표현될 수 있는 다음 형식 중 첫 번째 형식입니다. 

1. [int](int.md)
2. `uint`
3. [long](../../../csharp/language-reference/keywords/long.md)
4. [ulong](../../../csharp/language-reference/keywords/ulong.md) 
  
## <a name="conversions"></a>변환  
 `uint`에서 [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) 또는 [decimal](../../../csharp/language-reference/keywords/decimal.md)로 미리 정의된 암시적 변환이 있습니다. 예:  
  
```csharp  
float myFloat = 4294967290;   // OK: implicit conversion to float  
```  
  
 [byte](../../../csharp/language-reference/keywords/byte.md), [ushort](../../../csharp/language-reference/keywords/ushort.md) 또는 [char](../../../csharp/language-reference/keywords/char.md)에서 `uint`로 미리 정의된 암시적 변환이 있습니다. 그렇지 않으면 캐스트를 사용해야 합니다. 예를 들어 다음 대입문은 캐스트 없이 컴파일 오류를 생성합니다.  
  
```csharp  
long aLong = 22;  
// Error -- no implicit conversion from long:  
uint uInt1 = aLong;   
// OK -- explicit conversion:  
uint uInt2 = (uint)aLong;  
```  
  
 부동 소수점 형식에서 `uint`로의 암시적 변환은 없습니다. 예를 들어 명시적 캐스트를 사용하지 않는 경우 다음 문은 컴파일러 오류를 일으킵니다.  
  
```csharp  
// Error -- no implicit conversion from double:  
uint x = 3.0;  
// OK -- explicit conversion:  
uint y = (uint)3.0;   
```  
  
 부동 소수점 형식 및 정수 형식이 혼합된 산술 식에 대한 자세한 내용은 [float](../../../csharp/language-reference/keywords/float.md) 및 [double](../../../csharp/language-reference/keywords/double.md)을 참조하세요.  
  
 암시적 숫자 변환 규칙에 대한 자세한 내용은 [암시적 숫자 변환 표](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)를 참조하세요.  
  
## <a name="c-language-specification"></a>C# 언어 사양  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.UInt32>  
 [C# 참조](../../../csharp/language-reference/index.md)  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
 [C# 키워드](../../../csharp/language-reference/keywords/index.md)  
 [정수 계열 형식 표](../../../csharp/language-reference/keywords/integral-types-table.md)  
 [기본 제공 형식 표](../../../csharp/language-reference/keywords/built-in-types-table.md)  
 [암시적 숫자 변환 표](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)  
 [명시적 숫자 변환 표](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
