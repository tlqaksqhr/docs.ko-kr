---
title: float(C# 참조)
ms.date: 07/20/2015
f1_keywords:
- float
- float_CSharpKeyword
helpviewer_keywords:
- float keyword [C#]
- floating-point numbers [C#], float keyword
ms.assetid: 1e77db7b-dedb-48b7-8dd1-b055e96a9258
ms.openlocfilehash: edeed59da26c7007b23e1eec8c05fbd2e6d34d36
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33219247"
---
# <a name="float-c-reference"></a>float(C# 참조)
`float` 키워드는 32비트 부동 소수점 값을 저장하는 단순 형식을 나타냅니다. 다음 표에서는 `float` 형식의 전체 자릿수와 근사 범위를 보여 줍니다.  
  
|형식|근사 범위|전체 자릿수|.NET Framework 형식|  
|----------|-----------------------|---------------|-------------------------|  
|`float`|-3.4 × 10<sup>38</sup> ~ +3.4 × 10<sup>38</sup>|7개의 자릿수|<xref:System.Single?displayProperty=nameWithType>|  
  
## <a name="literals"></a>리터럴  
 기본적으로 대입 연산자 오른쪽의 실수 리터럴은 [double](double.md)로 처리됩니다. 따라서 부동 변수를 초기화하려면 다음 예제와 같이 접미사 `f` 또는 `F`를 사용합니다.  
  
```csharp
float x = 3.5F;  
```
  
 이전 선언에서 접미사를 사용하지 않은 경우 [double](double.md) 값을 `float` 변수에 저장하려고 하기 때문에 컴파일 오류가 발생합니다.  
  
## <a name="conversions"></a>변환  
 식에서 숫자 정수 형식과 부동 소수점 형식을 함께 사용할 수 있습니다. 이 경우 정수 형식이 부동 소수점 형식으로 변환됩니다. 식의 계산은 다음 규칙에 따라 수행됩니다.  
  
-   부동 소수점 형식 중 하나가 [double](double.md)이면 식은 [double](double.md) 또는 [bool](bool.md)(관계형 식이나 부울 식의 경우)로 계산됩니다.  
  
-   식에 [double](double.md) 형식이 없으면 `float` 또는 [bool](bool.md)(관계형 식이나 부울 식의 경우)로 계산됩니다.  
  
 부동 소수점 식에는 다음과 같은 값 집합이 포함될 수 있습니다.  
  
-   양수 및 음수 0  
  
-   양수 및 음수 무한대  
  
-   NaN(Not-a-Number) 값  
  
-   한정된 0이 아닌 값의 집합  
  
 이러한 값에 대한 자세한 내용은 [IEEE](http://www.ieee.org) 웹 사이트에서 제공되는 이진 부동 소수점 연산에 대한 IEEE 표준을 참조하세요.  
  
## <a name="example"></a>예  
 다음 예제에서는 [int](int.md), [short](short.md) 및 `float`가 수학 식에 포함되어 `float` 결과를 제공합니다. (`float`는 <xref:System.Single?displayProperty=nameWithType> 형식의 별칭입니다.) 식에 [double](double.md)이 없습니다.  
  
 [!code-csharp[csrefKeywordsTypes#13](../../../csharp/language-reference/keywords/codesnippet/CSharp/float_1.cs)]  
  
## <a name="c-language-specification"></a>C# 언어 사양  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Single>  
 [C# 참조](../../../csharp/language-reference/index.md)  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
 [캐스팅 및 형식 변환](../../../csharp/programming-guide/types/casting-and-type-conversions.md)  
 [C# 키워드](index.md)  
 [정수 계열 형식 표](integral-types-table.md)  
 [기본 제공 형식 표](built-in-types-table.md)  
 [암시적 숫자 변환 표](implicit-numeric-conversions-table.md)  
 [명시적 숫자 변환 표](explicit-numeric-conversions-table.md)
