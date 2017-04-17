---
title: "방법: 문자열에서 유효하지 않은 문자 제거 | Microsoft Docs"
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
  - "정규식, 예제"
  - "입력 정리"
  - "사용자 입력, 예제"
  - ".NET Framework 정규식, 예제"
  - "정규식[.NET Framework], 예제"
  - "Regex.Replace 메서드"
  - "잘못된 문자 제거"
  - "Replace 메서드"
  - "사용자 입력 유효성 검사"
ms.assetid: b4319c8a-9032-4129-a9d5-6f6fc28e7f32
caps.latest.revision: 15
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 15
---
# 방법: 문자열에서 유효하지 않은 문자 제거
다음 예제에서는 정적 <xref:System.Text.RegularExpressions.Regex.Replace%2A?displayProperty=fullName> 메서드를 사용하여 문자열에서 유효하지 않은 문자를 제거합니다.  
  
## 예제  
 이 예제에 정의된 `CleanInput` 메서드를 사용하면 사용자 입력을 받아들이는 텍스트 필드에 입력된 해로울 수 있는 문자를 제거할 수 있습니다.  이 경우 `CleanInput`은 마침표\(.\), at\(@\) 기호 및 하이픈\(\-\)을 제외하고 영문자가 아닌 모든 문자를 제거한 후 나머지 문자열을 반환합니다.  하지만 입력 문자열에 포함되어서는 안되는 모든 문자를 제거할 수 있도록 정규식 패턴을 수정할 수 있습니다.  
  
 [!code-csharp[RegularExpressions.Examples.StripChars#1](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.StripChars/cs/Example.cs#1)]
 [!code-vb[RegularExpressions.Examples.StripChars#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.StripChars/vb/Example.vb#1)]  
  
 `[^\w\.@-]` 정규식 패턴은 단어 문자가 아닌 모든 문자, 마침표, @ 기호 또는 하이픈을 찾습니다.  단어 문자란 모든 문자, 10진수 또는 밑줄 같은 연결 문장 부호를 가리킵니다.  이 패턴과 일치하는 모든 문자는 바꾸기 패턴에서 정의한 문자열인 <xref:System.String.Empty?displayProperty=fullName>로 바뀝니다.  사용자 입력에 추가 문자를 허용하려면 이러한 문자를 정규식 패턴의 문자 클래스에 추가합니다.  예를 들어 정규식 패턴 `[^\w\.@-\\%]`를 사용하면 백분율 기호와 역슬래시를 입력 문자열에 사용할 수도 있습니다.  
  
## 참고 항목  
 [.NET Framework 정규식](../../../docs/standard/base-types/regular-expressions.md)