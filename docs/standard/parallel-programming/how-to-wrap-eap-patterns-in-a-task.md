---
title: "How to: Wrap EAP Patterns in a Task | Microsoft Docs"
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
  - "tasks, how to wrap EAP patterns"
ms.assetid: f11ed467-af2f-4504-8a2e-299a6c36d44e
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# How to: Wrap EAP Patterns in a Task
다음 예제에서는 <xref:System.Threading.Tasks.TaskCompletionSource%601>를 사용하여 EAP\(Event\-Based Asynchronous Pattern\) 작업의 임의 시퀀스를 하나의 작업으로 노출하는 방법을 보여 줍니다.  또한 <xref:System.Threading.CancellationToken>을 사용하여 <xref:System.Net.WebClient> 개체에 대해 기본 제공 취소 메서드를 호출하는 방법도 보여 줍니다.  
  
## 예제  
 [!code-csharp[FromAsync#08](../../../samples/snippets/csharp/VS_Snippets_Misc/fromasync/cs/fromasync.cs#08)]
 [!code-vb[FromAsync#08](../../../samples/snippets/visualbasic/VS_Snippets_Misc/fromasync/vb/module1.vb#08)]  
  
## 참고 항목  
 [TPL and Traditional .NET Framework Asynchronous Programming](../../../docs/standard/parallel-programming/tpl-and-traditional-async-programming.md)