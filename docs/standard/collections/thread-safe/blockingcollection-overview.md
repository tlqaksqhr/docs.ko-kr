---
title: "BlockingCollection 개요 | Microsoft Docs"
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
  - "BlockingCollection, 개요"
ms.assetid: 987ea3d7-0ad5-4238-8b64-331ce4eb3f0b
caps.latest.revision: 12
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 12
---
# BlockingCollection 개요
<xref:System.Collections.Concurrent.BlockingCollection%601>은 스레드로부터 안전한 컬렉션 클래스이며 다음 기능을 제공합니다.  
  
-   공급자\/소비자 패턴 구현  
  
-   여러 스레드에서 동시에 항목 추가 및 가져오기  
  
-   선택적 최대 용량  
  
-   컬렉션이 비어 있거나 가득 찬 경우 차단되는 삽입 및 제거 작업  
  
-   차단되지 않거나 지정된 시간 동안 차단되는 삽입 및 제거 "시도" 작업  
  
-   <xref:System.Collections.Concurrent.IProducerConsumerCollection%601>을 구현하는 모든 컬렉션 형식의 캡슐화  
  
-   취소 토큰으로 취소  
  
-   `foreach`\(Visual Basic의 경우 `For Each`\)를 사용한 두 가지 유형의 열거  
  
    1.  읽기 전용 열거  
  
    2.  열거된 항목을 제거하는 열거  
  
## 한계 지정 및 차단 지원  
 <xref:System.Collections.Concurrent.BlockingCollection%601>은 한계 지정 및 차단을 지원합니다.  한계 지정이란 컬렉션의 최대 용량을 설정하는 것을 의미합니다.  한계 지정을 통해 메모리에서 컬렉션의 최대 크기를 제어할 수 있고 공급자 스레드가 소비자 스레드와 보조를 맞춰 실행되도록 할 수 있기 때문에 특정 시나리오에서 한계 지정은 중요한 의미를 가집니다.  
  
 다중 스레드 또는 작업은 동시에 항목을 컬렉션에 추가할 수 있습니다. 지정된 최대 용량에 컬렉션이 도달한 경우 항목 하나가 제거될 때까지 공급자 스레드는 차단됩니다.  여러 소비자는 동시에 항목을 제거할 수 있습니다. 컬렉션이 비어 있는 경우 공급자가 항목 하나를 추가할 때까지 소비자 스레드는 차단됩니다.  공급자 스레드는 <xref:System.Collections.Concurrent.BlockingCollection%601.CompleteAdding%2A>을 호출하여 더 이상 추가할 항목이 없음을 나타낼 수 있습니다.  소비자 스레드는 컬렉션이 비어 있는 되는 시점 및 더 이상 항목이 추가되지 않는 시점을 파악하기 위해 <xref:System.Collections.Concurrent.BlockingCollection%601.IsCompleted%2A> 속성을 모니터링합니다.  다음 예제에서는 한계 용량이 100인 간단한 BlockingCollection을 보여 줍니다.  공급자 작업에서는 일부 외부 조건이 true이면 컬렉션에 항목을 추가한 다음 <xref:System.Collections.Concurrent.BlockingCollection%601.CompleteAdding%2A>을 호출합니다.  소비자 작업에서는 <xref:System.Collections.Concurrent.BlockingCollection%601.IsCompleted%2A> 속성이 true일 때까지 항목을 가져옵니다.  
  
 [!code-csharp[CDS_BlockingCollection#04](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/blockingcollection.cs#04)]
 [!code-vb[CDS_BlockingCollection#04](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_blockingcollection/vb/introsnippetsbc.vb#04)]  
  
 전체 예제는 [방법: BlockingCollection에서 개별적으로 항목 추가 및 가져오기](../../../../docs/standard/collections/thread-safe/how-to-add-and-take-items.md)를 참조하십시오.  
  
## 시간이 지정된 차단 작업  
 한계 있는 컬렉션에 대한 시간이 지정된 <xref:System.Collections.Concurrent.BlockingCollection%601.TryAdd%2A> 및 <xref:System.Collections.Concurrent.BlockingCollection%601.TryTake%2A> 차단 작업에서 메서드는 항목을 추가하거나 가져오려고 합니다.  사용 가능한 항목이 있으면 이 항목은 참조로 전달된 변수에 저장되고 메서드는 true를 반환합니다.  지정된 제한 시간이 경과했지만 검색된 항목이 없으면 메서드에서 false를 반환합니다.  그런 다음 스레드는 컬렉션에 대한 액세스를 다시 시도하기 전에 유용한 다른 작업을 수행할 수 있습니다.  시간이 지정된 차단 액세스에 대한 예제는 [방법: BlockingCollection에서 개별적으로 항목 추가 및 가져오기](../../../../docs/standard/collections/thread-safe/how-to-add-and-take-items.md)의 두 번째 예제를 참조하십시오.  
  
## 추가 및 가져오기 작업 취소  
 추가 및 가져오기 작업은 일반적으로 루프에서 수행됩니다.  <xref:System.Collections.Concurrent.BlockingCollection%601.TryAdd%2A> 또는 <xref:System.Collections.Concurrent.BlockingCollection%601.TryTake%2A> 메서드에 <xref:System.Threading.CancellationToken>을 전달한 다음, 각 반복에서 이 토큰의 <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> 속성 값을 확인하여 루프를 취소할 수 있습니다.  이 속성 값이 true인 경우 리소스를 정리하고 루프를 종료하여 취소 요청에 응답하는 것은 사용자의 몫입니다.  다음 예제에서는 취소 토큰을 사용하는 <xref:System.Collections.Concurrent.BlockingCollection%601.TryAdd%2A>의 오버로드 및 이 오버로드를 사용하는 코드를 보여 줍니다.  
  
 [!code-csharp[CDS_BlockingCollection#05](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/blockingcollection.cs#05)]
 [!code-vb[CDS_BlockingCollection#05](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_blockingcollection/vb/introsnippetsbc.vb#05)]  
  
 취소 지원을 추가하는 방법에 대한 예제는 [방법: BlockingCollection에서 개별적으로 항목 추가 및 가져오기](../../../../docs/standard/collections/thread-safe/how-to-add-and-take-items.md)의 두 번째 예제를 참조하십시오.  
  
## 컬렉션 서식 지정  
 <xref:System.Collections.Concurrent.BlockingCollection%601>을 만들 경우 한계 용량뿐 아니라 사용할 컬렉션의 형식도 지정할 수 있습니다.  예를 들어, FIFO\(선입 선출\) 동작에 대해 <xref:System.Collections.Concurrent.ConcurrentQueue%601>을 지정하거나 LIFO\(후입 선출\) 동작에 대해 <xref:System.Collections.Concurrent.ConcurrentStack%601>을 지정할 수 있습니다.  <xref:System.Collections.Concurrent.IProducerConsumerCollection%601> 인터페이스를 구현하는 모든 컬렉션 클래스를 사용할 수 있습니다.  <xref:System.Collections.Concurrent.BlockingCollection%601>의 기본 컬렉션 형식은 <xref:System.Collections.Concurrent.ConcurrentQueue%601> 입니다.  다음 코드 예제에서는 용량이 1000인 <xref:System.Collections.Concurrent.BlockingCollection%601> 문자열을 만들고 <xref:System.Collections.Concurrent.ConcurrentBag%601> 을 만드는 방법을 보여 줍니다.  
  
```vb  
Dim bc = New BlockingCollection(Of String)(New ConcurrentBag(Of String()), 1000)  
```  
  
```csharp  
BlockingCollection<string> bc = new BlockingCollection<string>(new ConcurrentBag<string>(), 1000 );  
```  
  
 자세한 내용은 [방법: 컬렉션에 경계 및 차단 기능 추가](../../../../docs/standard/collections/thread-safe/how-to-add-bounding-and-blocking.md)을 참조하십시오.  
  
## IEnumerable 지원  
 <xref:System.Collections.Concurrent.BlockingCollection%601>에서는 컬렉션이 완료될 때까지, 즉 컬렉션이 비어 있고 더 이상 항목이 추가되지 않을 때까지 항목을 제거하는 데 `foreach`\([!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)]의 경우 `For Each`\)를 소비자가 사용할 수 있게 하는 <xref:System.Collections.Concurrent.BlockingCollection%601.GetConsumingEnumerable%2A> 메서드를 제공합니다.  자세한 내용은 [방법: ForEach를 사용하여 BlockingCollection의 항목 제거](../../../../docs/standard/collections/thread-safe/how-to-use-foreach-to-remove.md)을 참조하십시오.  
  
## 여러 BlockingCollection을 하나로 사용  
 소비자가 여러 컬렉션에서 동시에 항목을 가져와야 하는 시나리오의 경우 <xref:System.Collections.Concurrent.BlockingCollection%601> 배열을 만들고, 배열 내의 컬렉션에 항목을 추가하거나 컬렉션에서 항목을 가져올 <xref:System.Collections.Concurrent.BlockingCollection%601.TakeFromAny%2A> 및 <xref:System.Collections.Concurrent.BlockingCollection%601.AddToAny%2A> 같은 정적 메서드를 사용할 수 있습니다.  특정 컬렉션이 차단되는 즉시 메서드에서는 작업을 수행할 수 있는 컬렉션을 찾을 때까지 다른 컬렉션에 대한 액세스를 시도합니다.  자세한 내용은 [방법: 파이프라인에서 차단 수집 배열 사용](../../../../docs/standard/collections/thread-safe/how-to-use-arrays-of-blockingcollections.md)을 참조하십시오.  
  
## 참고 항목  
 <xref:System.Collections.Concurrent?displayProperty=fullName>   
 [컬렉션 및 데이터 구조](../../../../docs/standard/collections/index.md)   
 [스레드로부터 안전한 컬렉션](../../../../docs/standard/collections/thread-safe/index.md)