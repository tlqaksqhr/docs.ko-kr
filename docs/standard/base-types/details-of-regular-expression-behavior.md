---
title: "정규식 동작 정보 | Microsoft Docs"
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
  - "정규식, 동작"
  - ".NET Framework 정규식, 동작"
ms.assetid: 0ee1a6b8-caac-41d2-917f-d35570021b10
caps.latest.revision: 27
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 27
---
# 정규식 동작 정보
.NET Framework 정규식 엔진은 Perl, Python, Emacs 및 Tcl에서 사용하는 엔진과 같이 기존의 NFA\(Nondeterministic Finite Automaton\) 엔진을 통합하는 역행 정규식 검색 도구입니다.  Regex는 awk, egrep 또는 lex에 있는 엔진과 같이 속도는 빠르지만 더 제한된 순수 정규식 DFA\(Deterministic Finite Automaton\) 엔진과 구별됩니다.  또한 표준화되었지만 속도가 느린 POSIX NFA와도 구별됩니다.  다음 단원에서는 세 가지 유형의 정규식 엔진에 대해 설명하고 .NET Framework에서 정규식이 기존의 NFA 엔진을 사용하여 구현되는 이유에 대해 설명합니다.  
  
## NFA 엔진의 장점  
 DFA 엔진이 패턴 검색을 수행할 때 처리 순서는 입력 문자열에 의해 결정됩니다.  이 엔진은 입력 문자열의 첫 문자에서 시작하여 순차적으로 진행하며 다음 문자가 정규식 패턴과 일치하는지 여부를 확인합니다.  이 엔진을 사용하면 가능한 가장 긴 문자열을 찾을 수 있습니다.  DFA 엔진에서는 동일한 문자를 두 번 테스트하지 않기 때문에 역행 검사가 지원되지 않습니다.  그러나 DFA 엔진은 제한된 상태만 포함할 수 있으므로 역참조를 사용하는 패턴은 검색할 수 없으며, 명시적 확장을 구성할 수 없으므로 하위 식을 캡처할 수 없습니다.  
  
 기존의 NFA 엔진에서 패턴 검색을 수행할 때 처리 순서는 DFA 엔진과 달리 정규식 패턴에 의해 결정됩니다.  이 엔진은 특정 언어 요소를 처리할 때 가능한 많은 입력 문자열과 일치시키는 방법을 사용합니다.  그러나 하위 식을 성공적으로 일치시킨 후 상태를 저장하기도 합니다.  최종적으로 검색에 실패한 경우 이 엔진은 다른 검색을 시도하기 위해 저장된 상태로 복귀할 수 있습니다.  정규식의 뒷부분에 있는 언어 요소도 일치될 수 있도록 성공적인 하위 식 일치를 폐기하는 이 프로세스를 *역행 검사*라고도 합니다.  NFA 엔진에서는 역행 검사를 사용하여 정규식의 가능한 모든 확장을 특정 순서에 따라 테스트하고 첫 번째 일치 항목을 받아 들입니다.  기존의 NFA 엔진은 성공적인 검색을 위해 정규식의 특정 확장을 구성하므로 하위 식 일치 및 일치 역참조를 캡처할 수 있습니다.  그러나 NFA는 역행 검사를 수행하므로 서로 다른 경로를 통해 해당 상태에 도달한 경우 동일한 결과가 여러 번 나올 수 있습니다.  결과적으로 NFA는 최악의 경우에서 상당히 느리게 실행될 수 있습니다.  또한 기존의 NFA 엔진은 첫 번째로 발견된 일치 항목을 받아 들이므로 아직 발견되지 않은 다른 일치 항목\(더 긴 문자열\)을 아예 생략할 가능성도 있습니다.  
  
 POSIX NFA 엔진은 가장 긴 일치 항목을 찾을 때까지 역행 검사를 계속한다는 점을 제외하고는 기존의 NFA 엔진과 같습니다.  결과적으로 POSIX NFA 엔진은 NFA 엔진보다 속도가 느리고 POSIX NFA 엔진을 사용하면 역행 검사 순서를 변경하여 긴 문자열보다 짧은 문자열을 우선시할 수 없습니다.  
  
 프로그래머는 DFA 또는 POSIX NFA 엔진에 비해 문자열 일치에 대한 향상된 제어 수준을 제공하는 기존의 NFA 엔진을 선호합니다.  최악의 경우 실행 속도가 느려질 수 있지만 모호함을 줄이고 역행 검사를 제한하는 패턴을 사용하여 선형 또는 다항 시간으로 일치 항목을 찾도록 엔진을 조정할 수 있습니다.  즉, NFA 엔진은 처리 능력과 유연성을 얻는 대신 성능상의 손실을 감수하지만 정규식이 잘 작성되고 역행 검사로 인해 성능이 기하 급수적으로 저하되는 상황을 방지한다면 대부분의 경우에 만족스런 성능을 제공합니다.  
  
> [!NOTE]
>  과도한 역추적으로 인해 발생하는 성능상의 제약과 이를 해결할 수 있도록 정규식을 만드는 방법에 대한 자세한 내용은 [역행 검사](../../../docs/standard/base-types/backtracking-in-regular-expressions.md)을 참조하십시오.  
  
## .NET Framework 엔진 기능  
 기존 NFA 엔진의 장점을 활용하기 위해 .NET Framework 정규식 엔진은 프로그래머가 역행 검사 엔진을 조정할 수 있도록 하는 완전한 구문 집합을 포함합니다.  이러한 구문을 사용하여 일치 항목을 더 빨리 찾거나 다른 항목보다 특정 확장 항목을 우선시할 수 있습니다.  
  
 .NET Framework 정규식 엔진의 다른 기능은 다음과 같습니다.  
  
-   최소 일치 수량자: : `??`, `*?`, `+?`, `{`*n*`,`*m*`}?`.  이러한 구문은 최소 반복 항목을 먼저 검색하도록 역행 검사 엔진에 지시합니다.  이와 달리 일반적인 최대 수량자는 최대 반복 항목을 먼저 검색합니다.  다음 예제에서는 두 수량자의 차이점을 설명합니다.  정규식은 숫자로 끝나는 문장과 일치하고, 캡처링 그룹은 해당 숫자를 추출하게 되어 있습니다.  정규식 `.+(\d+)\.`에 greedy 수량자 `.+`가 포함되어 있으면 정규식 엔진이 해당 숫자의 마지막 자리만 캡처합니다.  반대로 정규식 `.+?(\d+)\.`에 lazy 수량자 `.+?`가 포함되어 있으면 정규식 엔진이 전체 숫자를 캡처합니다.  
  
     [!code-csharp[Conceptual.RegularExpressions.Design#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.design/cs/lazy1.cs#1)]
     [!code-vb[Conceptual.RegularExpressions.Design#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.design/vb/lazy1.vb#1)]  
  
     이 정규식의 최대 버전과 최소 버전은 다음 표에서와 같이 정의됩니다.  
  
    |패턴|설명|  
    |--------|--------|  
    |`.+`\(greedy 수량자\)|하나 이상의 특정 문자를 찾습니다.  정규식 엔진은 전체 문자열과 일치시킨 다음 패턴의 나머지 부분과 일치시키기 위해 필요에 따라 역행 검사를 수행합니다.|  
    |`.+?`\(lazy 수량자\)|하나 이상의 특정 문자를 찾지만 가능한 한 적은 수의 문자를 찾습니다.|  
    |`(\d+)`|하나 이상의 숫자와 일치시키고 숫자를 첫 번째 캡처링 그룹에 할당합니다.|  
    |`\.`|마침표를 찾습니다.|  
  
     lazy 수량자에 대한 자세한 내용은 [수량자](../../../docs/standard/base-types/quantifiers-in-regular-expressions.md)를 참조하십시오.  
  
-   양수 lookahead: `(?=`*subexpression*`)`.  이 기능을 사용하면 역행 검사 엔진은 하위 식을 검색한 후 텍스트의 같은 지점으로 돌아오기 때문에  이 기능은 같은 위치에서 시작하는 여러 패턴을 확인하여 텍스트 전체를 검색하는 데 유용합니다.  또한 역행 검사 엔진이 일치된 텍스트에 부분 문자열을 포함하지 않아도 일치 항목의 끝에 부분 문자열이 있는지 확인할 수 있게 합니다.  다음 예제에서는 긍정 lookahead를 사용하여 문장 내에서 구두점 기호 앞에 있지 않은 단어를 추출합니다.  
  
     [!code-csharp[Conceptual.RegularExpressions.Design#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.design/cs/lookahead1.cs#2)]
     [!code-vb[Conceptual.RegularExpressions.Design#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.design/vb/lookahead1.vb#2)]  
  
     `\b[A-Z]+\b(?=\P{P})` 정규식은 다음 표에서와 같이 정의됩니다.  
  
    |패턴|설명|  
    |--------|--------|  
    |`\b`|단어 경계에서 일치 항목 찾기를 시작합니다.|  
    |`[A-Z]+`|임의의 영문자를 한 번 이상 찾습니다.  <xref:System.Text.RegularExpressions.Regex.Matches%2A?displayProperty=fullName> 메서드가 <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName> 옵션을 사용하여 호출되므로 비교는 대소문자를 구분하지 않고 수행됩니다.|  
    |`\b`|단어 경계에서 일치 항목 찾기를 끝냅니다.|  
    |`(?=\P{P})`|다음 문자가 구두점 기호인지 여부를 확인하기 위해 왼쪽에서 오른쪽으로 검사합니다.  구두점 기호가 아니면 일치 항목 찾기에 성공합니다.|  
  
     긍정 lookahead 어설션에 대한 자세한 내용은 [그룹화 구문](../../../docs/standard/base-types/grouping-constructs-in-regular-expressions.md)을 참조하십시오.  
  
-   부정 lookahead: `(?!`*subexpression*`)`.  이 기능은 하위 식과 일치하지 않는 경우에만 식을 검색합니다.  이 기능은 때때로 가능한 경우를 제거하는 식을 제공하는 것이 가능한 경우를 포함하는 식을 제공하는 것보다 간단하기 때문에 검색 정리 작업에 특히 유용합니다.  예를 들어, "non"으로 시작하지 않는 단어보다 "non"으로 시작하는 단어를 찾는 것이 더 간단합니다.  다음 예제에서는 음성 lookahead를 사용하여 "non"으로 시작하지 않는 단어를 제외합니다.  
  
     [!code-csharp[Conceptual.RegularExpressions.Design#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.design/cs/lookahead2.cs#3)]
     [!code-vb[Conceptual.RegularExpressions.Design#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.design/vb/lookahead2.vb#3)]  
  
     `\b(?!non)\w+\b` 정규식 패턴은 다음 표에서와 같이 정의됩니다.  
  
    |패턴|설명|  
    |--------|--------|  
    |`\b`|단어 경계에서 일치 항목 찾기를 시작합니다.|  
    |`(?!non)`|현재 문자열이 "non"으로 시작하지 않는지 확인하기 위해 왼쪽에서 오른쪽으로 검사합니다.  "non"으로 시작하면 일치 항목 찾기에 실패합니다.|  
    |`(\w+)`|하나 이상의 단어 문자를 찾습니다.|  
    |`\b`|단어 경계에서 일치 항목 찾기를 끝냅니다.|  
  
     부정 lookahead 어설션에 대한 자세한 내용은 [그룹화 구문](../../../docs/standard/base-types/grouping-constructs-in-regular-expressions.md)을 참조하십시오.  
  
-   조건부 평가: `(?(`*expression*`)`*yes* `|` *no* `)` 및 `(?(`*name*`)`*yes* `|` *no* `)`, 여기서 *expression* 는 일치시킬 하위 식이고, *name*은 캡처링 그룹의 이름이고, *yes* 는 만약 *expression* 가 일치 되거나 *name* 이 유효할 경우 일치시킬 문자열이고, *no*는 *expression* 가 일치하지 않거나 *name* 가 유효하고 비어 있지 않은 캡쳐된 그룹이 아닌 경우 일치시킬 하위 식입니다.  이 기능은 엔진이 이전의 하위 식 일치 결과 또는 너비가 0인 어설션 결과에 따라 둘 이상의 대체 패턴을 사용하여 검색할 수 있게 합니다.  이 기능을 통해 보다 강력한 형태의 역참조\(예: 이전의 하위 식이 일치하는지 여부에 따라 하위 식을 일치시킬 수 있게 허용하는 역참조\)를 사용할 수 있습니다.  다음 예제의 정규식은 공용 및 내부용 단락을 검색합니다.  내부 전용 단락은 `<PRIVATE>` 태그로 시작합니다.  `^(?<Pvt>\<PRIVATE\>\s)?(?(Pvt)((\w+\p{P}?\s)+)|((\w+\p{P}?\s)+))\r?$` 정규식 패턴에서는 조건부 평가를 사용하여 공용 및 내부용 단락의 내용을 별도의 캡처링 그룹에 할당합니다.  이러한 단락은 이후에 서로 다르게 처리할 수 있습니다.  
  
     [!code-csharp[Conceptual.RegularExpressions.Design#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.design/cs/conditional1.cs#4)]
     [!code-vb[Conceptual.RegularExpressions.Design#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.design/vb/conditional1.vb#4)]  
  
     이 정규식 패턴은 다음 표에서와 같이 정의됩니다.  
  
    |패턴|설명|  
    |--------|--------|  
    |`^`|줄 시작 부분에서 일치 항목 찾기를 시작합니다.|  
    |`(?<Pvt>\<PRIVATE\>\s)?`|`<PRIVATE>` 문자열 0개 또는 1개 뒤에 공백 문자 1개가 나오는 경우를 찾습니다.  일치 항목을 `Pvt`라는 캡처링 그룹에 할당합니다.|  
    |`(?(Pvt)((\w+\p{P}?\s)+)`|`Pvt` 캡처링 그룹이 있으면 하나 이상의 단어 문자 뒤에 0개 또는 1개의 구두점 구분 기호와 공백 문자가 차례로 나오는 경우를 하나 이상 찾습니다.  부분 문자열을 첫 번째 캡처링 그룹에 할당합니다.|  
    |`&#124;((\w+\p{P}?\s)+))`|`Pvt` 캡처링 그룹이 없으면 하나 이상의 단어 문자 뒤에 0개 또는 1개의 구두점 구분 기호와 공백 문자가 차례로 나오는 경우를 하나 이상 찾습니다.  부분 문자열을 세 번째 캡처링 그룹에 할당합니다.|  
    |`\r?$`|줄의 끝 또는 문자열의 끝 부분을 찾습니다.|  
  
     조건부 평가에 대한 자세한 내용은 [교체 구문](../../../docs/standard/base-types/alternation-constructs-in-regular-expressions.md)을 참조하십시오.  
  
-   균형 조정 그룹 정의:  `(?<`*name1*`-`*name2*`>` *subexpression*`)`.  이 기능은 괄호 또는 열기 및 닫기 중괄호 같은 중첩 구문을 정규식 엔진이 추적할 수 있게 합니다.  예제를 보려면 [그룹화 구문](../../../docs/standard/base-types/grouping-constructs-in-regular-expressions.md)를 참조하십시오.  
  
-   역추적하지 않는 하위 식\(최대 일치 하위 식\): `(?>`*subexpression*`)`.  이 기능을 사용하면 역행 검사 엔진은 포함하는 식과 상관 없이 식이 실행되는 것처럼, 하위 식이 해당 하위 식에 대해 찾은 첫 번째 일치 항목만 검색하도록 합니다.  이 구문을 사용하지 않는 경우에는 더 큰 식의 역행 검사 결과에 따라 결과 하위 식 동작이 변경될 수 있습니다.  예를 들어 `(a+)\w` 정규식은 하나 이상의 "a" 문자 및 이러한 "a" 문자 뒤에 있는 단어 문자 1개와 일치시키고 일련의 "a" 문자를 첫 번째 캡처링 그룹에 할당합니다. 그러나 입력 문자열의 마지막 문자 역시 "a"인 경우에는 이 문자가 `\w` 언어 요소와 일치하지만 캡처된 그룹에 포함되지는 않습니다.  
  
     [!code-csharp[Conceptual.RegularExpressions.Design#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.design/cs/nonbacktracking2.cs#7)]
     [!code-vb[Conceptual.RegularExpressions.Design#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.design/vb/nonbacktracking2.vb#7)]  
  
     `((?>a+))\w` 정규식은 이러한 동작을 방지합니다.  연속되는 모든 "a" 문자는 역행 검사 없이도 일치하기 때문에 첫 번째 캡처링 그룹에는 연속되는 "a" 문자가 모두 포함됩니다.  "a" 문자 뒤에 "a" 이외의 문자가 하나 이상 있지 않으면 일치 항목 찾기에 실패합니다.  
  
     [!code-csharp[Conceptual.RegularExpressions.Design#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.design/cs/nonbacktracking1.cs#8)]
     [!code-vb[Conceptual.RegularExpressions.Design#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.design/vb/nonbacktracking1.vb#8)]  
  
     역추적하지 않는 하위 식에 대한 자세한 내용은 [그룹화 구문](../../../docs/standard/base-types/grouping-constructs-in-regular-expressions.md)을 참조하십시오.  
  
-   오른쪽에서 왼쪽으로 일치 검사. <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName> 옵션을 <xref:System.Text.RegularExpressions.Regex> 클래스 생성자 또는 정적 인스턴스의 일치 검사 메서드에 제공하여 지정됩니다.  이 기능은 왼쪽에서 오른쪽으로 검색하는 대신 오른쪽에서 왼쪽으로 검색하는 경우 또는 패턴의 왼쪽 부분보다는 패턴의 오른쪽 부분에서 검색을 시작하는 것이 효과적인 경우에 유용합니다.  다음 예제에서 볼 수 있듯이 오른쪽에서 왼쪽으로 일치 검사를 사용하면 greedy 수량자의 동작이 변경될 수 있습니다.  이 예제에서는 숫자로 끝나는 문장을 찾기 위해 두 가지 검색을 수행합니다.  greedy 수량자 `+`를 사용하는 왼쪽에서 오른쪽으로 검색의 경우 6자리를 모두 찾는 오른쪽에서 왼쪽으로 검색과 달리 문장에서 6자리 중 하나를 찾습니다.  정규식 패턴에 대한 설명은 이 단원 앞부분에서 lazy 수량자를 보여 주는 예제를 참조하십시오.  
  
     [!code-csharp[Conceptual.RegularExpressions.Design#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.design/cs/rtl1.cs#6)]
     [!code-vb[Conceptual.RegularExpressions.Design#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.design/vb/rtl1.vb#6)]  
  
     오른쪽에서 왼쪽으로 일치 검사에 대한 자세한 내용은 [정규식 옵션](../../../docs/standard/base-types/regular-expression-options.md)을 참조하십시오.  
  
-   긍정 및 부정 lookbehind: 긍정 lookbehind의 경우 `(?<=`*subexpression*`)`, 부정 lookbehind의 경우 `(?<!`*subexpression*`)`.  이 기능은 이 항목의 앞부분에 설명된 lookahead와 유사합니다.  정규식 엔진을 사용하면 오른쪽에서 왼쪽으로 일치 검사를 완벽하게 수행할 수 있으므로 정규식은 무제한 lookbehind를 허용합니다.  긍정 및 부정 lookbehind는 중첩된 하위 식이 외부 식의 상위 집합인 경우 중첩 수량자를 방지하기 위해 사용될 수도 있습니다.  중첩된 수량자를 포함하는 정규식의 성능이 좋지 않은 경우가 자주 있습니다.  예를 들어 다음 예제에서는 문자열이 영문자로 시작하고 끝나는지 확인하고, 해당 문자열 내의 다른 문자가 보다 큰 하위 집합의 일부인지 확인합니다.  이 예제는 전자 메일 주소의 유효성 검사에 사용되는 정규식의 일부분을 구성합니다. 자세한 내용은 [방법: 문자열이 올바른 전자 메일 형식인지 확인](../../../docs/standard/base-types/how-to-verify-that-strings-are-in-valid-email-format.md)을 참조하십시오.  
  
     [!code-csharp[Conceptual.RegularExpressions.Design#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.design/cs/lookbehind1.cs#5)]
     [!code-vb[Conceptual.RegularExpressions.Design#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.design/vb/lookbehind1.vb#5)]  
  
     `^[A-Z0-9]([-!#$%&'.*+/=?^`{}|~\w])*(?<=[A-Z0-9])$` 정규식은 다음 표에서와 같이 정의됩니다.  
  
    |패턴|설명|  
    |--------|--------|  
    |`^`|문자열의 시작 부분에서 일치 항목 찾기를 시작합니다.|  
    |`[A-Z0-9]`|모든 숫자 또는 영숫자 문자를 찾습니다. 비교 시 대\/소문자는 구분되지 않습니다.|  
    |`([-!#$%&'.*+/=?^`{}&#124;~\w])*`|어떤 단어의 문자 또는 \-, \!, \#, $, %, &, ', ., \*, \+, \/, \=, ?, ^, \`, {, }, &#124;, or ~ 에서 0개 이상 찾습니다.|  
    |`(?<=[A-Z0-9])`|오른쪽에서 왼쪽으로 검색하며 이전 문자를 찾습니다. 이 문자는 숫자 또는 영문자여야 합니다. 비교 시 대\/소문자는 구분되지 않습니다.|  
    |`$`|문자열의 끝 부분에서 일치 항목 찾기를 끝냅니다.|  
  
     긍정 및 부정 lookbehind에 대한 자세한 내용은 [그룹화 구문](../../../docs/standard/base-types/grouping-constructs-in-regular-expressions.md)을 참조하십시오.  
  
## 관련 항목  
  
|제목|설명|  
|--------|--------|  
|[역행 검사](../../../docs/standard/base-types/backtracking-in-regular-expressions.md)|다른 일치 항목을 찾기 위해 정규식 역행 검사가 어떻게 분기되는지에 대한 정보를 제공합니다.|  
|[컴파일 및 다시 사용](../../../docs/standard/base-types/compilation-and-reuse-in-regular-expressions.md)|성능을 높이기 위해 정규식을 컴파일한 후 다시 사용하는 방법에 대한 정보를 제공합니다.|  
|[스레드로부터의 안전성](../../../docs/standard/base-types/thread-safety-in-regular-expressions.md)|정규식에 대한 스레드로부터의 안전성에 관련된 정보를 제공하고 정규식 개체에 대한 액세스를 동기화해야 하는 시기에 대해 설명합니다.|  
|[.NET Framework 정규식](../../../docs/standard/base-types/regular-expressions.md)|정규식의 프로그래밍 언어에 대해 설명합니다.|  
|[Regular Expression 개체 모델](../../../docs/standard/base-types/the-regular-expression-object-model.md)|정규식 클래스의 사용 방법에 관한 내용과 코드 예제를 제공합니다.|  
|[정규식 예제](../../../docs/standard/base-types/regular-expression-examples.md)|공용 응용 프로그램에서 정규식 사용 예를 보여 주는 코드 예제가 포함되어 있습니다.|  
|[정규식 언어 \- 빠른 참조](../../../docs/standard/base-types/regular-expression-language-quick-reference.md)|정규식을 정의하는 데 사용할 수 있는 문자, 연산자 및 구문 집합에 대해 자세히 설명합니다.|  
  
## 참고 항목  
 <xref:System.Text.RegularExpressions?displayProperty=fullName>