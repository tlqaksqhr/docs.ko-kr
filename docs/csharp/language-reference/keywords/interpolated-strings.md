---
title: "보간된 문자열(C# 및 Visual Basic 참조) | Microsoft Docs"
ms.date: "2017-02-03"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
ms.assetid: 324f267e-1c61-431a-97ed-852c1530742d
caps.latest.revision: 9
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 9
---
# 보간된 문자열(C# 및 Visual Basic 참조)
문자열을 생성하는 데 사용됩니다.  보간된 문자열 식은 식이 포함된 템플릿 문자열과 유사합니다.  보간된 문자열 식은 포함된 식을 식 결과의 ToString 표현으로 대체하여 문자열을 만듭니다.  보간된 문자열은 인수 측면에서 [복합 형식 지정](../Topic/Composite%20Formatting.md)보다 이해하기 쉽습니다.  다음은 보간된 문자열의 예입니다.  
  
```c#  
Console.WriteLine($"Name = {name}, hours = {hours:hh}")  
```  
  
 보간된 문자열의 구조는 다음과 같습니다.  
  
```  
$ " <text> { <interpolation-expression> <optional-comma-field-width> <optional-colon-format> } <text> ... } "  
```  
  
 문자열 리터럴을 사용할 수 있는 곳이면 어디든지 보간된 문자열을 사용할 수 있습니다.  프로그램 실행 시 보간된 문자열 리터럴을 사용하여 코드가 실행되는 경우 코드에서 보간 식을 평가하여 새 문자열 리터럴을 계산합니다.  이 계산은 보간된 문자열을 포함하는 코드가 실행될 때마다 발생합니다.  
  
 보간된 문자열에 중괄호\("{" 또는 "}"\)를 포함하려면 두 개의 중괄호 "{{" 또는 "}}"를 사용합니다.  자세한 내용은 암시적 변환 섹션을 참조하세요.  
  
## 암시적 변환  
 보간된 문자열에서 다음과 같은 암시적 형식 변환을 수행할 수 있습니다.  
  
```c#  
var s = $"hello, {name}" System.IFormattable s = $"Hello, {name}" System.FormattableString s = $"Hello, {name}"  
  
```  
  
 첫 번째 예제에서는 모든 문자열 보간 값이 계산된 `string` 값을 생성합니다.  최종 결과이며 문자열 형식입니다.  나타나는 모든 이중 중괄호\("{{" 및 "}}"\)가 단일 중괄호로 변환됩니다.  
  
 두 번째 예제에서는 고정 컨텍스트를 포함하는 문자열을 변환할 수 있는 <xref:System.IFormattable> 변수를 생성합니다.  이 기능은 숫자 및 데이터 형식을 다양한 언어에서 올바르게 표시하는 데 유용합니다.  나타나는 모든 이중 중괄호\("{{" 및 "}}"\)는 ToString을 사용하여 문자열의 형식을 지정할 때까지 이중 중괄호로 유지됩니다.  포함된 보간 식은 모두 {0}, {1} 등으로 변환됩니다.  
  
```c#  
s.ToString(null, System.Globalization.CultureInfo.InvariantCulture);  
```  
  
 세 번째 예제에서는 보간 계산 결과로 얻은 개체를 검사할 수 있는 <xref:System.FormattableString>을 생성합니다.  예를 들어 개체와 개체가 문자열로 렌더링되는 방식을 검사하면 쿼리를 빌드하는 경우 삽입 공격으로부터 보호하는 데 도움이 됩니다.<xref:System.FormattableString>을 사용하면 InvariantCulture 및 CurrentCulture 문자열 결과를 편리하게 생성할 수 있습니다.  나타나는 모든 이중 중괄호\("{{" 및 "}}"\)는 형식을 지정할 때까지 이중 중괄호로 유지됩니다.  포함된 보간 식은 모두 {0}, {1} 등으로 변환됩니다.  
  
## 예제  
  
```c#  
$"Name = {name}, hours = {hours:hh}" var s = $"hello, {name}" System.IFormattable s = $"Hello, {name}" System.FormattableString s = $"Hello, {name}" $"{person.Name, 20} is {person.Age:D3} year {(p.Age == 1 ? "" : "s")} old."  
  
```  
  
 보간된 문자열 식은 $로 시작하고 컴파일러가 쉼표, 콜론 또는 닫는 중괄호를 발견할 때까지 포함된 보간 식을 균형 있는 텍스트로 검색하기 때문에 포함된 보간 식 내에서 인용 문자를 따옴표로 묶을 필요가 없습니다.  동일한 이유로, 마지막 예제에서는 괄호를 사용하여 형식 사양을 시작하는 콜론 없이 보간 식 내에 조건식\(`p.Age == 1 ? "" : "s"`\)을 포함할 수 있게 합니다.  포함된 보간 식 외부\(하지만 보간된 문자열 식 내부\)에서는 평소대로 인용 문자를 이스케이프합니다.  
  
## 구문  
  
```  
expression: interpolated-string-expression interpolated-string-expression: interpolated-string-start interpolations interpolated-string-end interpolations: single-interpolation single-interpolation interpolated-string-mid interpolations single-interpolation: interpolation-start interpolation-start : regular-string-literal interpolation-start: expression expression , expression  
  
```  
  
## 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
 자세한 내용은 [Visual Basic Language Reference](../../../visual-basic/language-reference/index.md)를 참조하세요.  
  
## 참고 항목  
 <xref:System.IFormattable?displayProperty=fullName>   
 <xref:System.FormattableString?displayProperty=fullName>   
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [Visual Basic Language Reference](../../../visual-basic/language-reference/index.md)   
 [Visual Basic Programming Guide](../../../visual-basic/programming-guide/index.md)