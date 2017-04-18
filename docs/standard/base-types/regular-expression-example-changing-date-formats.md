---
title: "정규식 예제: 날짜 형식 변경 | Microsoft Docs"
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
ms.assetid: 5fcc75a5-09d7-45ae-a4c0-9ad6085ac83d
caps.latest.revision: 19
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 19
---
# 정규식 예제: 날짜 형식 변경
다음 코드 예제에서는 <xref:System.Text.RegularExpressions.Regex.Replace%2A?displayProperty=fullName> 메서드를 사용하여 *mm*\/*dd*\/*yy* 형식의 날짜를 *dd*\-*mm*\-*yy* 형식의 날짜로 바꿉니다.  
  
## 예제  
 [!code-csharp[RegularExpressions.Examples.ChangeDateFormats#1](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.ChangeDateFormats/cs/Example_ChangeDateFormats1.cs#1)]
 [!code-vb[RegularExpressions.Examples.ChangeDateFormats#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.ChangeDateFormats/vb/Example_ChangeDateFormats1.vb#1)]  
  
 다음 코드에서는 응용 프로그램에서 `MDYToDMY` 메서드를 호출하는 방법을 보여 줍니다.  
  
 [!code-csharp[RegularExpressions.Examples.ChangeDateFormats#2](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.ChangeDateFormats/cs/Example_ChangeDateFormats1.cs#2)]
 [!code-vb[RegularExpressions.Examples.ChangeDateFormats#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.ChangeDateFormats/vb/Example_ChangeDateFormats1.vb#2)]  
  
## 설명  
 정규식 패턴 `\b(?<month>\d{1,2})/(?<day>\d{1,2})/(?<year>\d{2,4})\b`는 다음 표에서와 같이 해석됩니다.  
  
|패턴|설명|  
|--------|--------|  
|`\b`|단어 경계에서 일치 항목 찾기를 시작합니다.|  
|`(?<month>\d{1,2})`|하나 또는 두 개의 10진수를 찾습니다.  이 그룹은 `month` 캡처된 그룹입니다.|  
|`/`|슬래시 표시를 찾습니다.|  
|`(?<day>\d{1,2})`|하나 또는 두 개의 10진수를 찾습니다.  이 그룹은 `day` 캡처된 그룹입니다.|  
|`/`|슬래시 표시를 찾습니다.|  
|`(?<year>\d{2,4})`|두 개에서 네 개의 10진수를 찾습니다.  이 그룹은 `year` 캡처된 그룹입니다.|  
|`\b`|단어 경계에서 일치 항목 찾기를 끝냅니다.|  
  
 패턴 `${day}-${month}-${year}`는 다음 표에서와 같이 바꾸기 문자열을 정의합니다.  
  
|패턴|설명|  
|--------|--------|  
|`$(day)`|`day` 캡처링 그룹에서 캡처한 문자열을 추가합니다.|  
|`-`|하이픈을 추가합니다.|  
|`$(month)`|`month` 캡처링 그룹에서 캡처한 문자열을 추가합니다.|  
|`-`|하이픈을 추가합니다.|  
|`$(year)`|`year` 캡처링 그룹에서 캡처한 문자열을 추가합니다.|  
  
## 참고 항목  
 [.NET Framework 정규식](../../../docs/standard/base-types/regular-expressions.md)