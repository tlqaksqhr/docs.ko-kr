---
title: "Like Operator (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "Like"
  - "vb.Like"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "similar to"
  - "pattern matching"
  - "Like operator [Visual Basic]"
  - "? symbol, wildcard character"
  - "string comparison [Visual Basic], Like operator"
  - "strings [Visual Basic], comparing"
  - "comparison operators"
  - "symbols, wildcard"
  - "wildcards, Like operator"
  - "strings [Visual Basic], matching"
  - "string comparison [Visual Basic], sorting data"
  - "data [Visual Basic], sorting"
  - "text [Visual Basic], comparing"
  - "operators [Visual Basic], pattern-matching"
  - "data [Visual Basic], string comparisons"
  - "string comparison [Visual Basic], Like operators"
ms.assetid: 966283ec-80e2-4294-baa8-c75baff804f9
caps.latest.revision: 18
caps.handback.revision: 18
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Like Operator (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

문자열을 패턴과 비교합니다.  
  
## 구문  
  
```  
  
result = string Like pattern  
```  
  
## 요소  
 `result`  
 필수 요소.  `Boolean` 형식의 임의 변수입니다.  결과는 `string`이 `pattern`을 충족하는지 여부를 나타내는 `Boolean` 값입니다.  
  
 `string`  
 필수 요소.  `String` 식입니다.  
  
 `pattern`  
 필수 요소.  "설명" 부분에서 명시한 패턴 일치 규칙에 맞는 임의의 `String` 식입니다.  
  
## 설명  
 `string`의 값이 `pattern`에 포함된 패턴을 충족할 경우 `result`는 `True`입니다.  문자열이 패턴을 충족하지 않을 경우 `result`는 `False`입니다.  `string`과 `pattern`이 모두 빈 문자열이면 결과는 `True`가 됩니다.  
  
## 비교 메서드  
 `Like` 연산자의 동작은 [Option Compare Statement](../../../visual-basic/language-reference/statements/option-compare-statement.md)에 따라 달라집니다.  각 소스 파일의 기본 문자열 비교 메서드는 `Option Compare Binary`입니다.  
  
## 패턴 옵션  
 기본 제공 패턴 일치 기능을 사용하면 여러 가지 방법으로 문자열을 비교할 수 있습니다.  패턴 일치 기능을 사용하면 특정 문자, 와일드카드 문자, 문자 목록, 문자 범위 등에 대해 `string`의 각 문자를 일치시킬 수 있습니다.  다음 표에서는 `pattern`에 사용할 수 있는 문자와 해당 문자와 일치하는 대상을 보여 줍니다.  
  
|`pattern`의 문자|`string`의 일치 대상|  
|-------------------|---------------------|  
|`?`|임의의 단일 문자|  
|`*`|0개 이상의 문자|  
|`#`|임의의 단일 숫자\(0–9\)|  
|`[` `charlist` `]`|`charlist`에 있는 임의의 단일 문자|  
|`[!` `charlist` `]`|`charlist`에 없는 임의의 단일 문자|  
  
## 문자 목록  
 하나 이상의 문자를 대괄호\(`[ ]`\)로 묶은 문자 그룹\(`charlist`\)은 `string`에 있는 임의의 단일 문자와 일치시키는 데 사용될 수 있으며, 숫자뿐만 아니라 거의 모든 문자 코드를 포함할 수 있습니다.  
  
 `charlist`의 시작 부분에 있는 느낌표\(`!`\)는 `charlist`에 있는 문자를 제외한 문자가 `string`에 있으면 해당 문자를 찾습니다.  대괄호 외부에서 느낌표를 사용하면 느낌표 자체를 찾습니다.  
  
## 특수 문자  
 왼쪽 대괄호\(`[`\), 물음표\(`?`\), 숫자 표시\(`#`\), 별표\(`*`\) 등과 같은 특수 문자와 일치시키려면 해당 문자를 대괄호로 묶습니다.  그룹 내에 오른쪽 대괄호\(`]`\)를 사용하여 자신과 일치하는 문자를 찾을 수는 없지만 그룹 외부에서는 개별 문자로 사용할 수 있습니다.  
  
 문자 시퀀스 `[]`는 길이가 0인 문자열\(`""`\)로 간주됩니다.  그러나 대괄호로 묶은 문자 목록의 일부가 될 수는 없습니다.  `string`의 특정 위치에 문자 그룹 중 하나가 포함되어 있거나 문자가 전혀 포함되지 않았는지 확인하려면 `Like`를 두 번 사용합니다.  예제를 보려면 [How to: Match a String against a Pattern](../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-match-a-string-against-a-pattern.md)을 참조하십시오.  
  
## 문자 범위  
 범위의 상한과 하한을 구분하는 하이픈\(`–`\)을 사용하여 `charlist`에서 문자의 범위를 지정할 수 있습니다.  예를 들어, `string`의 해당 문자 위치에 `A`에서 `Z` 사이의 임의 문자가 있으면 `[A–Z]`를 사용하여 찾고 해당 문자 위치에 `H`에서 `L` 사이를 벗어나는 임의 문자가 있으면 `[!H–L]`를 사용하여 찾습니다.  
  
 문자의 범위를 지정하면 문자는 오름차순\(A \- Z\)으로 표시되어야 합니다.  따라서 `[A–Z]`는 유효한 패턴이지만 `[Z–A]`는 유효하지 않습니다.  
  
### 여러 문자 범위  
 동일한 문자 위치에 대해 여러 범위를 지정하려면 구분 기호 없이 대괄호 내에 추가합니다.  예를 들어, `string`의 해당 문자 위치에 `A`에서 `C` 사이 또는 `X`에서 `Z` 사이의 임의 문자가 있으면 `[A–CX–Z]`를 사용하여 찾습니다.  
  
### 하이픈 사용  
 하이픈\(`–`\) 자체를 찾으려면 하이픈을 `charlist`의 시작 부분\(느낌표가 사용되는 경우 그 다음\)이나 끝 부분에 사용합니다.  하이픈을 다른 위치에 사용하면 하이픈 양쪽에 있는 문자의 범위를 나타냅니다.  
  
## 데이터 정렬 순서  
 지정된 범위의 의미는 런타임에 문자 순서에 따라 달라집니다. 즉, `Option` `Compare`와 코드가 실행되는 시스템의 로캘 설정에 의해 결정됩니다.  `Option` `Compare` `Binary`의 경우 범위 `[A–E]`는 `A`, `B`, `C`, `D` 및 `E`에 해당합니다.  `Option` `Compare` `Text`의 경우 범위 `[A–E]`는 `A`, `a`, `À`, `à`, `B`, `b`, `C`, `c`, `D`, `d`, `E` 및 `e`에 해당합니다.  정렬 순서에 따라 악센트 부호가 있는 문자는 악센트 부호가 없는 문자 다음에 오므로 해당 범위에는 `Ê` 또는 `ê`가 포함되지 않습니다.  
  
## Digraph 문자  
 일부 언어에는 별도의 두 문자를 나타내는 영문자가 있습니다.  예를 들어, 일부 언어에서는 `æ` 문자를 사용하여 `a`와 `e` 문자를 나타냅니다.  `Like` 연산자는 이 digraph 문자 하나와 두 개의 개별 문자를 같은 것으로 인식합니다.  
  
 시스템 로캘 설정에 digraph 문자를 사용하는 언어가 지정되어 있는 경우, `pattern` 또는 `string`에 digraph 문자가 있으면 다른 문자열에서 이에 해당하는 두 문자 시퀀스를 찾습니다.  마찬가지로 `pattern`의 digraph 문자를 대괄호 내에 단독으로 사용하거나 목록 또는 범위에서 사용하는 경우, `string`에서 이에 해당하는 두 문자 시퀀스를 찾습니다.  
  
## 오버로딩  
 `Like` 연산자는 필요에 따라 *오버로드*할 수 있습니다. 즉, 피연산자의 형식이 특정 클래스 또는 구조체인 경우 해당 클래스나 구조체에서 이 연산자의 동작을 다시 정의할 수 있습니다.  코드에서 이러한 클래스나 구조체에 대해 이 연산자를 사용할 때는 다시 정의된 동작을 알고 있어야 합니다.  자세한 내용은 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)를 참조하십시오.  
  
## 예제  
 다음 예제에서는 `Like` 연산자를 사용하여 문자열과 다양한 패턴을 비교합니다.  결과는 각 문자열이 패턴을 충족하는지 나타내는 `Boolean` 변수입니다.  
  
 [!CODE [VbVbalrOperators#30](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrOperators#30)]  
  
## 참고 항목  
 <xref:Microsoft.VisualBasic.Strings.InStr%2A>   
 <xref:Microsoft.VisualBasic.Strings.StrComp%2A>   
 [Comparison Operators](../../../visual-basic/language-reference/operators/comparison-operators.md)   
 [Operator Precedence in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Option Compare Statement](../../../visual-basic/language-reference/statements/option-compare-statement.md)   
 [Operators and Expressions](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)   
 [How to: Match a String against a Pattern](../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-match-a-string-against-a-pattern.md)