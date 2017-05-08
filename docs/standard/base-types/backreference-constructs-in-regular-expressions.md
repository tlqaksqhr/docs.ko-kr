---
title: "정규식의 역참조 구문 | Microsoft Docs"
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
  - ".NET Framework 정규식, 역참조 구문"
  - "역참조"
  - "생성, 역참조"
  - "정규식, 역참조 구문"
ms.assetid: 567a4b8d-0e79-49dc-8df9-f4b1aa376a2a
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# 정규식의 역참조 구문
역참조는 문자열 내에서 반복되는 문자나 하위 문자열을 식별하는 편리한 방법을 제공합니다.  예를 들어, 입력 문자열에 임의의 부분 문자열이 여러 개 있으면 캡처 그룹을 사용하여 첫 번째로 나타나는 부분 문자열을 찾은 다음 역참조를 사용하여 이후에 나타나는 부분 문자열을 찾을 수 있습니다.  
  
> [!NOTE]
>  별도의 구문은 교체 문자열에서 명명되고 번호가 매겨진 캡처링 그룹을 참조하는 데 사용됩니다.  자세한 내용은 [대체](../../../docs/standard/base-types/substitutions-in-regular-expressions.md)을 참조하십시오.  
  
 .NET Framework는 번호 매기기 및 명명된 캡처링 그룹을 참조하는 별도의 언어 요소를 정의합니다.  캡처링 그룹에 대한 자세한 내용은 [그룹화 구문](../../../docs/standard/base-types/grouping-constructs-in-regular-expressions.md)를 참조하십시오.  
  
## 번호가 지정된 역참조.  
 번호 매기기 역참조는 다음 구문을 사용합니다.  
  
 `\` *number*  
  
 *number* 는 정규식에 있는 캡처링 그룹의 서수 위치입니다.  예를 들어, `\4`은 4번째 캡처링 그룹의 내용을 찾습니다.  *number* 이 정규식 패턴에 정의되지 않은 경우 구문 분석 오류가 발생하고 정규식 엔진이 <xref:System.ArgumentException> 를 throw합니다.  예를 들어, 정규식 `(\w+)`이 식에 있는 첫 번째이자 유일한 캡처링 그룹이기 때문에 정규식 `\b(\w+)\s\1`는 유효합니다.  반면에 `\b(\w+)\s\2`는 유효하지 않으며 `\2` 번호 지정된 캡처링 그룹이 없기 때문에 인수 예외를 throw합니다.  
  
 8진수 이스케이프 코드\(예: `\16`\) 및 동일한 표기법을 사용하는 `\`*number* 역참조 간의 모호성에 유의하십시오.  이러한 모호성은 다음과 같이 해결됩니다.  
  
-   식 `\1` ~ `\9`는 항상8진수 코드가 아닌 역참조로 해석됩니다.  
  
-   두 자릿수 이상으로 된 식이 8 또는 9\(예: `\80` 또는 `\91`\)인 경우 식은 리터럴로 해석됩니다.  
  
-   해당 번호에 해당하는 역참조가 있을 경우 `\10`보다 큰 식은 역참조로 간주되고, 그렇지 않으면, 8진수 코드로 해석됩니다.  
  
-   정의되지 않은 그룹 숫자에 대한 역참조가 정규식에 포함되어 있으면 구문 분석 오류가 발생하고 정규식 엔진이 <xref:System.ArgumentException>를 throw합니다.  
  
 모호성이 문제가 되는 경우에는 명백하고 8진법 문자 코드와 혼동되지 않는 `\k<`*name*`>` 표기법을 사용할 수 있습니다.  마찬가지로, `\xdd` 같은 16진수 코드는 모호하지 않으며 역참조와 혼동을 일으키지 않습니다.  
  
 다음 예제에서는 문자열에서 중복된 단어 문자를 찾습니다.  다음과 같은 요소로 구성되는 정규식 `(\w)\1`을 정의합니다.  
  
|요소|설명|  
|--------|--------|  
|`(\w)`|단어 문자를 찾고 첫 번째 캡처링 그룹에 할당합니다.|  
|`\1`|첫 번째 캡처 그룹의 값과 동일한 다음 문자를 찾습니다.|  
  
 [!code-csharp[RegularExpressions.Language.Backreferences#1](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.backreferences/cs/backreference1.cs#1)]
 [!code-vb[RegularExpressions.Language.Backreferences#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.backreferences/vb/backreference1.vb#1)]  
  
## 명명된 역참조.  
 명명된 역참조는 다음 구문을 사용하여 정의됩니다.  
  
 `\k<` *name* `>`  
  
 또는  
  
 `\k'` *name* `'`  
  
 *name* 은 정규식 패턴에 정의된 캡처링 그룹의 이름입니다.  *name* 이 정규식 패턴에 정의되지 않은 경우 구문 분석 오류가 발생하고 정규식 엔진이 <xref:System.ArgumentException> 를 throw합니다.  
  
 다음 예제에서는 문자열에서 중복된 단어 문자를 찾습니다.  다음과 같은 요소로 구성되는 정규식 `(?<char>\w)\k<char>`을 정의합니다.  
  
|요소|설명|  
|--------|--------|  
|`(?<char>\w)`|단어 문자를 찾고 `char`라는 캡처링 그룹에 할당합니다.|  
|`\k<char>`|`char` 캡처 그룹의 값과 동일한 다음 문자를 찾습니다.|  
  
 [!code-csharp[RegularExpressions.Language.Backreferences#2](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.backreferences/cs/backreference2.cs#2)]
 [!code-vb[RegularExpressions.Language.Backreferences#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.backreferences/vb/backreference2.vb#2)]  
  
 *name* 은 숫자의 문자열 표현이 될 수도 있습니다.  예를 들어, 다음 예제에서는 정규식 `(?<2>\w)\k<2>`를 사용하여 문자열에서 중복된 단어 문자를 찾습니다.  
  
 [!code-csharp[RegularExpressions.Language.Backreferences#3](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.backreferences/cs/backreference3.cs#3)]
 [!code-vb[RegularExpressions.Language.Backreferences#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.backreferences/vb/backreference3.vb#3)]  
  
## 역참조가 검색하는 내용  
 역참조는 가장 최근의 그룹 정의\(왼쪽으로 오른쪽으로 검색하는 경우 가장 왼쪽에 있는 정의\)를 참조합니다.  그룹에서 여러 개의 캡처를 만드는 경우 역참조는 가장 최근의 캡처를 참조합니다.  
  
 다음 예제에서는 이름이 \\1인 그룹을 다시 정의하는 정규식 패턴 `(?<1>a)(?<1>\1b)*`가 포함됩니다.  다음 표에서는 정규식의 각 패턴을 설명합니다.  
  
|패턴|설명|  
|--------|--------|  
|`(?<1>a)`|문자 "a"를 찾고 `1`이라는 캡처링 그룹에 결과를 할당합니다.|  
|`(?<1>\1b)*`|"b"와 함께 `1`이라는 그룹의 0 또는 1 발생을 일치시키고 결과를 `1`이라는 캡처링 그룹에 할당합니다.|  
  
 [!code-csharp[RegularExpressions.Language.Backreferences#4](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.backreferences/cs/backreference4.cs#4)]
 [!code-vb[RegularExpressions.Language.Backreferences#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.backreferences/vb/backreference4.vb#4)]  
  
 정규식을 입력 문자열\("aababb"\)과 비교할 때 정규식 엔진은 다음 작업을 수행합니다.  
  
1.  문자열의 시작 부분에서 시작하여 `(?<1>a)` 식을 사용하여 "a"를 성공적으로 찾습니다.  `1` 그룹의 값은 이제 "a"입니다.  
  
2.  두 번째 문자 앞으로 이동하고 식 `\1b`를 사용하여 문자열 "ab" 또는 "ab"를 추가합니다.  그런 다음 결과 "ab"를 `\1`에 할당합니다.  
  
3.  네 번째 문자 앞으로 이동합니다.  식 `(?<1>\1b)`는 0번 이상 일치되므로 문자열 "abb"를 식 `\1b`와 성공적으로 일치됩니다.  결과 "abb"를 다시 `\1` 에 할당합니다.  
  
 이 예제에서 `*`는 루핑 수량자입니다. 정규식 엔진이 정의하는 패턴을 일치시킬 수 없을 때까지 반복적으로 계산됩니다.  반복 수량자는 그룹 정의를 제거하지 않습니다.  
  
 그룹에서 부분 문자열을 캡처링하지 않은 경우 해당 그룹에 대한 역참조는 정의되지 않으며 검색되지 않습니다.  이는 정규식 패턴 `\b(\p{Lu}{2})(\d{2})?(\p{Lu}{2})\b`에 나와 있으며 다음과 같이 정의됩니다.  
  
|패턴|설명|  
|--------|--------|  
|`\b`|단어 경계에서 일치 항목 찾기를 시작합니다.|  
|`(\p{Lu}{2})`|두 개의 대문자를 찾습니다.  이 그룹은 첫 번째 캡처링 그룹입니다.|  
|`(\d{2})?`|두 개의 10진수 0개 또는 한 개를 찾습니다.  이 그룹은 두 번째 캡처링 그룹입니다.|  
|`(\p{Lu}{2})`|두 개의 대문자를 찾습니다.  이 그룹은 세 번째 캡처링 그룹입니다.|  
|`\b`|단어 경계에서 일치 항목 찾기를 끝냅니다.|  
  
 입력 문자열은 두 번째 캡처링 그룹에 의해 정의된 두 소수 자릿수가 없는 경우에도 이 정규식을 일치시킬 수 있습니다.  다음 예제에서는 일치가 성공하더라도 두 성공적인 캡처링 그룹 사이에서 빈 캡처링 그룹이 발견되는 것을 보여줍니다.  
  
 [!code-csharp[RegularExpressions.Language.Backreferences#5](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.backreferences/cs/backreference5.cs#5)]
 [!code-vb[RegularExpressions.Language.Backreferences#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.backreferences/vb/backreference5.vb#5)]  
  
## 참고 항목  
 [정규식 언어 \- 빠른 참조](../../../docs/standard/base-types/regular-expression-language-quick-reference.md)