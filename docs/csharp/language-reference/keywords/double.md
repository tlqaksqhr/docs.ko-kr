---
title: "double(C# 참조) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- double
- double_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- double data type [C#]
ms.assetid: 0980e11b-6004-4102-abcf-cfc280fc6991
caps.latest.revision: 26
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
ms.openlocfilehash: ccdd29c78a3cdc9d32fa08b1be94eecd717418fc
ms.lasthandoff: 03/13/2017

---
# <a name="double-c-reference"></a>double(C# 참조)
`double` 키워드는 64비트 부동 소수점 값을 저장하는 단순 형식을 나타냅니다. 다음 표에서는 `double` 형식의 전체 자릿수와 근사 범위를 보여 줍니다.  
  
|형식|근사 범위|전체 자릿수|.NET Framework 형식|  
|----------|-----------------------|---------------|-------------------------|  
|`double`|±5.0 × 10<sup>−324</sup> ~ ±1.7 × 10<sup>308</sup>|15-16자리|<xref:System.Double?displayProperty=fullName>|  
  
## <a name="literals"></a>리터럴  
 기본적으로 대입 연산자 오른쪽의 실수 리터럴은 `double`로 처리됩니다. 그러나 정수가 `double`로 처리되도록 하려면 접미사 d 또는 D를 사용하세요. 예를 들면 다음과 같습니다.  
  
```  
  
double x = 3D;  
```  
  
## <a name="conversions"></a>변환  
 식에서 숫자 정수 형식과 부동 소수점 형식을 함께 사용할 수 있습니다. 이 경우 정수 형식이 부동 소수점 형식으로 변환됩니다. 식의 계산은 다음 규칙에 따라 수행됩니다.  
  
-   부동 소수점 형식 중 하나가 `double`이면 식은 `double` 또는 [bool](../../../csharp/language-reference/keywords/bool.md)(관계형 식이나 부울 식의 경우)로 계산됩니다.  
  
-   식에 `double` 형식이 없으면 [float](../../../csharp/language-reference/keywords/float.md) 또는 [bool](../../../csharp/language-reference/keywords/bool.md)(관계형 식이나 부울 식의 경우)로 계산됩니다.  
  
 부동 소수점 식에는 다음과 같은 값 집합이 포함될 수 있습니다.  
  
-   양수 및 음수 0.  
  
-   양수 및 음수 무한대.  
  
-   NaN(Not-a-Number) 값.  
  
-   한정된 0이 아닌 값의 집합.  
  
 이러한 값에 대한 자세한 내용은 [IEEE](http://go.microsoft.com/fwlink/?LinkId=26269) 웹 사이트에서 제공되는 이진 부동 소수점 연산에 대한 IEEE 표준을 참조하세요.  
  
## <a name="example"></a>예제  
 다음 예제에서는 [int](../../../csharp/language-reference/keywords/int.md), [short](../../../csharp/language-reference/keywords/short.md), [float](../../../csharp/language-reference/keywords/float.md) 및 `double`을 함께 더하여 `double` 결과를 제공합니다.  
  
 [!code-cs[csrefKeywordsTypes#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/double_1.cs)]  
  
## <a name="c-language-specification"></a>C# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [C# 참조](../../../csharp/language-reference/index.md)   
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C# 키워드](../../../csharp/language-reference/keywords/index.md)   
 [기본값 표](../../../csharp/language-reference/keywords/default-values-table.md)   
 [기본 제공 형식 표](../../../csharp/language-reference/keywords/built-in-types-table.md)   
 [부동 소수점 형식 표](../../../csharp/language-reference/keywords/floating-point-types-table.md)   
 [암시적 숫자 변환 표](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)   
 [명시적 숫자 변환 표](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
