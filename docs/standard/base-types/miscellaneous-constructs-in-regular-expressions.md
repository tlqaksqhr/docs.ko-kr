---
title: "정규식의 기타 구문"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- constructs, miscellaneous
- .NET Framework regular expressions, miscellaneous constructs
- regular expressions, miscellaneous constructs
ms.assetid: 7d10d11f-680f-4721-b047-fb136316b4cd
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9b33d196a7af9bc5a1f81c1624bbd98fea074319
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="miscellaneous-constructs-in-regular-expressions"></a>정규식의 기타 구문
.NET의 정규식에는 세 가지 기타 언어 구문이 포함됩니다. 한 구문에서는 정규식 패턴 중간에 특정 일치 옵션을 사용하거나 사용하지 않도록 설정할 수 있습니다. 나머지 두 구문에서는 정규식에 주석을 포함할 수 있습니다.  
  
## <a name="inline-options"></a>인라인 옵션  
 구문을 사용하여 정규식의 일부에 대해 특정 패턴 일치 옵션을 사용하거나 사용하지 않도록 설정할 수 있습니다.  
  
```  
(?imnsx-imnsx)  
```  
  
 물음표 뒤에 사용할 옵션을 나열하고, 빼기 기호 뒤에 사용하지 않을 옵션을 나열합니다. 다음 표는 각 옵션에 대해 설명합니다. 각 옵션에 대한 자세한 내용은 [정규식 옵션](../../../docs/standard/base-types/regular-expression-options.md)을 참조하세요.  
  
|옵션|설명|  
|------------|-----------------|  
|`i`|대/소문자를 구분하지 않는 일치입니다.|  
|`m`|여러 줄 모드입니다.|  
|`n`|명시적 캡처만 해당합니다. 괄호는 캡처링 그룹으로 동작하지 않습니다.|  
|`s`|한 줄 모드입니다.|  
|`x`|이스케이프되지 않은 공백을 무시하고 x-모드 주석을 허용합니다.|  
  
 모든 변경 하 여 정의 된 정규식 옵션에는 `(?imnsx-imnsx)` 포함 그룹의 끝까지 계속 적용 생성 합니다.  
  
> [!NOTE]
>  `(?imnsx-imnsx:` *subexpression* `)` 그룹화 구문은 하위 식에 대 한 동일한 기능을 제공 합니다. 자세한 내용은 [그룹화 구문](../../../docs/standard/base-types/grouping-constructs-in-regular-expressions.md)을 참조하세요.  
  
 다음 예제에서는 `i`, `n`, 및 `x` 옵션 대/소문자 구분 및 명시적 캡처를 사용 하 고 정규식 중에 정규식 패턴에서 공백은 무시 합니다.  
  
 [!code-csharp[RegularExpressions.Language.Miscellaneous#1](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.miscellaneous/cs/miscellaneous1.cs#1)]
 [!code-vb[RegularExpressions.Language.Miscellaneous#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.miscellaneous/vb/miscellaneous1.vb#1)]  
  
 이 예제에서는 두 개의 정규식을 정의합니다. 첫 번째 `\b(D\w+)\s(d\w+)\b` 정규식은 대문자 "D"와 소문자 "d"로 시작하는 두 개의 연속 단어와 일치합니다. 두 번째 `\b(D\w+)(?ixn) \s (d\w+) \b` 정규식은 다음 표에 설명된 대로 인라인 옵션을 사용하여 이 패턴을 수정합니다. 결과를 비교하면 `(?ixn)` 구문의 효과를 확인할 수 있습니다.  
  
|패턴|설명|  
|-------------|-----------------|  
|`\b`|단어 경계를 시작합니다.|  
|`(D\w+)`|대문자 "D"와 하나 이상의 단어 문자를 찾습니다. 첫 번째 캡처 그룹입니다.|  
|`(?ixn)`|이때부터 대/소문자를 구분하지 않고 비교하고, 명시적 캡처만 수행되며, 정규식 패턴의 공백이 무시됩니다.|  
|`\s`|공백 문자를 찾습니다.|  
|`(d\w+)`|대문자 또는 소문자 "d"와 하나 이상의 단어 문자를 찾습니다. 때문에이 그룹은 캡처되지 않음는 `n` (명시적 캡처) 옵션을 사용할 수...|  
|`\b`|단어 경계를 찾습니다.|  
  
## <a name="inline-comment"></a>인라인 주석  
 `(?#` *주석* `)` 구문을 사용 하는 정규식에서 인라인 주석을 포함할 수 있습니다. 정규식 엔진은 주석에서 반환 되는 문자열에 포함 되어 있지만 일부 패턴 일치에서 주석으로 처리를 사용 하지 않습니다는 <xref:System.Text.RegularExpressions.Regex.ToString%2A?displayProperty=nameWithType> 메서드. 주석이 첫 번째 닫는 괄호 문자에서 끝납니다.  
  
 다음 예제에서는 이전 섹션의 예제에서 사용된 첫 번째 정규식 패턴을 반복합니다. 정규식에 두 개의 인라인 주석을 추가하여 비교가 대/소문자를 구분하는지 여부를 나타냅니다. 정규식 패턴 `\b((?# case-sensitive comparison)D\w+)\s((?#case-insensitive comparison)d\w+)\b`는 다음과 같이 정의됩니다.  
  
|패턴|설명|  
|-------------|-----------------|  
|`\b`|단어 경계를 시작합니다.|  
|`(?# case-sensitive comparison)`|주석입니다. 패턴 일치 동작에 영향을 주지 않습니다.|  
|`(D\w+)`|대문자 "D"와 하나 이상의 단어 문자를 찾습니다. 이 그룹은 첫 번째 캡처링 그룹입니다.|  
|`\s`|공백 문자를 찾습니다.|  
|`(?ixn)`|이때부터 대/소문자를 구분하지 않고 비교하고, 명시적 캡처만 수행되며, 정규식 패턴의 공백이 무시됩니다.|  
|`(?#case-insensitive comparison)`|주석입니다. 패턴 일치 동작에 영향을 주지 않습니다.|  
|`(d\w+)`|대문자 또는 소문자 "d"와 하나 이상의 단어 문자를 찾습니다. 두 번째 캡처 그룹입니다.|  
|`\b`|단어 경계를 찾습니다.|  
  
 [!code-csharp[RegularExpressions.Language.Miscellaneous#2](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.miscellaneous/cs/miscellaneous2.cs#2)]
 [!code-vb[RegularExpressions.Language.Miscellaneous#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.miscellaneous/vb/miscellaneous2.vb#2)]  
  
## <a name="end-of-line-comment"></a>줄의 끝 주석  
 숫자 기호 (`#`) 정규식 패턴의 끝에 이스케이프 되지 않은 # 문자부터 시작 하는 줄의 끝까지 계속 됩니다는 x-모드 주석 표시 합니다. 설정 하거나이 구조를 사용 하는 `x` (인라인 옵션)을 통해 다시 실행 하거나 제공는 <xref:System.Text.RegularExpressions.RegexOptions.IgnorePatternWhitespace?displayProperty=nameWithType> 값을 `option` 인스턴스화할 때 매개 변수는 <xref:System.Text.RegularExpressions.Regex> 개체 또는 정적 호출 <xref:System.Text.RegularExpressions.Regex> 메서드.  
  
 다음 예제에서는 줄의 끝 주석 구문을 보여 줍니다. 문자열이 하나 이상의 형식 항목을 포함하는 복합 형식 문자열인지 여부를 결정합니다. 다음 표에서는 정규식 패턴의 구문을 설명합니다.  
  
 `\{\d+(,-*\d+)*(\:\w{1,4}?)*\}(?x) # Looks for a composite format item.`  
  
|패턴|설명|  
|-------------|-----------------|  
|`\{`|여는 중괄호를 찾습니다.|  
|`\d+`|하나 이상의 10진수 숫자가 일치하는지 확인합니다.|  
|`(,-*\d+)*`|선택적 빼기 기호, 하나 이상의 10진수 앞에 나오는 쉼표를 0번 또는 한 번 찾습니다.|  
|`(\:\w{1,4}?)*`|1-4개(최대한 적은 개수)의 공백 문자 앞에 나오는 콜론을 0번 또는 한 번 찾습니다.|  
|`(?#case insensitive comparison)`|인라인 주석입니다. 패턴 일치 동작에 영향을 주지 않습니다.|  
|`\}`|닫는 중괄호를 찾습니다.|  
|`(?x)`|줄의 끝 주석이 인식되도록 패턴 공백 무시 옵션을 사용하도록 설정합니다.|  
|`# Looks for a composite format item.`|줄의 끝 주석입니다.|  
  
 [!code-csharp[RegularExpressions.Language.Miscellaneous#3](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.miscellaneous/cs/miscellaneous3.cs#3)]
 [!code-vb[RegularExpressions.Language.Miscellaneous#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.miscellaneous/vb/miscellaneous3.vb#3)]  
  
 유의 제공 하는 대신는 `(?x)` 생성는 정규식에서 주석 수 인식할 수도 호출 하 여는 <xref:System.Text.RegularExpressions.Regex.IsMatch%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.RegexOptions%29?displayProperty=nameWithType> 메서드에 전달 하는 <xref:System.Text.RegularExpressions.RegexOptions.IgnorePatternWhitespace?displayProperty=nameWithType> 열거형 값입니다.  
  
## <a name="see-also"></a>참고 항목  
 [정규식 언어 - 빠른 참조](../../../docs/standard/base-types/regular-expression-language-quick-reference.md)
