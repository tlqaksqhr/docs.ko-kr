---
title: "decimal(C# 참조)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- decimal_CSharpKeyword
- decimal
helpviewer_keywords:
- decimal keyword [C#]
ms.assetid: b6522132-b5ee-4be3-ad13-3adfdb7de7a1
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 0da001851c681fe4d698b920d9668b2f6b731e3a
ms.sourcegitcommit: 973a12d1e6962cd9a9c263fbfaad040ec8267fe9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/22/2018
---
# <a name="decimal-c-reference"></a>decimal(C# 참조)
`decimal` 키워드는 128비트 데이터 형식을 나타냅니다. `decimal` 형식은 부동 소수점 형식보다 전체 자릿수는 크고 범위는 작아서 재무 및 통화 계산에 적합합니다. 다음 표에서는 `decimal` 형식의 대략적인 범위와 전체 자릿수를 보여 줍니다.  
  
|형식|근사 범위|전체 자릿수|.NET Framework 형식|  
|----------|-----------------------|---------------|-------------------------|  
|`decimal`|(-7.9 x 10<sup>28</sup> ~ 7.9 x 10<sup>28</sup>) / (10<sup>0</sup> ~ 10<sup>28</sup>)|28-29개의 유효 자릿수|<xref:System.Decimal?displayProperty=nameWithType>|  

`decimal`의 기본값은 0m입니다.
  
## <a name="literals"></a>리터럴  
 숫자 형식의 실수 리터럴이 `decimal`로 처리되게 하려면 다음과 같이 접미사 m 또는 M을 사용합니다.  
  
```csharp
decimal myMoney = 300.5m;  
```  
  
 m 접미사가 없으면 숫자가 [double](../../../csharp/language-reference/keywords/double.md)로 처리되어 컴파일러 오류가 발생합니다.  
  
## <a name="conversions"></a>변환  
 정수 형식은 암시적으로 `decimal`로 변환되어 계산 결과가 `decimal`로 나타납니다. 따라서 접미사를 붙이지 않고 정수 리터럴을 사용하여 decimal 변수를 초기화할 수 있습니다. 예를 들면 다음과 같습니다.  
  
```csharp
decimal myMoney = 300;  
```  
  
 다른 부동 소수점 형식과 `decimal` 형식 간의 암시적 변환은 없습니다. 따라서 이 두 형식 간의 변환에는 캐스트를 사용해야 합니다. 예:  
  
```csharp
decimal myMoney = 99.9m;  
double x = (double)myMoney;  
myMoney = (decimal)x;  
```  
  
 또한 같은 식에서 `decimal`과 숫자 정수 형식을 혼합할 수 있습니다. 그러나 캐스트를 사용하지 않고 `decimal`과 다른 부동 소수점 형식을 혼합하면 컴파일 오류가 발생합니다.  
  
 암시적 숫자 변환에 대한 자세한 내용은 [암시적 숫자 변환 표](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)를 참조하세요.  
  
 명시적 숫자 변환에 대한 자세한 내용은 [명시적 숫자 변환 표](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)를 참조하세요.  
  
## <a name="formatting-decimal-output"></a>Decimal 출력 서식 지정  
 `String.Format` 메서드를 사용하거나 <xref:System.Console.Write%2A?displayProperty=nameWithType>을 호출하는 `String.Format()` 메서드를 통해 결과의 서식을 지정할 수 있습니다. 통화 서식은 이 문서 뒷부분에 있는 두 번째 예제처럼 표준 통화 서식 문자열 "C" 또는 "c"를 사용하여 지정합니다. `String.Format` 메서드에 대한 자세한 내용은 <xref:System.String.Format%2A?displayProperty=nameWithType>을 참조하십시오.  
  
## <a name="example"></a>예  
 다음은 [double](../../../csharp/language-reference/keywords/double.md) 및 `decimal` 변수를 추가하려고 시도하여 컴파일러 오류가 발생하는 예제입니다.  
  
```csharp  
decimal dec = 0m;
double dub = 9;  
// The following line causes an error that reads "Operator '+' cannot be applied to   
// operands of type 'double' and 'decimal'"  
Console.WriteLine(dec + dub);   
  
// You can fix the error by using explicit casting of either operand.  
Console.WriteLine(dec + (decimal)dub);  
Console.WriteLine((double)dec + dub);  
```  
  
 다음 오류가 발생합니다.  
  
 `Operator '+' cannot be applied to operands of type 'double' and 'decimal'`  
  
 이 예제에서는 같은 식에 `decimal`과 [int](../../../csharp/language-reference/keywords/int.md)가 혼합되어 있습니다. 계산 결과는 `decimal` 형식입니다.  
  
 [!code-csharp[csrefKeywordsTypes#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/decimal_1.cs)]  
  
## <a name="example"></a>예  
 이 예제에서는 통화 서식 문자열을 사용하여 출력 서식을 지정합니다. `x`는 소수 자릿수가 $0.99를 초과하기 때문에 반올림됩니다. 최대 자릿수를 나타내는 변수 `y`는 올바른 서식으로 정확하게 표시됩니다.  
  
 [!code-csharp[csrefKeywordsTypes#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/decimal_2.cs)]  
  
## <a name="c-language-specification"></a>C# 언어 사양  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Decimal>  
 [C# 참조](../../../csharp/language-reference/index.md)  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
 [C# 키워드](../../../csharp/language-reference/keywords/index.md)  
 [정수 계열 형식 표](../../../csharp/language-reference/keywords/integral-types-table.md)  
 [기본 제공 형식 표](../../../csharp/language-reference/keywords/built-in-types-table.md)  
 [암시적 숫자 변환 표](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)  
 [명시적 숫자 변환 표](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)  
 [표준 숫자 형식 문자열](../../../standard/base-types/standard-numeric-format-strings.md)
