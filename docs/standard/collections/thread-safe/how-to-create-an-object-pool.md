---
title: "방법: ConcurrentBag을 사용하여 개체 풀 만들기 | Microsoft Docs"
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
  - "개체 풀, .NET Framework"
ms.assetid: 0480e7ff-b6f9-480e-a889-2ed4264d8372
caps.latest.revision: 5
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 5
---
# 방법: ConcurrentBag을 사용하여 개체 풀 만들기
이 예제에서는 CurrentBag을 사용하여 개체 풀을 구현하는 방법을 보여 줍니다.  개체 풀은 여러 클래스 인스턴스가 필요하고 클래스가 만들거나 삭제하는 데 비용이 많이 드는 경우 응용 프로그램 성능을 향상시킬 수 있습니다.  클라이언트 프로그램이 새 개체를 요청하면 개체 풀이 먼저 이미 만들어져 풀에 반환된 개체를 제공하려고 시도합니다.  사용할 수 있는 개체가 없는 경우에만 새 개체가 만들어집니다.  
  
 <xref:System.Collections.Concurrent.ConcurrentBag%601>은 특히 동일 스레드가 항목 추가 및 제거를 모두 수행 중일 때 삽입 및 제거 속도가 빠르기 때문에 개체를 저장하는 데 사용됩니다.  이 예제는 <xref:System.Collections.Concurrent.ConcurrentQueue%601> 및 <xref:System.Collections.Concurrent.ConcurrentStack%601>과 같이 모음 데이터 구조가 구현하는 <xref:System.Collections.Concurrent.IProducerConsumerCollection%601>을 기반으로 추가로 확장할 수 있습니다.  
  
## 예제  
 [!code-csharp[CDS#04](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds/cs/objectpool.cs#04)]
 [!code-vb[CDS#04](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds/vb/objectpool04.vb#04)]  
  
## 참고 항목  
 [스레드로부터 안전한 컬렉션](../../../../docs/standard/collections/thread-safe/index.md)