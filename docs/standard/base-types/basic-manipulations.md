---
title: "방법: .NET Framework의 기본 문자열 조작 수행 | Microsoft Docs"
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
  - "문자열[.NET Framework], 예제"
ms.assetid: 121d1eae-251b-44c0-8818-57da04b8215e
caps.latest.revision: 7
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 7
---
# 방법: .NET Framework의 기본 문자열 조작 수행
다음 예제에서는[기본적인 문자열 작업](../../../docs/standard/base-types/basic-string-operations.md)항목에서 설명한 메서드를 통해 실제 응용 프로그램에서 수행하는것과 동일한 방식으로 문자열을 조작하는 클래스를 만듭니다.  `MailToData` 클래스에서는 개인의 이름과 주소를 별개의 속성에 저장하고 `City`, `State` 및 `Zip` 필드를 단일 문자열로 연결하여 사용자에게 표시할 수 있습니다.  이 클래스를 사용하면 사용자가 도시, 주 및 우편 번호 정보를 단일 문자열로 입력할 수도 있습니다. 그러면 응용 프로그램에서 이 문자열을 구문 분석하여 각각의 정보를 적절한 속성에 저장합니다.  
  
 작업이 간편하도록 이 예제에서는 명령줄 인터페이스를 표시하는 콘솔 응용 프로그램을 사용합니다.  
  
## 예제  
 [!code-csharp[Conceptual.String.BasicOps#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/basicops.cs#1)]
 [!code-vb[Conceptual.String.BasicOps#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/basicops.vb#1)]  
  
 위 코드를 실행하면 이름과 주소를 입력하라는 메시지가 표시됩니다.  응용 프로그램에서는 정보를 적절한 속성에 저장하고 도시, 주 및 우편 번호 정보를 단일 문자열로 만들어 사용자에게 다시 표시합니다.  
  
## 참고 항목  
 [기본적인 문자열 작업](../../../docs/standard/base-types/basic-string-operations.md)