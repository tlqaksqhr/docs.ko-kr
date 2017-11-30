---
title: "방법: URL에서 프로토콜 및 포트 번호 추출"
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
- searching with regular expressions, examples
- parsing text with regular expressions, examples
- regular expressions, examples
- .NET Framework regular expressions, examples
- regular expressions [.NET Framework], examples
- pattern-matching with regular expressions, examples
ms.assetid: ab7f62b3-6d2c-4efb-8ac6-28600df5fd5c
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 10ab05ac8b24c0658be2f27809137c6b0bd4834f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-extract-a-protocol-and-port-number-from-a-url"></a>방법: URL에서 프로토콜 및 포트 번호 추출
다음 예제에서는 URL에서 프로토콜 및 포트 번호를 추출합니다.  
  
## <a name="example"></a>예제  
 이 예제에서는 사용 된 <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType> 포트 번호 뒤에 오는 콜론 뒤의 프로토콜을 반환 하는 메서드.  
  
 [!code-csharp[RegularExpressions.Examples.Protocol#1](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.Protocol/cs/Example.cs#1)]
 [!code-vb[RegularExpressions.Examples.Protocol#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.Protocol/vb/Example.vb#1)]  
  
 정규식 패턴 `^(?<proto>\w+)://[^/]+?(?<port>:\d+)?/`는 다음 표와 같이 해석할 수 있습니다.  
  
|패턴|설명|  
|-------------|-----------------|  
|`^`|문자열의 시작 부분에서 일치 항목 찾기를 시작합니다.|  
|`(?<proto>\w+)`|하나 이상의 단어 문자를 찾습니다. 이 그룹의 이름을 `proto`합니다.|  
|`://`|콜론과 두 개의 슬래시 기호를 찾습니다.|  
|`[^/]+?`|슬래시 기호 이외의 문자를 한 번 이상(가능한 적게) 찾습니다.|  
|`(?<port>:\d+)?`|하나 이상의 숫자 문자 앞에 나오는 콜론을 0번 또는 한 번 찾습니다. 이 그룹의 이름을 `port`합니다.|  
|`/`|슬래시 기호를 찾습니다.|  
  
 <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType> 메서드는 확장은 `${proto}${port}` 정규식 패턴에서 캡처되는 두 개의 명명 된 그룹 값을 연결 하는 대체 시퀀스입니다. 명시적으로 반환 되는 컬렉션 개체에서 검색 문자열을 연결 편리한 방법이 <xref:System.Text.RegularExpressions.Match.Groups%2A?displayProperty=nameWithType> 속성입니다.  
  
 이 예제에서는 사용는 <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType> 메서드 두 개의 대체 `${proto}` 및 `${port}`, 출력 문자열에 캡처된 그룹을 포함 하도록 합니다. 일치 항목의 캡처된 그룹을 검색할 수 <xref:System.Text.RegularExpressions.GroupCollection> 대신 다음 코드 에서처럼 개체입니다.  
  
 [!code-csharp[RegularExpressions.Examples.Protocol#2](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.Protocol/cs/example2.cs#2)]
 [!code-vb[RegularExpressions.Examples.Protocol#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.Protocol/vb/example2.vb#2)]  
  
## <a name="see-also"></a>참고 항목  
 [.NET 정규식](../../../docs/standard/base-types/regular-expressions.md)
