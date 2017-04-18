---
title: "정규식 예제: HREF 스캐닝 | Microsoft Docs"
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
  - "정규식으로 검색, 예제"
  - "정규식으로 텍스트 구문 분석, 예제"
  - "정규식, 예제"
  - ".NET Framework 정규식, 예제"
  - "정규식[.NET Framework], 예제"
  - "정규식과 패턴 일치, 예제"
ms.assetid: fae2c15b-7adf-4b15-b118-58eb3906994f
caps.latest.revision: 24
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 24
---
# 정규식 예제: HREF 스캐닝
다음 예제는 입력 문자열을 검색하고 모든 href\="..." 값과 문자열에서의 해당 위치를 보여줍니다.  
  
## Regex 개체  
 사용자 코드에서 `DumpHRefs` 메서드를 여러 번 호출할 수 있으므로 여기에는 `static`\(Visual Basic의 경우 `Shared`\) <xref:System.Text.RegularExpressions.Regex.Match%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.RegexOptions%29?displayProperty=fullName> 메서드가 사용됩니다.  정규식 엔진은 이를 통해 정규식을 캐시하여 메서드가 호출될 때마다 새 <xref:System.Text.RegularExpressions.Regex> 개체를 인스턴스화하는 오버헤드를 피할 수 있습니다.  그런 다음 <xref:System.Text.RegularExpressions.Match> 개체를 사용하여 문자열의 모든 일치 항목을 반복할 수 있습니다.  
  
 [!code-csharp[RegularExpressions.Examples.HREF#1](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.HREF/cs/example.cs#1)]
 [!code-vb[RegularExpressions.Examples.HREF#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.HREF/vb/example.vb#1)]  
  
 다음 예제에서는 `DumpHRefs` 메서드 호출을 보여 줍니다.  
  
 [!code-csharp[RegularExpressions.Examples.HREF#2](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.HREF/cs/example.cs#2)]
 [!code-vb[RegularExpressions.Examples.HREF#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.HREF/vb/example.vb#2)]  
  
 정규식 패턴 `href\s*=\s*(?:["'](?<1>[^"']*)["']|(?<1>\S+))`는 다음 표에서와 같이 해석됩니다.  
  
|패턴|설명|  
|--------|--------|  
|`href`|리터럴 문자열 "href"의 일치 여부를 확인합니다.  일치 여부를 확인할 때 대\/소문자는 구분되지 않습니다.|  
|`\s*`|0개 이상의 공백 문자가 일치하는지 확인합니다.|  
|`=`|등호의 일치 여부를 확인합니다.|  
|`\s*`|0개 이상의 공백 문자가 일치하는지 확인합니다.|  
|`(?:["'](?<1>[^"']*)"&#124;(?<1>\S+))`|캡처된 그룹에 결과를 할당하지 않고 다음 중 하나의 일치 여부를 확인합니다.<br /><br /> -   따옴표 또는 아포스트로피 뒤에 따옴표 또는 아포스트로피 이외의 다른 문자가 0개 이상 나오고 그 뒤에 다시 따옴표 또는 아포스트로피가 나오는 항목.  `1`이라는 그룹이 이 패턴에 포함됩니다.<br />-   공백이 아닌 0개 이상의 문자.  `1`이라는 그룹이 이 패턴에 포함됩니다.|  
|`(?<1>[^"']*)`|`1`이라는 캡처 그룹에 따옴표 또는 아포스트로피 이외의 다른 문자 항목을 0개 이상 할당합니다.|  
|`"(?<1>\S+)`|`1`이라는 캡처 그룹에 공백이 아닌 0개 이상의 문자를 할당합니다.|  
  
## Match 결과 클래스  
 검색 결과는 검색에서 추출된 모든 부분 문자열에 대한 액세스를 제공하는 <xref:System.Text.RegularExpressions.Match> 클래스에 저장됩니다.  또한 이 클래스는 마지막 검색이 끝난 지점에서 다른 검색을 시작하기 위해 <xref:System.Text.RegularExpressions.Match.NextMatch%2A?displayProperty=fullName> 메서드를 호출할 수 있도록 검색 대상 문자열과 사용되는 정규식을 기억합니다.  
  
## 명시적으로 명명된 캡처  
 기존의 정규식에서 캡처링 괄호는 자동으로 번호가 매겨지는데  여기에서 두 가지 문제가 발생합니다.  첫째, 괄호를 삽입하거나 제거하여 정규식을 수정한 경우, 이전 번호를 참조하는 모든 코드를 새로 지정된 번호에 맞춰 다시 작성해야 합니다.  둘째, 일치하는 항목을 찾기 위해 서로 다른 두 가지 식을 사용하는 경우에는 괄호를 두 개 이상 사용해야 하는데, 이런 경우 어느 식에서 실제로 값을 반환했는지 판단하기 어렵습니다.  
  
 이러한 문제를 해결하기 위해 <xref:System.Text.RegularExpressions.Regex> 클래스에서는 일치 항목을 지정된 슬롯에 캡처링할 수 있도록 `(?<name>…)` 구문을 지원합니다. 문자열 또는 정수를 사용하여 슬롯에 이름을 지정할 수 있는데, 정수를 사용했을 때 속도가 더 빠릅니다.  이 구문을 사용하면 같은 문자열에서 찾은 일치 항목을 동일한 위치에 넣을 수 있습니다.  충돌이 발생하는 경우에는 슬롯에 있는 마지막 일치 항목이 성공적으로 검색된 항목입니다. 그러나 한 슬롯에 대한 여러 일치 항목의 전체 목록이 제공됩니다.  자세한 내용은 <xref:System.Text.RegularExpressions.Group.Captures%2A?displayProperty=fullName> 컬렉션을 참조하십시오.  
  
## 참고 항목  
 [.NET Framework 정규식](../../../docs/standard/base-types/regular-expressions.md)