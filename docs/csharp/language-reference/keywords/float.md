---
title: "float(C# 참조) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "float"
  - "float_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "float 키워드[C#]"
  - "부동 소수점 숫자[C#], float 키워드"
ms.assetid: 1e77db7b-dedb-48b7-8dd1-b055e96a9258
caps.latest.revision: 24
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 24
---
# float(C# 참조)
`float` 키워드는 32비트 부동 소수점 값을 저장하는 단순 형식을 나타냅니다.  다음 표에서는 `float` 형식의 전체 자릿수와 근사 범위를 보여 줍니다.  
  
|형식|근사 범위|전체 자릿수|.NET Framework 형식|  
|--------|-----------|------------|-----------------------|  
|`float`|\-3.4 × 10<sup>38</sup>to \+3.4 × 10<sup>38</sup>|7개의 자릿수|<xref:System.Single?displayProperty=fullName>|  
  
## 리터럴  
 기본적으로 할당 연산자의 오른쪽에 있는 실수형 숫자 리터럴은 [double](../../../csharp/language-reference/keywords/double.md)로 처리됩니다.  따라서 float 형식의 변수를 초기화하려면 다음 예제와 같이 `f` 또는 `F` 접미사를 사용하십시오.  
  
```  
  
float x = 3.5F;  
```  
  
 위의 선언에서 접미사를 사용하지 않은 경우 `float` 변수에 [double](../../../csharp/language-reference/keywords/double.md) 값을 저장하려고 했으므로 컴파일 오류가 발생합니다.  
  
## 변환  
 한 식에서 숫자 정수 계열 형식과 부동 소수점 형식을 함께 사용할 수 있습니다.  이 경우 정수 계열 형식은 부동 소수점 형식으로 변환됩니다.  식 계산은 다음 규칙에 따라 수행됩니다.  
  
-   부동 소수점 형식 중 하나가 [double](../../../csharp/language-reference/keywords/double.md)인 경우 식은 [double](../../../csharp/language-reference/keywords/double.md)로 계산되거나, 부울 식이거나 관계식의 경우 [bool](../../../csharp/language-reference/keywords/bool.md)로 계산됩니다.  
  
-   식에 [double](../../../csharp/language-reference/keywords/double.md) 형식이 없는 경우 식은 `float`로 계산되거나, 부울 식 또는 관계식의 경우 [bool](../../../csharp/language-reference/keywords/bool.md)로 계산됩니다.  
  
 부동 소수점 식에는 다음과 같은 값이 포함될 수 있습니다.  
  
-   양수 및 음수 0  
  
-   양수 및 음수 무한  
  
-   NaN\(Not\-a\-Number\) 값  
  
-   0이 아닌 값의 유한 집합  
  
 이러한 값에 대한 자세한 내용은 [IEEE](http://go.microsoft.com/fwlink/?LinkId=26269) 웹 사이트에서 IEEE Standard for Binary Floating\-Point Arithmetic을 참조하십시오.  
  
## 예제  
 다음 예제에서는 수학 식에 [int](../../../csharp/language-reference/keywords/int.md), [short](../../../csharp/language-reference/keywords/short.md) 및 `float`가 포함되고 결과는 `float`가 됩니다.  `float`는 <xref:System.Single?displayProperty=fullName> 형식의 별칭이라는 것을 기억하십시오. 이 식에 [double](../../../csharp/language-reference/keywords/double.md) 형식은 없습니다.  
  
 [!code-cs[csrefKeywordsTypes#13](../../../csharp/language-reference/keywords/codesnippet/csharp/float_1.cs)]  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## 참고 항목  
 <xref:System.Single>   
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [캐스팅 및 형식 변환\(C\#\)](../../../csharp/programming-guide/types/casting-and-type-conversions.md)   
 [C\# 키워드](../../../csharp/language-reference/keywords/index.md)   
 [정수 계열 형식 표](../../../csharp/language-reference/keywords/integral-types-table.md)   
 [기본 제공 형식 표](../../../csharp/language-reference/keywords/built-in-types-table.md)   
 [암시적 숫자 변환 표](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)   
 [명시적 숫자 변환 표](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)