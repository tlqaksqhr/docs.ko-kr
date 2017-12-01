---
title: "정규식의 수량자"
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
- regular expressions, quantifiers
- metacharacters, quantifiers
- minimal matching quantifiers
- quantifiers in regular expressions
- .NET Framework regular expressions, quantifiers
- quantifiers
- lazy quantifiers
ms.assetid: 36b81212-6511-49ed-a8f1-ff080415312f
caps.latest.revision: "22"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ab06aa0c331c8cbd4c8986cced29334046f30264
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="quantifiers-in-regular-expressions"></a>정규식의 수량자
수량자는 찾을 일치 항목의 입력에 있어야 하는 문자, 그룹 또는 문자 클래스의 인스턴스 수를 지정합니다.  다음 테이블에서는 .NET에서 지원하는 수량자를 보여 줍니다.  
  
|탐욕적 수량자|게으른 수량자|설명|  
|-----------------------|---------------------|-----------------|  
|`*`|`*?`|0번 이상 일치합니다.|  
|`+`|`+?`|1번 이상 일치합니다.|  
|`?`|`??`|0번 또는 1번 일치합니다.|  
|`{` *n* `}`|`{` *n* `}?`|정확히 일치  *n*  시간입니다.|  
|`{` *n* `,}`|`{` *n* `,}?`|이상과 일치  *n*  시간입니다.|  
|`{` *n* `,` *분* `}`|`{` *n* `,` *분* `}?`|일치  *n*  를 *m* 시간입니다.|  
  
 수량 `n` 및 `m` 은 정수 상수입니다. 일반적으로 수량자는 탐욕적입니다. 그러면 최대한의 정규식 엔진이 특정 패턴과 일치하게 됩니다. `?` 문자를 수량자에 추가하면 게으른 수량자로 만들 수 있습니다. 그러면 최소한의 정규식 엔진이 일치하게 됩니다. 탐욕적 수량자와 게으른 수량자 간의 차이에 대한 설명은 이 항목의 뒷부분에 나오는 [탐욕적 및 게으른 수량자](#Greedy) 섹션을 참조하세요.  
  
> [!IMPORTANT]
>  예를 들어, 정규식 패턴 `(a*)*`과 같이 수량자가 중첩되면 정규식 엔진이 입력 문자열에 있는 문자 수의 지 수 함수로 수행해야 하는 비교의 수를 증가시킬 수 있습니다. 이 문제 및 해결 방법에 대 한 자세한 내용은 참조 [역 추적](../../../docs/standard/base-types/backtracking-in-regular-expressions.md)합니다.  
  
## <a name="regular-expression-quantifiers"></a>정규식 수량자  
 다음 섹션에는 .NET의 정규식에서 지원하는 수량자를 보여 줍니다.  
  
> [!NOTE]
>  경우는 *, +,?, {, 및} 문자가 있는 정규식 패턴에서 정규식 엔진에 포함 된 경우가 아니면이 수량자 또는 수량자 구조의 일부로 해석 한 [문자 클래스](../../../docs/standard/base-types/character-classes-in-regular-expressions.md)합니다. 이를 문자 클래스 외부의 리터럴 문자로 해석하려면 앞에 백슬래시를 추가하여 이스케이프해야 합니다. 예를 들어 문자열 `\*` 는 리터럴 별표로 정규식 패턴은 해석 ("\*") 문자.  
  
### <a name="match-zero-or-more-times-"></a>0번 이상 일치: *  
 `*` 수량자는 이전 요소를 0번 이상 일치시킵니다. 동일는 `{0,}` 수량자입니다. `*`지연 된 진수 표현은 greedy 수량자 `*?`합니다.  
  
 다음 예제에서는 이 정규식을 설명합니다. 입력 문자열에서 9자리 숫자 중에 5개는 패턴과 일치하고 4개(`95`, `929`, `9129` 및 `9919`)는 일치하지 않습니다.  
  
 [!code-csharp[RegularExpressions.Quantifiers#1](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#1)]
 [!code-vb[RegularExpressions.Quantifiers#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#1)]  
  
 이 정규식 패턴은 다음 테이블과 같이 정의됩니다.  
  
|패턴|설명|  
|-------------|-----------------|  
|`\b`|단어 경계를 시작합니다.|  
|`91*`|뒤에 0개 이상의 "1" 문자가 있는 "9"를 찾습니다.|  
|`9*`|0개 이상의 "9" 문자를 찾습니다.|  
|`\b`|단어 경계를 종료합니다.|  
  
### <a name="match-one-or-more-times-"></a>1번 이상 일치: +  
 `+` 수량자는 이전 요소를 한 번 이상 찾습니다. 동일 `{1,}`합니다. `+`지연 된 진수 표현은 greedy 수량자 `+?`합니다.  
  
 예를 들어, 정규식 `\ban+\w*?\b`은 `n` 문자의 인스턴스가 하나 이상 뒤에 오는 `a` 문자로 시작하는 전체 단어를 찾으려고 합니다. 다음 예제에서는 이 정규식을 설명합니다. 정규식은 `an`, `annual`, `announcement` 및 `antique` 단어를 찾며 `autumn` 및 `all` 단어를 찾는 데 실패합니다.  
  
 [!code-csharp[RegularExpressions.Quantifiers#2](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#2)]
 [!code-vb[RegularExpressions.Quantifiers#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#2)]  
  
 이 정규식 패턴은 다음 테이블과 같이 정의됩니다.  
  
|패턴|설명|  
|-------------|-----------------|  
|`\b`|단어 경계를 시작합니다.|  
|`an+`|뒤에 하나 이상의 "n" 문자가 있는 "a"를 찾습니다.|  
|`\w*?`|단어 문자와 0번 이상의 일치하지만 가능한 적은 수로 일치합니다.|  
|`\b`|단어 경계를 종료합니다.|  
  
### <a name="match-zero-or-one-time-"></a>0번 또는 1번 일치: ?  
 `?` 수량자는 이전 요소를 0 개 또는 1 개 찾습니다. 동일 `{0,1}`합니다. `?`지연 된 진수 표현은 greedy 수량자 `??`합니다.  
  
 예를 들어, 정규식 `\ban?\b`은 `n` 문자의 인스턴스가 0개 또는 1개 뒤에 오는 `a` 문자로 시작하는 전체 단어를 찾으려고 합니다. 즉, 단어 `a` 및 `an`를 찾으려고 합니다. 다음 예제에서는 이 정규식을 설명합니다.  
  
 [!code-csharp[RegularExpressions.Quantifiers#3](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#3)]
 [!code-vb[RegularExpressions.Quantifiers#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#3)]  
  
 이 정규식 패턴은 다음 테이블과 같이 정의됩니다.  
  
|패턴|설명|  
|-------------|-----------------|  
|`\b`|단어 경계를 시작합니다.|  
|`an?`|뒤에 0개 또는 1개의 "n" 문자가 있는 "a"를 찾습니다.|  
|`\b`|단어 경계를 종료합니다.|  
  
### <a name="match-exactly-n-times-n"></a>정확히 n번 일치: {n}  
 `{`  *n*  `}` 수량자는 이전 요소를 정확 하 게 일치  *n*  시간, where  *n* 는 모든 정수입니다. `{`*n*`}`지연 된 진수 표현은 greedy 수량자 `{`  *n*  `}?`합니다.  
  
 예를 들어, 정규식 `\b\d+\,\d{3}\b`는 뒤에 하나 이상의 10진수 숫자, 세 개의 10진수 숫자와 단어 경계가 있는 단어 경계를 찾으려고 합니다. 다음 예제에서는 이 정규식을 설명합니다.  
  
 [!code-csharp[RegularExpressions.Quantifiers#4](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#4)]
 [!code-vb[RegularExpressions.Quantifiers#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#4)]  
  
 이 정규식 패턴은 다음 테이블과 같이 정의됩니다.  
  
|패턴|설명|  
|-------------|-----------------|  
|`\b`|단어 경계를 시작합니다.|  
|`\d+`|하나 이상의 10진수 숫자가 일치하는지 확인합니다.|  
|`\,`|쉼표 문자를 찾습니다.|  
|`\d{3}`|세 개의 10진수를 찾습니다.|  
|`\b`|단어 경계를 종료합니다.|  
  
### <a name="match-at-least-n-times-n"></a>적어도 n번 일치: {n,}  
 `{`  *n*  `,}` 수량자는 이전 요소 이상  *n*  시간, where  *n* 는 모든 정수입니다. `{`*n*`,}`지연 된 진수 표현은 greedy 수량자 `{`  *n*  `}?`합니다.  
  
 예를 들어, 정규식 `\b\d{2,}\b\D+`는 뒤에 적어도 두 개의 숫자, 단어 경계와 숫자가 아닌 문자가 있는 단어 경계를 찾으려고 합니다. 다음 예제에서는 이 정규식을 설명합니다. 정규식과 라는 구가 일치 하지 `"7 days"` 하나의 10 진수 숫자를 포함 하지만 구과 일치 하기 때문에 `"10 weeks and 300 years"`합니다.  
  
 [!code-csharp[RegularExpressions.Quantifiers#5](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#5)]
 [!code-vb[RegularExpressions.Quantifiers#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#5)]  
  
 이 정규식 패턴은 다음 테이블과 같이 정의됩니다.  
  
|패턴|설명|  
|-------------|-----------------|  
|`\b`|단어 경계를 시작합니다.|  
|`\d{2,}`|적어도 두 개의 10진수를 찾습니다.|  
|`\b`|단어 경계를 찾습니다.|  
|`\D+`|적어도 하나의 10진수가 아닌 수를 찾습니다.|  
  
### <a name="match-between-n-and-m-times-nm"></a>n번에서 m번 사이에 일치: {n, m}  
 `{`  *n*  `,` *m* `}` 수량자는 이전 요소 이상  *n*  시간, 하지만 개 이하의 *m* 시간, where  *n*  및 *m* 는 정수입니다. `{`*n*`,`*m* `}` 지연 표현은 해당 greedy 수량자 `{`  *n*  `,` *m*`}?`합니다.  
  
 다음 예제에서 정규식 `(00\s){2,4}`은 뒤에 공백이 있는 두 개의 숫자 0이 2회에서 4회 사이에 발생하는 경우를 찾습니다. 입력 문자열의 마지막 부분에는 이 패턴이 5번이나 포함됩니다(최대 4번 아님). 그러나 공백 및 0의 다섯 번째 쌍까지의 하위 문자열의 처음 부분만이 정규식 패턴과 일치합니다.  
  
 [!code-csharp[RegularExpressions.Quantifiers#6](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#6)]
 [!code-vb[RegularExpressions.Quantifiers#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#6)]  
  
### <a name="match-zero-or-more-times-lazy-match-"></a>0번 이상 일치(게으른 일치 항목): *?  
 `*?` 수량자는 이전 요소를 0 개 이상 가능한 한 적은 개수로 찾습니다. 그는 greedy 수량자 지연에 관련 `*`합니다.  
  
 다음 예제에서 정규식 `\b\w*?oo\w*?\b`은 문자열 `oo`이 포함된 모든 단어를 찾습니다.  
  
 [!code-csharp[RegularExpressions.Quantifiers#7](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#7)]
 [!code-vb[RegularExpressions.Quantifiers#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#7)]  
  
 이 정규식 패턴은 다음 테이블과 같이 정의됩니다.  
  
|패턴|설명|  
|-------------|-----------------|  
|`\b`|단어 경계를 시작합니다.|  
|`\w*?`|0개 이상의 단어 문자(가능한 한 적은 문자)를 찾습니다.|  
|`oo`|"oo" 문자열을 찾습니다.|  
|`\w*?`|0개 이상의 단어 문자(가능한 한 적은 문자)를 찾습니다.|  
|`\b`|단어 경계를 종료합니다.|  
  
### <a name="match-one-or-more-times-lazy-match-"></a>0번 이상 일치(게으른 일치 항목): +?  
 `+?` 수량자는 이전 요소를 하나 이상 가능한 한 적은 개수로 찾습니다. 그는 greedy 수량자 지연에 관련 `+`합니다.  
  
 예를 들어, 정규식 `\b\w+?\b`은 단어 경계로 구분된 1개 이상의 문자를 찾습니다. 다음 예제에서는 이 정규식을 설명합니다.  
  
 [!code-csharp[RegularExpressions.Quantifiers#8](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#8)]
 [!code-vb[RegularExpressions.Quantifiers#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#8)]  
  
### <a name="match-zero-or-one-time-lazy-match-"></a>0번 또는 1번 일치(게으른 일치): ??  
 `??` 수량자는 이전 요소를 0 개 또는 1 개, 가능한 한 적은 개수로 찾습니다. 그는 greedy 수량자 지연에 관련 `?`합니다.  
  
 예를 들어, 정규식 `^\s*(System.)??Console.Write(Line)??\(??`은 "Console.Write" 또는 "Console.WriteLine" 문자열을 찾으려고 합니다. 문자열은 "Console" 앞에 "System."을 포함할 수도 있고 문자열 뒤에 여는 괄호가 있을 수 있습니다. 문자열 앞에는 공백이 있을 수 있지만 줄의 시작 부분에 있어야 합니다. 다음 예제에서는 이 정규식을 설명합니다.  
  
 [!code-csharp[RegularExpressions.Quantifiers#9](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#9)]
 [!code-vb[RegularExpressions.Quantifiers#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#9)]  
  
 이 정규식 패턴은 다음 테이블과 같이 정의됩니다.  
  
|패턴|설명|  
|-------------|-----------------|  
|`^`|입력 스트림의 시작 부분을 찾습니다.|  
|`\s*`|0개 이상의 공백 문자가 일치하는지 확인합니다.|  
|`(System.)??`|"System."이라는 0개 또는 1개의 문자열을 찾습니다.|  
|`Console.Write`|"Console.Write"라는 문자열을 찾습니다.|  
|`(Line)??`|"Line"이라는 0개 또는 1개의 문자열을 찾습니다.|  
|`\(??`|0개 또는 1개의 여는 괄호를 찾습니다.|  
  
### <a name="match-exactly-n-times-lazy-match-n"></a>정확히 n번 일치(게으른 일치): {n}?  
 `{`  *n*  `}?` 수량자는 이전 요소를 정확 하 게 일치 `n` 시간, where  *n*  는 모든 정수입니다. 그는 greedy 수량자 지연에 관련 `{`  *n*  `}+`합니다.  
  
 다음 예제에서 정규식 `\b(\w{3,}?\.){2}?\w{3,}?\b`은 웹 사이트 주소를 식별하는 데 사용됩니다. "www.microsoft.com" 및 "msdn.microsoft.com"과 일치하지만 "mywebsite" 또는 "mycompany.com"과 일치하지 않습니다.  
  
 [!code-csharp[RegularExpressions.Quantifiers#10](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#10)]
 [!code-vb[RegularExpressions.Quantifiers#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#10)]  
  
 이 정규식 패턴은 다음 테이블과 같이 정의됩니다.  
  
|패턴|설명|  
|-------------|-----------------|  
|`\b`|단어 경계를 시작합니다.|  
|`(\w{3,}?\.)`|뒤에 점 또는 마침표 문자가 있는 가능한 적은 수의 최소한 3개의 단어 문자를 찾습니다. 이 그룹은 첫 번째 캡처링 그룹입니다.|  
|`(\w{3,}?\.){2}?`|첫 번째 그룹의 패턴과 두 번 일치하지만 가능한 적은 수로 일치합니다.|  
|`\b`|단어 경계에서 일치 항목 찾기를 끝냅니다.|  
  
### <a name="match-at-least-n-times-lazy-match-n"></a>적어도 n번 일치(게으른 일치): {n,}?  
 `{`  *n*  `,}?` 수량자는 이전 요소 이상 `n` 시간, where  *n*  은 임의의 정수를 적은 횟수 가능한 합니다. 그는 greedy 수량자 지연에 관련 `{`  *n*  `,}`합니다.  
  
 예를 참조는 `{`  *n*  `}?` 수량자에 대 한 예시는 이전 섹션에 있습니다. 이 예에서는 정규식을 사용 하는 `{`  *n*  `,}` 수량자 뒤에 마침표 3 개 이상의 문자가 있는 문자열을 검색 하도록 합니다.  
  
### <a name="match-between-n-and-m-times-lazy-match-nm"></a>n번에서 m번 사이에 일치(게으른 일치): {n,m}?  
 `{`  *n*  `,` *m* `}?` 수량자는 이전 요소 `n` 및 `m` 시간, where  *n*  및 *m* 가능한 한 적은 개수로 정수입니다. 그는 greedy 수량자 지연에 관련 `{`  *n*  `,` *m*`}`합니다.  
  
 다음 예제에서 정규식 `\b[A-Z](\w*\s+){1,10}?[.!?]`은 하나에서 열 개 단어 사이를 포함하는 문장을 찾습니다. 18개의 단어가 포함된 한 문장을 제외하고 입력 문자열에 있는 모든 문장을 찾습니다.  
  
 [!code-csharp[RegularExpressions.Quantifiers#12](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#12)]
 [!code-vb[RegularExpressions.Quantifiers#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#12)]  
  
 이 정규식 패턴은 다음 테이블과 같이 정의됩니다.  
  
|패턴|설명|  
|-------------|-----------------|  
|`\b`|단어 경계를 시작합니다.|  
|`[A-Z]`|A-Z의 대문자를 찾습니다.|  
|`(\w*\s+)`|뒤에 1개 이상의 공백 문자가 있는 0개 이상의 단어 문자를 찾습니다. 이 그룹은 첫 번째 캡처 그룹입니다.|  
|`{1,10}?`|이전 패턴과 1번에서 10번 사이에 일치하지만 가능한 적은 수로 일치합니다.|  
|`[.!?]`|문장 부호 문자 ".", "!" 또는 "?" 중 하나를 찾습니다.|  
  
<a name="Greedy"></a>   
## <a name="greedy-and-lazy-quantifiers"></a>탐욕적 및 게으른 수량자  
 여러 수량자에는 두 가지 버전이 있습니다.  
  
-   탐욕적 버전  
  
     탐욕적 수량자는 요소를 최대한 많이 찾으려고 합니다.  
  
-   식별 (또는 지연) 버전입니다.  
  
     탐욕적이 아닌 수량자는 요소를 최대한 적게 찾으려고 합니다. 추가 하기만 하면 lazy 수량자도 greedy 수량자를 바꿀 수 있습니다는 `?`합니다.  
  
 신용 카드 번호와 같은 숫자 문자열에서 마지막 4자리를 추출하기 위한 간단한 정규식을 사용합니다. 사용 하는 정규식의 버전은 `*` greedy 수량자는 `\b.*([0-9]{4})\b`합니다. 그러나 문자열이 두 개의 숫자를 포함하는 경우 다음 예제와 같이 정규식은 두 번째 숫자의 마지막 4자리가 일치합니다.  
  
 [!code-csharp[RegularExpressions.Quantifiers.Greedy#1](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers.Greedy/cs/Greedy.cs#1)]
 [!code-vb[RegularExpressions.Quantifiers.Greedy#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers.Greedy/vb/Greedy.vb#1)]  
  
 정규식과 때문에 첫 번째 숫자 일치 하지는 `*` 수량자는 전체 문자열에서 최대한 많이 이전 요소를 일치 시 키 려 고 문자열의 끝에서 찾기를 검색 합니다.  
  
 이러한 동작이 발생하지 않아야 합니다. 대신 사용할 수는 `*?`lazy 수량자 다음 예제와 같이 두 숫자 모두에서 숫자를 추출 하 합니다.  
  
 [!code-csharp[RegularExpressions.Quantifiers.Greedy#2](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers.Greedy/cs/Greedy.cs#2)]
 [!code-vb[RegularExpressions.Quantifiers.Greedy#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers.Greedy/vb/Greedy.vb#2)]  
  
 대부분의 경우 탐욕적 및 게으른 수량자를 포함하는 정규식은 동일한 일치 항목을 반환합니다. 와일드 카드 사용 될 때 가장 일반적으로 서로 다른 결과 반환 (`.`) 메타 문자가 있는 모든 문자를 찾습니다.  
  
## <a name="quantifiers-and-empty-matches"></a>수량자 및 빈 일치 항목  
 수량자 `*`, `+`, 및 `{`  *n*  `,` *m* `}` 지연 대응 하지는 빈 후 반복 일치 하는 최소한의 캡처를 찾았습니다. 가능한 그룹 캡처의 최대 수가 무한 또는 거의 무한인 경우 이 규칙은 수량자가 빈 하위 식을 찾기 위해 무한 루프를 입력하지 않도록 방지합니다.  
  
 다음 코드에 대 한 호출의 결과 표시 하는 예를 들어는 <xref:System.Text.RegularExpressions.Regex.Match%2A?displayProperty=nameWithType> 메서드는 정규식 패턴을 가진 `(a?)*`, 0 개 또는 1 "a" 문자 0 회 이상 찾는 합니다. 단일 캡처링 그룹 결과 캡처할 "a"를 참고 뿐만 아니라 <xref:System.String.Empty?displayProperty=nameWithType>는 없지만 첫 번째 빈 일치 인해 수량자가 반복을 멈추기 때문에 두 번째 빈 일치 하지 않는 합니다.  
  
 [!code-csharp[RegularExpressions.Quantifiers.EmptyMatch#1](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.quantifiers.emptymatch/cs/emptymatch1.cs#1)]
 [!code-vb[RegularExpressions.Quantifiers.EmptyMatch#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.quantifiers.emptymatch/vb/emptymatch1.vb#1)]  
  
 캡처의 최소 및 최대 수를 정의하는 캡처링 그룹과 캡처의 고정 수를 정의하는 그룹 사이의 실질적인 차이를 확인하려면 정규식 패턴 `(a\1|(?(1)\1)){0,2}` 및 `(a\1|(?(1)\1)){2}`를 사용하는 것이 좋습니다. 두 정규식은 단일 캡처링 그룹으로 구성되며 다음 테이블과 같이 정의됩니다.  
  
|패턴|설명|  
|-------------|-----------------|  
|`(a\1`|첫 번째 캡처된 그룹의 값과 함께 "a"를 찾거나…|  
|`&#124;(?(1)`|… 또는 첫 번째 캡처된 그룹이 정의되어 있는지 여부를 테스트합니다. (유의 `(?(1)` 구문의 캡처링 그룹을 정의 하지 않습니다.)|  
|`\1))`|첫 번째 캡처된 그룹이 있는 경우 해당 값을 찾습니다. 해당 그룹이 그룹 일치 합니다 <xref:System.String.Empty?displayProperty=nameWithType>합니다.|  
  
 첫 번째 정규식이 0번과 두 번 사이에 이 패턴을 찾으려 합니다. 두 번째 정규식은 정확히 두 번입니다. 첫 번째 패턴의 첫 번째 캡처와 캡처의 최소 수에 도달 하기 때문에 <xref:System.String.Empty?displayProperty=nameWithType>를 일치 시 키 려 반복 하지 않습니다 `a\1`; `{0,2}` 수량자 마지막 반복에서 빈만 일치 항목을 허용 합니다. 두 번째 정규식이 `a\1`을 두 번째로 평가하기 때문에 "a"를 찾는 반면 반복의 최소수인 2는 빈 일치 항목 뒤에 엔진이 반복되도록 강제합니다.  
  
 [!code-csharp[RegularExpressions.Quantifiers.EmptyMatch#2](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.quantifiers.emptymatch/cs/emptymatch4.cs#2)]
 [!code-vb[RegularExpressions.Quantifiers.EmptyMatch#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.quantifiers.emptymatch/vb/emptymatch4.vb#2)]  
  
## <a name="see-also"></a>참고 항목  
 [정규식 언어 - 빠른 참조](../../../docs/standard/base-types/regular-expression-language-quick-reference.md)  
 [역추적](../../../docs/standard/base-types/backtracking-in-regular-expressions.md)
