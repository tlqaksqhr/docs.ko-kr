---
title: ".NET Framework에서 문자열 채우기 | Microsoft Docs"
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
  - "문자열 채우기"
  - "PadLeft 메서드"
  - "PadRight 메서드"
  - "문자열[.NET Framework], 안쪽 여백"
  - "공백"
ms.assetid: 84a9f142-3244-4c90-ba02-21af9bbaff71
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# .NET Framework에서 문자열 채우기
다음 <xref:System.String> 메서드 중 하나를 사용하면 지정한 전체 길이에 맞도록 원래 문자열에 선행 또는 후행 문자를 채운 새 문자열을 만들 수 있습니다.  채움 문자는 공백이거나 지정한 문자일 수 있으며, 따라서 오른쪽이나 왼쪽에 맞춰 표시됩니다.  
  
|메서드 이름|기능|  
|------------|--------|  
|<xref:System.String.PadLeft%2A?displayProperty=fullName>|지정한 전체 길이에 맞도록 선행 문자로 문자열을 채웁니다.|  
|<xref:System.String.PadRight%2A?displayProperty=fullName>|지정한 전체 길이에 맞도록 후행 문자로 문자열을 채웁니다.|  
  
## PadLeft  
 <xref:System.String.PadLeft%2A?displayProperty=fullName> 메서드는 지정한 전체 길이에 맞도록 필요한 만큼의 선행 채움 문자를 원래 문자열에 연결하여 새 문자열을 만듭니다.  <xref:System.String.PadLeft%28System.Int32%29?displayProperty=fullName> 메서드는 채움 문자로 공백을 사용하며, <xref:System.String.PadLeft%28System.Int32%2CSystem.Char%29?displayProperty=fullName> 메서드를 사용할 경우에는 원하는 채움 문자를 지정할 수 있습니다.  
  
 다음 코드 예제에서는 <xref:System.String.PadLeft%2A> 메서드를 사용하여 20자 길이의 새 문자열을 만듭니다.  이 예제에서는 콘솔에 "`--------Hello World!`"를 표시합니다.  
  
 [!code-cpp[Conceptual.String.BasicOps#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/padding.cpp#3)]
 [!code-csharp[Conceptual.String.BasicOps#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/padding.cs#3)]
 [!code-vb[Conceptual.String.BasicOps#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/padding.vb#3)]  
  
## PadRight  
 <xref:System.String.PadRight%2A?displayProperty=fullName> 메서드는 지정한 전체 길이에 맞도록 필요한 만큼의 후행 채움 문자를 원래 문자열에 연결하여 새 문자열을 만듭니다.  <xref:System.String.PadRight%28System.Int32%29?displayProperty=fullName> 메서드는 채움 문자로 공백을 사용하며, <xref:System.String.PadRight%28System.Int32%2CSystem.Char%29?displayProperty=fullName> 메서드를 사용할 경우에는 원하는 채움 문자를 지정할 수 있습니다.  
  
 다음 코드 예제에서는 <xref:System.String.PadRight%2A> 메서드를 사용하여 20자 길이의 새 문자열을 만듭니다.  이 예제에서는 콘솔에 "`Hello World!--------`"를 표시합니다.  
  
 [!code-cpp[Conceptual.String.BasicOps#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/padding.cpp#4)]
 [!code-csharp[Conceptual.String.BasicOps#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/padding.cs#4)]
 [!code-vb[Conceptual.String.BasicOps#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/padding.vb#4)]  
  
## 참고 항목  
 [기본적인 문자열 작업](../../../docs/standard/base-types/basic-string-operations.md)