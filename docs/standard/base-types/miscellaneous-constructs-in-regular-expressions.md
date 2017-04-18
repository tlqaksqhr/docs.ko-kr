---
title: "정규식의 기타 구문 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - ".NET Framework 정규식, 기타 구문"
  - "생성, 기타"
  - "정규식, 기타 구문"
ms.assetid: 7d10d11f-680f-4721-b047-fb136316b4cd
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# 정규식의 기타 구문
.NET Framework에서 정규식에는 세 가지 기타 언어 구문이 포함됩니다.  정규식 패턴 중간에 특정 일치 옵션을 사용하거나 사용하지 않도록 설정할 수 있습니다.  나머지 둘을 사용하면 정규식에 주석을 포함할 수 있습니다.  
  
## 인라인 옵션  
 구문을 사용하여 정규식 일부에 대해 특정 패턴 일치 옵션을 설정하거나 비활성화할 수 있습니다.  
  
```  
(?imnsx-imnsx)  
```  
  
 물음표 다음에 활성화하려는 옵션 및 빼기 기호 다음에 비활성화하려는 옵션을 나열합니다.  다음 표는 각 옵션에 대해 설명합니다.  각 옵션에 대한 자세한 내용은 [정규식 옵션](../../../docs/standard/base-types/regular-expression-options.md)을 참조하십시오.  
  
|옵션|설명|  
|--------|--------|  
|`i`|대\/소문자를 구분하지 않는 일치.|  
|`m`|여러 줄 모드입니다.|  
|`n`|명시적 캡처의 경우에만. \(괄호는 캡처링 그룹으로 작동하지 않는다.\)|  
|`s`|한 줄 모드.|  
|`x`|이스케이프되지 않은 공백 무시 및 X\-모드 주석 허용|  
  
 `(?imnsx-imnsx)` 의해 정의된 정규식 옵션 변경은 포함 그룹의 끝에 도달할 때까지 유효합니다.  
  
> [!NOTE]
>  `(?imnsx-imnsx:` *subexpression* `)` 그룹화 구문은 하위 식에 대해 동일한 기능을 제공합니다.  자세한 내용은 [그룹화 구문](../../../docs/standard/base-types/grouping-constructs-in-regular-expressions.md)을 참조하십시오.  
  
 다음 예제에서는 `i`, `n` 및 `x` 옵션을 사용하여 대\/소문자 구분 및 명시적 캡처를 사용하고 정규식 패턴에서 정규식의 중간에 있는 공백은 무시합니다.  
  
 [!code-csharp[RegularExpressions.Language.Miscellaneous#1](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.miscellaneous/cs/miscellaneous1.cs#1)]
 [!code-vb[RegularExpressions.Language.Miscellaneous#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.miscellaneous/vb/miscellaneous1.vb#1)]  
  
 예제는 두 가지 정규식을 정의합니다.  첫 번째 `\b(D\w+)\s(d\w+)\b`는 대문자 "D" 및 소문자 "d"로 시작하는 두 개의 연속된 단어를 찾습니다.  두 번째 정규식, `\b(D\w+)(?ixn) \s (d\w+) \b`은 다음 표에 설명하는 것처럼 인라인 옵션을 사용하여 이 패턴을 수정합니다.  결과 비교는 `(?ixn)` 구문의 효과를 확인합니다.  
  
|패턴|설명|  
|--------|--------|  
|`\b`|단어 경계를 시작합니다.|  
|`(D\w+)`|대문자 D 다음에 하나 이상의 단어가 있는 문자를 찾습니다.  이 그룹은 첫 번째 캡처링 그룹입니다.|  
|`(?ixn)`|이 지점에서 대\/소문자를 구분하는 비교를 하고 명시적인 캡처만 수행하며 정규식 패턴에서 공백을 무시하십시오.|  
|`\s`|공백 문자를 찾습니다.|  
|`(d\w+)`|대문자 또는 소문자 "d" 다음에 하나 이상의 단어 문자를 찾습니다.  이 그룹은 `n`\(명시적 캡처\) 옵션이 설정되어 있기 때문에 캡처되지 않습니다.|  
|`\b`|단어 경계를 찾습니다.|  
  
## 인라인 주석  
 `(?#`  *comment* `)` 구문은 정규식에 인라인 주석을 포함할 수 있습니다.  <xref:System.Text.RegularExpressions.Regex.ToString%2A?displayProperty=fullName> 메서드에서 반환하는 문자열에 주석이 포함되어 있지만 정규식 엔진은 패턴 일치의 주석 부분을 사용하지 않습니다.  주석이 첫 번째 닫는 괄호 문자에서 끝납니다.  
  
 다음 예제에서는 이전 섹션 예제의 첫 번째 정규식 패턴을 반복합니다.  비교가 대\/소문자를 구분하는지 여부를 나타내기 위해 정규식에 두 인라인 주석을 추가합니다.  정규식 패턴 `\b((?# case-sensitive comparison)D\w+)\s((?#case-insensitive comparison)d\w+)\b`은 다음과 같이 정의됩니다.  
  
|패턴|설명|  
|--------|--------|  
|`\b`|단어 경계를 시작합니다.|  
|`(?# case-sensitive comparison)`|주석  패턴 일치 동작에 아무런 영향을 주지 않습니다.|  
|`(D\w+)`|대문자 D 다음에 하나 이상의 단어가 있는 문자를 찾습니다.  이 그룹은 첫 번째 캡처링 그룹입니다.|  
|`\s`|공백 문자를 찾습니다.|  
|`(?ixn)`|이 지점에서 대\/소문자를 구분하는 비교를 하고 명시적인 캡처만 수행하며 정규식 패턴에서 공백을 무시하십시오.|  
|`(?#case-insensitive comparison)`|주석  패턴 일치 동작에 아무런 영향을 주지 않습니다.|  
|`(d\w+)`|대문자 또는 소문자 "d" 다음에 하나 이상의 단어 문자를 찾습니다.  이 그룹은 두 번째 캡처링 그룹입니다.|  
|`\b`|단어 경계를 찾습니다.|  
  
 [!code-csharp[RegularExpressions.Language.Miscellaneous#2](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.miscellaneous/cs/miscellaneous2.cs#2)]
 [!code-vb[RegularExpressions.Language.Miscellaneous#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.miscellaneous/vb/miscellaneous2.vb#2)]  
  
## 줄의 끝 주석  
 숫자 기호 \(`#`\)는 정규식 패턴 끝에 이스케이프되지 않은 \# 문자로 시작하여 줄 끝까지 계속되는 x\-모드 주석을 표시합니다.  이 구문을 사용하려면 `x` 옵션\(인라인 옵션을 통해\)을 활성화하거나 <xref:System.Text.RegularExpressions.Regex> 개체를 인스턴스화하거나 정적 <xref:System.Text.RegularExpressions.Regex> 메서드를 호출할 때 <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName> 값을 `option` 매개 변수에 제공해야 합니다.  
  
 다음 예제에서는 줄의 끝 구문을 보여 줍니다.  문자열이 하나 이상의 형식 항목을 포함하는 합성 형식 문자열인지 여부를 결정합니다.  다음 표에서는 정규식 패턴의 구문에 대해 설명합니다.  
  
 `\{\d+(,-*\d+)*(\:\w{1,4}?)*\}(?x) # Looks for a composite format item.`  
  
|패턴|설명|  
|--------|--------|  
|`\{`|여는 중괄호를 찾습니다.|  
|`\d+`|하나 이상의 10진수 숫자가 일치하는지 확인합니다.|  
|`(,-*\d+)*`|하나 이상의 쉼표, 옵션 빼기 기호, 이어서 한 개 이상의 10진수 숫자를 일치하십시오.|  
|`(\:\w{1,4}?)*`|하나 이상의 콜론, 다음에 1~4개가 나오고 가능한 적은 공백 문자를 일치하십시오.|  
|`(?#case insensitive comparison)`|인라인 주석입니다.  패턴 일치 동작에 아무런 영향을 주지 않습니다.|  
|`\}`|닫는 중괄호를 찾습니다.|  
|`(?x)`|줄 끝 주석을 인식하도록 패턴 공백 옵션을 무시하도록 설정합니다.|  
|`# Looks for a composite format item.`|줄 끝 주석입니다.|  
  
 [!code-csharp[RegularExpressions.Language.Miscellaneous#3](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.miscellaneous/cs/miscellaneous3.cs#3)]
 [!code-vb[RegularExpressions.Language.Miscellaneous#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.miscellaneous/vb/miscellaneous3.vb#3)]  
  
 정규식에서 `(?x)` 구문을 제공하는 대신 주석은 <xref:System.Text.RegularExpressions.Regex.IsMatch%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.RegexOptions%29?displayProperty=fullName> 메서드를 호출하고 <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName> 열거형 값을 전달하여 인식할 수도 있습니다.  
  
## 참고 항목  
 [정규식 언어 \- 빠른 참조](../../../docs/standard/base-types/regular-expression-language-quick-reference.md)