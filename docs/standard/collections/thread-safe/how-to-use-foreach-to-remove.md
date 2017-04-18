---
title: "방법: ForEach를 사용하여 BlockingCollection의 항목 제거 | Microsoft Docs"
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
  - "스레드로부터 안전한 컬렉션, 차단 컬렉션 열거 방법"
ms.assetid: 2096103c-22f7-420d-b631-f102bc33a6dd
caps.latest.revision: 13
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 13
---
# 방법: ForEach를 사용하여 BlockingCollection의 항목 제거
<xref:System.Collections.Concurrent.BlockingCollection%601.Take%2A> 및 <xref:System.Collections.Concurrent.BlockingCollection%601.TryTake%2A> 메서드를 사용하여 <xref:System.Collections.Concurrent.BlockingCollection%601>에서 항목을 가져오는 것 외에도 [foreach](../Topic/foreach,%20in%20\(C%23%20Reference\).md)\(Visual Basic의 경우 [For Each](../Topic/For%20Each...Next%20Statement%20\(Visual%20Basic\).md)\)를 사용하여 추가 작업이 완료되고 컬렉션이 빌 때까지 항목을 제거할 수 있습니다.  이를 *열거형 변경* 또는 *열거형 소비*라고 합니다. 일반적인 `foreach`\(`For Each`\) 루프와 달리 이 열거자는 항목을 제거하여 소스 컬렉션을 수정하기 때문입니다.  
  
## 예제  
 다음 예제에서는 `foreach`\(`For Each`\) 루프를 사용하여 <xref:System.Collections.Concurrent.BlockingCollection%601>의 항목을 모두 제거하는 방법을 보여 줍니다.  
  
 [!code-csharp[CDS_BlockingCollection#03](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/example03.cs#03)]
 [!code-vb[CDS_BlockingCollection#03](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_blockingcollection/vb/enumeratebc.vb#03)]  
  
 이 예제에서는 `foreach` 루프를 소비 스레드의 <xref:System.Collections.Concurrent.BlockingCollection%601.GetConsumingEnumerable%2A?displayProperty=fullName> 메서드와 함께 사용하여 컬렉션을 열거할 때 해당 컬렉션에서 각 항목을 제거합니다.  <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=fullName>은 컬렉션에 있는 항목의 최대 수를 항상 제한합니다.  이와 같이 컬렉션을 열거하는 경우 사용 가능한 항목이 없거나 컬렉션이 비어 있으면 소비자 스레드가 차단됩니다.  이 예제에서는 생산자 스레드가 항목이 소비되는 것보다 더 빠르게 항목을 추가하기 때문에 차단이 발생하지 않습니다.  
  
 생산자 스레드를 통해 항목이 추가된 순서와 항목의 열거 순서는 같지 않을 수 있습니다.  
  
 컬렉션을 수정하지 않고 열거하려면 <xref:System.Collections.Concurrent.BlockingCollection%601.GetConsumingEnumerable%2A> 메서드 없이 `foreach`\(`For Each`\)만 사용합니다.  그러나 이와 같이 열거한 결과는 특정 시점에서의 컬렉션을 나타내는 스냅숏에 불과하다는 사실을 이해하고 있어야 합니다.  루프를 실행하는 동안 다른 스레드를 통해 항목이 계속하여 추가 또는 제거되고 있다면 루프에 표시되는 상태가 컬렉션의 실제 상태와 다를 수 있습니다.  
  
## 참고 항목  
 <xref:System.Collections.Concurrent?displayProperty=fullName>   
 [Parallel Programming](../../../../docs/standard/parallel-programming/index.md)