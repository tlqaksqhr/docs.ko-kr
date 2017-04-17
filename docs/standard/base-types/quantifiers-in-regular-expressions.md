---
title: "정규식의 수량자 | Microsoft Docs"
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
  - "정규식, 수량자"
  - "메타문자, 수량자"
  - "최소 일치 수량자"
  - "정규식의 수량자"
  - ".NET Framework 정규식, 수량자"
  - "수량자"
  - "최소 일치 수량자"
ms.assetid: 36b81212-6511-49ed-a8f1-ff080415312f
caps.latest.revision: 22
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 22
---
# 정규식의 수량자
수량자는 문자, 그룹 또는 문자 클래스의 인스턴스가 입력에 몇 개 있어야 일치가 검색되는지를 지정합니다.  다음 표에서는 .NET Framework에서 지원하는 수량자를 보여 줍니다.  
  
|greedy 수량자|lazy 수량자|설명|  
|----------------|--------------|--------|  
|`*`|`*?`|0개 이상 찾습니다.|  
|`+`|`+?`|0개 또는 한 개 찾습니다.|  
|`?`|`??`|0개 또는 1개 찾습니다.|  
|`{` *n* `}`|`{` *n* `}?`|정확히 *n* 번 찾습니다.|  
|`{` *n* `,}`|`{` *n* `,}?`|적어도 *n* 번 찾습니다.|  
|`{` *n* `,` *m* `}`|`{` *n* `,` *m* `}?`|*n* 에서 *m* 번 일치시킵니다.|  
  
 수량 `n` 및 `m`은 정수 상수입니다.  일반적으로 수량자 greedy가 있습니다. 정규식 엔진이 가능한 한 많은 특정 패턴의 발생을 일치시킵니다.  `?` 문자를 수량자에 추가하면 지연이 발생합니다. 즉, 정규식 엔진이 가능한 적은 발생으로 일치시키게 됩니다.  greedy 및 lazy 수량자 사이의 차이점에 대한 자세한 설명은 이 항목 뒷부분의 [Greedy 및 Lazy 수량자](#Greedy) 단원을 참조하십시오.  
  
> [!IMPORTANT]
>  중첩 수량자\(예: 정규식 패턴 `(a*)*`임\)에서는 입력 문자열에서 문자 수의 지수 함수로서 정규식 엔진을 수행해야 하는 비교 수가 늘어날 수 있습니다.  이 동작 및 해결 방법에 대한 자세한 내용은 [역행 검사](../../../docs/standard/base-types/backtracking-in-regular-expressions.md)을 참조하십시오.  
  
## 정규식 수량자  
 다음 섹션에서는 .NET Framework 정규식에서 지원되는 수량자를 보여 줍니다.  
  
> [!NOTE]
>  \*, \+, ?, {, and } 문자가 정규식 패턴에 있는 경우 정규식 엔진은 [문자 클래스](../../../docs/standard/base-types/character-classes-in-regular-expressions.md)에 포함되지 않은 한 이를 수량자 또는 수량자 구조의 일부로 해석합니다.  이를 문자 클래스 이외의 리터럴 문자로 해석하려면 앞에 백슬래시를 입력해야 합니다.  예를 들어, 정규식 패턴의 문자열 `\*`는 리터럴 별표\("\*"\) 문자로 해석됩니다.  
  
### 0개 이상 찾습니다: \*  
 `*` 수량자는 이전 요소를 0개 이상 찾습니다.  이는 `{0,}` 수량자와 같습니다.  `*`는 greedy 수량자이며 해당 lazy 수량자는 `*?`입니다.  
  
 다음 예제에서는 이 정규식을 보여 줍니다.  입력 문자열에 있는 숫자 9개 중 5개가 패턴과 일치하고 4개\(`95`, `929`, `9129` 및 `9919`\)는 일치하지 않습니다.  
  
 [!code-csharp[RegularExpressions.Quantifiers#1](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#1)]
 [!code-vb[RegularExpressions.Quantifiers#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#1)]  
  
 이 정규식 패턴은 다음 표에서와 같이 정의됩니다.  
  
|패턴|설명|  
|--------|--------|  
|`\b`|단어 경계를 시작합니다.|  
|`91*`|9 다음에 0 개 이상의 "1"이 있는 문자를 찾습니다.|  
|`9*`|0개 이상의 "9" 문자를 찾습니다.|  
|`\b`|단어 경계를 종료합니다.|  
  
### 한 개 이상 찾습니다: \+  
 `+` 수량자는 이전 요소를 한 개 이상 찾습니다.  이 옵션은 `{1,}`와 같습니다.  `+`는 greedy 수량자이며 해당 lazy 수량자는 `+?`입니다.  
  
 예를 들어 정규식 `\ban+\w*?\b`는 문자 `a`로 시작하고 뒤에 문자 `n`이 한 개 이상 나오는 전체 단어를 찾습니다.  다음 예제에서는 이 정규식을 보여 줍니다.  이 정규식은 단어 `an`, `annual`, `announcement` 및 `antique`와 일치하지만 `autumn` 및 `all`과는 일치하지 않습니다.  
  
 [!code-csharp[RegularExpressions.Quantifiers#2](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#2)]
 [!code-vb[RegularExpressions.Quantifiers#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#2)]  
  
 이 정규식 패턴은 다음 표에서와 같이 정의됩니다.  
  
|패턴|설명|  
|--------|--------|  
|`\b`|단어 경계를 시작합니다.|  
|`an+`|"a" 다음에 하나 이상의 "n" 문자를 찾습니다.|  
|`\w*?`|단어 문자를 0개 이상 찾지만 가능한 적은 개수로 찾습니다.|  
|`\b`|단어 경계를 종료합니다.|  
  
### 0개 또는 1개 찾습니다: ?  
 `?` 수량자는 이전 요소를 0개 또는 한 개 찾습니다.  이 옵션은 `{0,1}`와 같습니다.  `?`는 greedy 수량자이며 해당 lazy 수량자는 `??`입니다.  
  
 예를 들어 정규식 `\ban?\b`는 문자 `a`로 시작하고 뒤에 문자 `n`이 0개 또는 1개 나오는 전체 단어를 찾습니다.  즉, 단어 `a` 및 `an`과 일치합니다.  다음 예제에서는 이 정규식을 보여 줍니다.  
  
 [!code-csharp[RegularExpressions.Quantifiers#3](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#3)]
 [!code-vb[RegularExpressions.Quantifiers#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#3)]  
  
 이 정규식 패턴은 다음 표에서와 같이 정의됩니다.  
  
|패턴|설명|  
|--------|--------|  
|`\b`|단어 경계를 시작합니다.|  
|`an?`|"a" 다음에 0개 또는 한 개 "n" 문자를 찾습니다.|  
|`\b`|단어 경계를 종료합니다.|  
  
### 정확히 n개 찾습니다: {n}  
 `{` *n* `}` 수량자는 이전 요소를 정확히 *n*번 일치시킵니다. 여기서 *n*은 정수입니다.  `{`*n*`}`는 해당 lazy 수량자가 `{`*n*`}?` 인 greedy 수량자 입니다.  
  
 예를 들어 정규식 `\b\d+\,\d{3}\b`는 단어 경계 뒤에 숫자가 하나 이상 나오고 그 뒤에 숫자 세 개가 나온 후 단어 경계가 나오는 경우를 찾습니다.  다음 예제에서는 이 정규식을 보여 줍니다.  
  
 [!code-csharp[RegularExpressions.Quantifiers#4](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#4)]
 [!code-vb[RegularExpressions.Quantifiers#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#4)]  
  
 이 정규식 패턴은 다음 표에서와 같이 정의됩니다.  
  
|패턴|설명|  
|--------|--------|  
|`\b`|단어 경계를 시작합니다.|  
|`\d+`|하나 이상의 10진수 숫자가 일치하는지 확인합니다.|  
|`\,`|쉼표 문자를 찾습니다.|  
|`\d{3}`|세 개의 10진수를 찾습니다.|  
|`\b`|단어 경계를 종료합니다.|  
  
### 최소 n개 이상 찾습니다: {n,}  
 `{` *n* `,}` 수량자는 이전 요소를 최소 *n*번 찾습니다. 여기서 *n* 는 정수 입니다.  `{`*n*`,}` 는 lazy equivalent가 `{`*n*`}?`인 greedy 수량자 입니다.  
  
 예를 들어 정규식 `\b\d{2,}\b\D+`는 단어 경계 뒤에 최소한 숫자 2개가 나오고 그 뒤에 단어 경계가 나온 후 숫자가 아닌 문자가 나오는 경우를 찾습니다.  다음 예제에서는 이 정규식을 보여 줍니다.  `"7 days"`라는 구는 숫자를 하나만 포함하므로 이 정규식과 일치하지 않지만 `"10 weeks and 300 years"`라는 구는 정규식과 일치합니다.  
  
 [!code-csharp[RegularExpressions.Quantifiers#5](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#5)]
 [!code-vb[RegularExpressions.Quantifiers#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#5)]  
  
 이 정규식 패턴은 다음 표에서와 같이 정의됩니다.  
  
|패턴|설명|  
|--------|--------|  
|`\b`|단어 경계를 시작합니다.|  
|`\d{2,}`|두 개 이상의 10진수를 찾습니다.|  
|`\b`|단어 경계를 찾습니다.|  
|`\D+`|하나 이상의 10진수가 아닌 숫자를 찾습니다.|  
  
### n개에서 m개 찾습니다: {n, m}  
 `{` *n* `,` *m* `}` 수량자는 이전 요소를 최소*n*번, *m* 번은 초과하지 않게 일치 시킵니다. 여기서 *n* 및 *m* 은 정수입니다.  `{`*n*`,`*m*`}` 는 해당 lazy equivalent가 `{`*n*`,`*m*`}?`인 greedy 수량자입니다.  
  
 다음 예제에서는 정규식 `(00\s){2,4}`는 두 개의 0이 2\-4회 나온 후 공백이 나오는 경우를 찾습니다.  입력 문자열의 마지막 부분에는 이 패턴이 최대값인 4회가 아닌 5회 포함되어 있습니다.  그러나 이 부분 문자열의 처음 부분\(공백과 다섯 번째 0 쌍\)만 정규식 패턴과 일치합니다.  
  
 [!code-csharp[RegularExpressions.Quantifiers#6](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#6)]
 [!code-vb[RegularExpressions.Quantifiers#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#6)]  
  
### 0개 이상 찾습니다\(지연 일치\): \*?  
 `*?` 수량자는 이전 요소를 0개 이상 가능한 한 적은 개수로 찾습니다.  greedy 수량자 `*`의 lazy 수량자입니다.  
  
 다음 예제에서 `\b\w*?oo\w*?\b` 정규식은 `oo` 문자열이 포함된 모든 단어와 일치합니다.  
  
 [!code-csharp[RegularExpressions.Quantifiers#7](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#7)]
 [!code-vb[RegularExpressions.Quantifiers#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#7)]  
  
 이 정규식 패턴은 다음 표에서와 같이 정의됩니다.  
  
|패턴|설명|  
|--------|--------|  
|`\b`|단어 경계를 시작합니다.|  
|`\w*?`|0개 이상의 단어 문자이지만 가능한 적은 문자를 일치시킵니다.|  
|`oo`|문자열 "oo"를 찾습니다.|  
|`\w*?`|0개 이상의 단어 문자이지만 가능한 적은 문자를 일치시킵니다.|  
|`\b`|단어 경계에서 종료합니다.|  
  
### 0개 또는 한 개 찾습니다\(지연 일치\): \+?  
 `+?` 수량자는 이전 요소를 1개 이상 가능한 한 적은 개수로 찾습니다.  greedy 수량자 `+`의 lazy 수량자입니다.  
  
 예를 들어 정규식 `\b\w+?\b`는 단어 경계로 구분된 하나 이상의 문자를 찾습니다.  다음 예제에서는 이 정규식을 보여 줍니다.  
  
 [!code-csharp[RegularExpressions.Quantifiers#8](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#8)]
 [!code-vb[RegularExpressions.Quantifiers#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#8)]  
  
### 0개 또는 한 개 찾습니다\(지연 일치\): ??  
 `??` 수량자는 이전 요소를 0개 또는 1개 가능한 한 적은 개수로 찾습니다.  greedy 수량자 `?`의 lazy 수량자입니다.  
  
 예를 들어, `^\s*(System.)??Console.Write(Line)??\(??` 정규식은 "Console.Write" 또는 "Console.WriteLine" 문자열을 일치시키려고 시도합니다.  문자열은 "Console" 앞에 "System."도 포함할 수 있으며, 그 다음에 여는 괄호가 올 수 있습니다.  문자열은 줄의 맨 앞에 있어야 하지만 앞에 공백이 나올 수는 있습니다.  다음 예제에서는 이 정규식을 보여 줍니다.  
  
 [!code-csharp[RegularExpressions.Quantifiers#9](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#9)]
 [!code-vb[RegularExpressions.Quantifiers#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#9)]  
  
 이 정규식 패턴은 다음 표에서와 같이 정의됩니다.  
  
|패턴|설명|  
|--------|--------|  
|`^`|입력 스트림의 시작을 찾습니다.|  
|`\s*`|0개 이상의 공백 문자가 일치하는지 확인합니다.|  
|`(System.)??`|문자열 "System." 0개 또는 한 개를 찾습니다.|  
|`Console.Write`|문자열 "Console.Write"에 해당합니다.|  
|`(Line)??`|0 또는 1개의 문자열 "Line"에 해당합니다.|  
|`\(??`|여는 괄호 0개 또는 한 개를 찾습니다.|  
  
### 정확히 n개 찾습니다\(지연 일치\): {n}?  
 `{` *n* `}?` 수량자는 이전 요소를 정확히 `n`번 일치시킵니다. 여기서 *n*은 정수입니다.  greedy 수량자의 lazy 상대는 `{`*n*`}+` 입니다.  
  
 다음 예제에서는 웹 사이트 주소를 식별하는 데 `\b(\w{3,}?\.){2}?\w{3,}?\b` 정규식이 사용되었습니다.  "www.microsoft.com" 및 "msdn.microsoft.com"은 찾지만 "mywebsite" 또는 "mycompany.com"은 찾지 못합니다.  
  
 [!code-csharp[RegularExpressions.Quantifiers#10](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#10)]
 [!code-vb[RegularExpressions.Quantifiers#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#10)]  
  
 이 정규식 패턴은 다음 표에서와 같이 정의됩니다.  
  
|패턴|설명|  
|--------|--------|  
|`\b`|단어 경계를 시작합니다.|  
|`(\w{3,}?\.)`|3개 이상의 단어 문자와 일치하지만 가능한 한 적은 수의 문자로 점 또는 기간 문자가 이어집니다.  이 그룹은 첫 번째 캡처링 그룹입니다.|  
|`(\w{3,}?\.){2}?`|첫 번째 그룹의 패턴을 두 번 찾지만 가능한 적게 찾습니다.|  
|`\b`|단어 경계에서 일치 항목 찾기를 끝냅니다.|  
  
### 최소 n개 이상\(지연 일치\) 찾습니다: {n,}?  
 `{` *n* `,}?` 수량자는 이전 요소를 최소 `n` 번 일치 시킵니다. 여기서 *n* 은 정수이지만 가능한 적은 수입니다.  greedy 수량자의 lazy 상대는 `{`*n*`,}` 입니다.  
  
 이전 단원의 그림에서 `{`*n*`}?` 수량자에 대한 예제를 참조하십시오.  해당 예제의 정규식에서는`{`*n*`,}` 수량자를 사용하여 최소한 3개의 문자 뒤에 마침표가 나오는 문자열을 일치 시킵니다.  
  
### n 및 m 사이를 찾습니다\(지연 일치\): {n, m}?  
 `{` *n* `,` *m* `}?` 수량자는 이전 요소를 `n` 에서 `m` 번 동안 일치시킵니다. 여기서 *n* 과 *m* 는 정수이지만, 가능하면 작은 수 입니다.  greedy 수량자 lazy 상대는 `{`*n*`,`*m*`}` 입니다.  
  
 다음 예제에서 정규식 `\b[A-Z](../../../amples/snippets/visualbasic/VS_Snippets_Remoting/SoapAttributes1/VB/s.vb){1,10}?[.!?]`는 단어가 1\-10개 들어 있는 문장을 찾습니다.  이 정규식은 입력 문자열에서 단어가 18개 들어 있는 문장 하나를 제외하고 모든 문장과 일치합니다.  
  
 [!code-csharp[RegularExpressions.Quantifiers#12](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#12)]
 [!code-vb[RegularExpressions.Quantifiers#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#12)]  
  
 이 정규식 패턴은 다음 표에서와 같이 정의됩니다.  
  
|패턴|설명|  
|--------|--------|  
|`\b`|단어 경계를 시작합니다.|  
|`[A-Z]`|A\-Z의 대문자를 찾습니다.|  
|`(\w*\s+)`|0개 이상의 문자 다음에 한 개 이상의 공백 문자를 찾습니다.  이 그룹은 첫 번째 캡처링 그룹입니다.|  
|`{1,10}?`|이전 패턴을 1개에서 10개 찾으며, 가능한 한 적은 개수로 찾습니다.|  
|`[.!?]`|문장 부호 문자 ".","\!", 또는 "?" 중 하나를 찾습니다.|  
  
<a name="Greedy"></a>   
## Greedy 및 Lazy 수량자  
 여러 수량자에는 두 가지 버전이 있습니다.  
  
-   greedy 버전  
  
     greedy 수량자는 요소를 찾을 때 최대한 많은 횟수를 적용합니다.  
  
-   non\-greedy 또는 lazy 버전  
  
     greedy가 아닌 수량자는 요소를 찾을 때 최대한 적은 횟수를 적용합니다.  단순히 `?`를 추가하여 greedy 수량자를 lazy 수량자로 전환할 수 있습니다.  
  
 신용 카드 번호와 같은 숫자 문자열에서 마지막 네 숫자를 추출하는 단순한 정규식을 예로 들어 봅니다.  `*` greedy 수량자를 사용하는 정규식 버전은 `\b.*([0-9]{4})\b`입니다.  그러나 문자열에 숫자가 두 개 들어 있는 경우 이 정규식은 다음 예제와 같이 두 번째 숫자의 마지막 네 숫자만 일치합니다.  
  
 [!code-csharp[RegularExpressions.Quantifiers.Greedy#1](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers.Greedy/cs/Greedy.cs#1)]
 [!code-vb[RegularExpressions.Quantifiers.Greedy#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers.Greedy/vb/Greedy.vb#1)]  
  
 `*` 수량자는 전체 문자열에서 이전 요소를 최대한 많이 찾으므로 첫 번째 숫자가 정규식과 일치하지 않고 문자열의 끝 부분에서 일치 항목이 검색됩니다.  
  
 이는 올바른 동작이 아닙니다.  대신, `*?` ``  지연 수량자를 사용하여 다음 예제와 같이 두 번호에서 숫자를 추출할 수 있습니다.  
  
 [!code-csharp[RegularExpressions.Quantifiers.Greedy#2](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers.Greedy/cs/Greedy.cs#2)]
 [!code-vb[RegularExpressions.Quantifiers.Greedy#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers.Greedy/vb/Greedy.vb#2)]  
  
 대부분의 경우에는 greedy 수량자와 lazy 수량자를 사용한 정규식에서 동일한 일치 항목을 반환합니다.  서로 다른 결과가 반환되는 가장 일반적인 경우는 모든 문자를 찾는 와일드카드\( `.`\) 메타문자가 사용된 경우입니다.  
  
## 수량자 및 빈 일치 항목  
 수량자 `*`, `+`, 및 `{`*n*`,`*m*`}` 및 그들의 lazy 상대는 최소 캡처 수를 찾은 경우 빈 일치 항목이 지나면 반복되지 않습니다.  이 규칙은 가능한 최대 그룹 캡처 수가 무한이거나 무한에 가까울 경우 수량자가 빈 하위 식에 무한 루프를 입력하지 않도록 합니다.  
  
 예를 들어, 다음 코드는 0개 또는 1개의 "a" 문자를 0회 이상 일치시키는 정규식 패턴 `(a?)*`을 사용하여 <xref:System.Text.RegularExpressions.Regex.Match%2A?displayProperty=fullName> 메서드에 호출 결과를 보여줍니다.  단일 캡처링 그룹은 <xref:System.String.Empty?displayProperty=fullName> 외에도 각 "a"를 캡처하지만 첫 번째 빈 일치로 인해 수량자가 반복을 멈추기 때문에 두 번째 빈 일치가 없습니다.  
  
 [!code-csharp[RegularExpressions.Quantifiers.EmptyMatch#1](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.quantifiers.emptymatch/cs/emptymatch1.cs#1)]
 [!code-vb[RegularExpressions.Quantifiers.EmptyMatch#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.quantifiers.emptymatch/vb/emptymatch1.vb#1)]  
  
 캡처의 최소 및 최대 수를 정의하는 캡처 그룹과 고정 캡처 수를 정의하는 캡처 그룹 간의 실질적인 차이를 확인하려면 `(a\1|(?(1)\1)){0,2}` 및 `(a\1|(?(1)\1)){2}`의 정규식 패턴을 고려합니다.  두 정규식은 다음 표에 표시된 대로 정의된 단일 캡처링 그룹으로 구성됩니다.  
  
|패턴|설명|  
|--------|--------|  
|`(a\1`|첫 번째 캡처 그룹의 값에 따라 "a"와 일치 …|  
|`&#124;(?(1)`|... 또는 첫 번째 캡처된 그룹을 정의했는지 테스트합니다. \(`(?(1)` 구문에서는 캡처링 그룹을 정의하지 않습니다.\)|  
|`\1))`|첫 번째 캡처된 그룹이 있으면 그 값을 일치시킵니다.  그룹이 없으면 이 그룹은 <xref:System.String.Empty?displayProperty=fullName>와 일치합니다.|  
  
 첫 번째 정규식은 0과 두 번 사이에서 이 패턴과 일치하도록 시도하며 두 번째 정규식은 정확히 두 번이 일치하도록 시도합니다.  첫 번째 패턴은 <xref:System.String.Empty?displayProperty=fullName>의 첫 번째 캡처를 사용하여 최소한의 캡처에 도달하기 때문에 `a\1` 일치를 찾으려는 시도를 반복하지 않습니다. `{0,2}` 수량자를 사용하면 마지막 반복에서만 빈 일치가 가능합니다.  이와 반대로 두 번째 정규식은 `a\1`을\(를\) 두 번 평가하기 때문에 실제로 "a"와 일치하며 최소 반복 횟수 2는 빈 일치 항목 이후 엔진이 반복되도록 합니다.  
  
 [!code-csharp[RegularExpressions.Quantifiers.EmptyMatch#2](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.quantifiers.emptymatch/cs/emptymatch4.cs#2)]
 [!code-vb[RegularExpressions.Quantifiers.EmptyMatch#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.quantifiers.emptymatch/vb/emptymatch4.vb#2)]  
  
## 참고 항목  
 [정규식 언어 \- 빠른 참조](../../../docs/standard/base-types/regular-expression-language-quick-reference.md)   
 [역행 검사](../../../docs/standard/base-types/backtracking-in-regular-expressions.md)