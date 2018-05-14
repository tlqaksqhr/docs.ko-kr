---
title: '방법: URL에서 프로토콜 및 포트 번호 추출'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- searching with regular expressions, examples
- parsing text with regular expressions, examples
- regular expressions, examples
- .NET Framework regular expressions, examples
- regular expressions [.NET Framework], examples
- pattern-matching with regular expressions, examples
ms.assetid: ab7f62b3-6d2c-4efb-8ac6-28600df5fd5c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ffb31030a2e29458165ae6615a51685ed163fbac
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="how-to-extract-a-protocol-and-port-number-from-a-url"></a>방법: URL에서 프로토콜 및 포트 번호 추출
다음 예제에서는 URL에서 프로토콜 및 포트 번호를 추출합니다.  
  
## <a name="example"></a>예  
 이 예제에서는 <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType> 메서드를 사용하여 프로토콜, 콜론, 포트 번호 순서로 구성된 값을 반환합니다.  
  
 [!code-csharp[RegularExpressions.Examples.Protocol#1](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.Protocol/cs/Example.cs#1)]
 [!code-vb[RegularExpressions.Examples.Protocol#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.Protocol/vb/Example.vb#1)]  
  
 정규식 패턴 `^(?<proto>\w+)://[^/]+?(?<port>:\d+)?/`는 다음 표와 같이 해석할 수 있습니다.  
  
|무늬|설명|  
|-------------|-----------------|  
|`^`|문자열의 시작 부분에서 일치 항목 찾기를 시작합니다.|  
|`(?<proto>\w+)`|하나 이상의 단어 문자를 찾습니다. 이 그룹의 이름을 `proto`로 지정합니다.|  
|`://`|콜론과 두 개의 슬래시 기호를 찾습니다.|  
|`[^/]+?`|슬래시 기호 이외의 문자를 한 번 이상(가능한 적게) 찾습니다.|  
|`(?<port>:\d+)?`|하나 이상의 숫자 문자 앞에 나오는 콜론을 0번 또는 한 번 찾습니다. 이 그룹의 이름을 `port`로 지정합니다.|  
|`/`|슬래시 기호를 찾습니다.|  
  
 <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType> 메서드는 정규식 패턴에 캡처된 두 개의 명명된 그룹 값을 연결하는 `${proto}${port}` 대체 시퀀스를 확장합니다. 이 메서드는 <xref:System.Text.RegularExpressions.Match.Groups%2A?displayProperty=nameWithType> 속성으로 반환된 컬렉션 개체에서 검색된 문자열을 명시적으로 연결하는 편리한 대체 방법입니다.  
  
 이 예제에서는 <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType> 메서드를 두 개의 대체 즉, `${proto}` 및 `${port}`와 함께 사용하여 캡처된 그룹을 출력 문자열에 포함합니다. 대신, 다음 코드와 같이 일치 항목의 <xref:System.Text.RegularExpressions.GroupCollection> 개체에서 캡처된 그룹을 검색할 수 있습니다.  
  
 [!code-csharp[RegularExpressions.Examples.Protocol#2](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.Protocol/cs/example2.cs#2)]
 [!code-vb[RegularExpressions.Examples.Protocol#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.Protocol/vb/example2.vb#2)]  
  
## <a name="see-also"></a>참고 항목  
 [.NET 정규식](../../../docs/standard/base-types/regular-expressions.md)
