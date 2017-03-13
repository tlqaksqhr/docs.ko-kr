---
title: "double(C# 참조) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "double"
  - "double_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "double 데이터 형식[C#]"
ms.assetid: 0980e11b-6004-4102-abcf-cfc280fc6991
caps.latest.revision: 26
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 26
---
# double(C# 참조)
`double` 키워드는 64비트 부동 소수점 값을 저장하는 단순 형식을 나타냅니다.  다음 표에서는 `double` 형식의 전체 자릿수와 근사 범위를 보여 줍니다.  
  
|형식|근사 범위|전체 자릿수|.NET Framework 형식|  
|--------|-----------|------------|-----------------------|  
|`double`|±5.0 × 10<sup>−324</sup> ~ ±1.7 × 10<sup>308</sup>|15\-16개의 자릿수|<xref:System.Double?displayProperty=fullName>|  
  
## 리터럴  
 기본적으로 할당 연산자의 오른쪽에 있는 실수형 숫자 리터럴은 `double`로 처리됩니다.  그러나 정수형 숫자를 `double`로 처리하려면 다음 예제와 같이 d 또는 D 접미사를 사용하십시오.  
  
```  
  
double x = 3D;  
```  
  
## 변환  
 한 식에서 숫자 정수 계열 형식과 부동 소수점 형식을 함께 사용할 수 있습니다.  이 경우 정수 계열 형식은 부동 소수점 형식으로 변환됩니다.  식 계산은 다음 규칙에 따라 수행됩니다.  
  
-   부동 소수점 형식 중 하나가 `double`인 경우 식은 `double`로 계산되고 부울 식 또는 관계식의 경우에는 [bool](../../../csharp/language-reference/keywords/bool.md)로 계산됩니다.  
  
-   식에 `double` 형식이 없는 경우 식은 [float](../../../csharp/language-reference/keywords/float.md)로 계산되고 부울 식 또는 관계식의 경우에는 [bool](../../../csharp/language-reference/keywords/bool.md)로 계산됩니다.  
  
 부동 소수점 식에는 다음과 같은 값이 포함될 수 있습니다.  
  
-   양수 및 음수 0  
  
-   양수 및 음수 무한  
  
-   NaN\(Not\-a\-Number\) 값  
  
-   0이 아닌 값의 유한 집합  
  
 이러한 값에 대한 자세한 내용은 [IEEE](http://go.microsoft.com/fwlink/?LinkId=26269) 웹 사이트에서 IEEE Standard for Binary Floating\-Point Arithmetic을 참조하십시오.  
  
## 예제  
 다음 예제에서는 [int](../../../csharp/language-reference/keywords/int.md), [short](../../../csharp/language-reference/keywords/short.md), [float](../../../csharp/language-reference/keywords/float.md) 및 `double` 키워드가 함께 추가되고 결과는 `double`이 됩니다.  
  
 [!code-cs[csrefKeywordsTypes#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/double_1.cs)]  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\# 키워드](../../../csharp/language-reference/keywords/index.md)   
 [기본값 표](../../../csharp/language-reference/keywords/default-values-table.md)   
 [기본 제공 형식 표](../../../csharp/language-reference/keywords/built-in-types-table.md)   
 [부동 소수점 형식 표](../../../csharp/language-reference/keywords/floating-point-types-table.md)   
 [암시적 숫자 변환 표](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)   
 [명시적 숫자 변환 표](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)