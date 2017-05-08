---
title: "보안 및 공용 읽기 전용 배열 필드 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "보안[.NET Framework], 읽기 전용 공용 배열 필드"
ms.assetid: 3df28dee-2a9f-40ff-9852-bfdbe59c27f3
caps.latest.revision: 7
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 7
---
# 보안 및 공용 읽기 전용 배열 필드
읽기 전용 공용 배열 필드는 수정할 수 없으므로, 관리되는 라이브러리의 읽기 전용 공용 배열 필드를 사용하여 응용 프로그램의 경계 동작이나 보안을 정의해서는 안 됩니다.  
  
## 설명  
 .NET Framework 클래스 중에는 플랫폼별 경계 매개 변수가 들어 있는 읽기 전용 공용 필드가 포함된 경우도 있습니다.  예를 들어, <xref:System.IO.Path.InvalidPathChars> 필드는 파일 경로 문자열에 사용할 수 없는 문자를 설명하는 배열입니다.  .NET Framework 전체적으로 이와 비슷한 필드가 많이 있습니다.  
  
 <xref:System.IO.Path.InvalidPathChars>와 같은 읽기 전용 공용 필드의 값은 사용자의 코드나 코드의 응용 프로그램 도메인을 공유하는 코드를 사용하여 수정할 수 있습니다.  이와 같은 읽기 전용 공용 배열 필드를 사용하여 응용 프로그램의 경계 동작을 정의해서는 안 됩니다.  그럴 경우 악성 코드가 경계 정의를 변경하고 사용자의 코드를 예기치 않은 방식으로 사용할 수 있습니다.  
  
 .NET Framework의 버전 2.0 이상에서는 공용 배열 필드를 사용하는 대신 새 배열을 반환하는 메서드를 사용해야 합니다.  예를 들어, <xref:System.IO.Path.InvalidPathChars> 필드를 사용하는 대신 <xref:System.IO.Path.GetInvalidPathChars%2A> 메서드를 사용해야 합니다.  
  
 .NET Framework 형식은 공용 필드를 사용하여 경계 형식을 내부적으로 정의하지 않습니다.  대신 .NET Framework에서는 별도의 전용 필드를 사용합니다.  이러한 공용 필드 값을 변경해도 .NET Framework 형식의 동작은 변경되지 않습니다.  
  
## 참고 항목  
 [보안 코딩 지침](../../../docs/standard/security/secure-coding-guidelines.md)