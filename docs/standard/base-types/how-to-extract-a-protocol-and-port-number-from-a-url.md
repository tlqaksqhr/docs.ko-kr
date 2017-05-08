---
title: "방법: URL에서 프로토콜 및 포트 번호 추출 | Microsoft Docs"
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
  - ".NET Framework 정규식, 예제"
  - "정규식으로 텍스트 구문 분석, 예제"
  - "정규식과 패턴 일치, 예제"
  - "정규식[.NET Framework], 예제"
  - "정규식, 예제"
  - "정규식으로 검색, 예제"
ms.assetid: ab7f62b3-6d2c-4efb-8ac6-28600df5fd5c
caps.latest.revision: 15
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 15
---
# 방법: URL에서 프로토콜 및 포트 번호 추출
다음 예제에서는 URL에서 프로토콜과 포트 번호를 추출합니다.  
  
## 예제  
 이 예제에서는 <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=fullName> 메서드를 사용하여 프로토콜을 반환하고 그 뒤에 콜론과 포트 번호를 차례로 반환합니다.  
  
 [!code-csharp[RegularExpressions.Examples.Protocol#1](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.Protocol/cs/Example.cs#1)]
 [!code-vb[RegularExpressions.Examples.Protocol#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.Protocol/vb/Example.vb#1)]  
  
 정규식 패턴 `^(?<proto>\w+)://[^/]+?(?<port>:\d+)?/`는 다음 표와 같이 해석될 수 있습니다.  
  
|패턴|설명|  
|--------|--------|  
|`^`|문자열의 시작 부분에서 일치 항목 찾기를 시작합니다.|  
|`(?<proto>\w+)`|하나 이상의 단어 문자를 찾습니다.  이 그룹의 이름을 `proto`로 지정합니다.|  
|`://`|두 개의 슬래시 기호가 뒤에 오는 콜론을 찾습니다.|  
|`[^/]+?`|슬래시 기호 이외의 모든 문자를 가능한 한 적은 개수로 1개 이상 찾습니다.|  
|`(?<port>:\d+)?`|하나 이상의 10진수 문자가 뒤에 오는 콜론을 0개 또는 1개 찾습니다.  이 그룹의 이름을 `port`로 지정합니다.|  
|`/`|슬래시 기호를 찾습니다.|  
  
 <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=fullName> 메서드는 정규식 패턴에서 캡처된 두 개의 명명된 그룹 값을 연결하는 `${proto}${port}` 대체 시퀀스를 확장합니다.  이는 <xref:System.Text.RegularExpressions.Match.Groups%2A?displayProperty=fullName> 속성에서 반환한 컬렉션 개체에서 검색된 문자열을 명시적으로 연결하기 위한 편리한 대체 방법입니다.  
  
 이 예제에서는 <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=fullName> 메서드를 두 가지 대체 패턴인 `${proto}` 및 `${port}`와 함께 사용하여 캡처된 그룹을 출력 문자열에 포함합니다.  다음 코드에서와 같이 일치 항목의 <xref:System.Text.RegularExpressions.GroupCollection> 개체에서 캡처된 그룹을 검색할 수도 있습니다.  
  
 [!code-csharp[RegularExpressions.Examples.Protocol#2](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.Protocol/cs/example2.cs#2)]
 [!code-vb[RegularExpressions.Examples.Protocol#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.Protocol/vb/example2.vb#2)]  
  
## 참고 항목  
 [.NET Framework 정규식](../../../docs/standard/base-types/regular-expressions.md)