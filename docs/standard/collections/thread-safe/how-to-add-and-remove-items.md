---
title: "방법: ConcurrentDictionary에서 항목 추가 및 제거 | Microsoft Docs"
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
  - "스레드로부터 안전한 컬렉션, 동시 사전"
ms.assetid: 81b64b95-13f7-4532-9249-ab532f629598
caps.latest.revision: 13
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 13
---
# 방법: ConcurrentDictionary에서 항목 추가 및 제거
이 예제에서는 <xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=fullName>의 항목을 추가, 검색, 업데이트 및 제거하는 방법을 보여 줍니다.  이 컬렉션 클래스는 스레드로부터 안전하게 구현되어 있습니다.  여러 스레드에서 동시에 컬렉션에 액세스할 가능성이 있는 경우에는 항상 이 클래스를 사용하는 것이 좋습니다.  
  
 <xref:System.Collections.Concurrent.ConcurrentDictionary%602>에서는 데이터를 추가 또는 제거하려고 하기 전에 키의 존재 여부를 먼저 확인하는 코드가 필요 없도록 하는 편리한 메서드를 여러 가지 제공합니다.  다음 표에서는 이와 같은 편리한 메서드를 나열하고 해당 메서드가 사용되는 경우에 대해 설명합니다.  
  
|메서드|용도|  
|---------|--------|  
|<xref:System.Collections.Concurrent.ConcurrentDictionary%602.AddOrUpdate%2A>|지정된 키의 새 값을 추가하고 키가 이미 있으면 키 값을 바꾸려는 경우|  
|<xref:System.Collections.Concurrent.ConcurrentDictionary%602.GetOrAdd%2A>|지정된 키의 기존 값을 검색하고 키가 아직 없으면 키\/값 쌍을 지정하려는 경우|  
|<xref:System.Collections.Concurrent.ConcurrentDictionary%602.TryAdd%2A>, <xref:System.Collections.Concurrent.ConcurrentDictionary%602.TryGetValue%2A> , <xref:System.Collections.Concurrent.ConcurrentDictionary%602.TryUpdate%2A> , <xref:System.Collections.Concurrent.ConcurrentDictionary%602.TryRemove%2A>|키\/값 쌍을 추가하고, 가져오고, 업데이트하거나 제거하려는 경우. 이러한 시도가 어떤 이유로 인해 실패하거나 키가 이미 있으면 다른 작업을 대신 수행하려는 경우|  
  
## 예제  
 다음 예제에서는 <xref:System.Threading.Tasks.Task> 인스턴스 두 개를 사용하여 <xref:System.Collections.Concurrent.ConcurrentDictionary%602>에 일부 요소를 동시에 추가한 다음 모든 내용을 출력하여 요소가 성공적으로 추가되었음을 보여 줍니다.  또한 이 예제에서는  <xref:System.Collections.Concurrent.ConcurrentDictionary%602.AddOrUpdate%2A>, <xref:System.Collections.Generic.Dictionary%602.TryGetValue%2A>, 및  <xref:System.Collections.Concurrent.ConcurrentDictionary%602.GetOrAdd%2A> 메서드를 사용하여 컬렉션의 항목을 추가, 업데이트, 검색 하는 방법을 보여 줍니다.  
  
 [!code-csharp[CDS#16](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds/cs/cds_dictionaryhowto.cs#16)]
 [!code-vb[CDS#16](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds/vb/cds_concdict.vb#16)]  
  
 <xref:System.Collections.Concurrent.ConcurrentDictionary%602>는 다중 스레드 시나리오에 맞게 디자인되어 있습니다.  이 컬렉션의 항목을 추가하거나 제거하기 위해 코드에서 잠금을 사용할 필요는 없습니다.  그러나 특정 스레드가 값을 검색하는 즉시 다른 스레드에서 동일한 키에 새 값을 지정하여 컬렉션을 업데이트하는 것은 항상 가능합니다.  
  
 또한 <xref:System.Collections.Concurrent.ConcurrentDictionary%602>의 모든 메서드가 스레드로부터 안전하지만 모든 메서드가 원자성 메서드인 것은 아닙니다. 특히 <xref:System.Collections.Concurrent.ConcurrentDictionary%602.GetOrAdd%2A> 및 <xref:System.Collections.Concurrent.ConcurrentDictionary%602.AddOrUpdate%2A>는 원자성 메서드가 아닙니다.  이러한 메서드에 전달되는 사용자 대리자는 사전의 내부 잠금 외부에서 호출됩니다. 이렇게 하는 이유는 알려지지 않은 코드가 모든 스레드를 차단하지 않도록 방지하기 위해서입니다. 따라서 다음과 같은 이벤트 시퀀스가 발생할 수 있습니다.  
  
 1\) threadA가 <xref:System.Collections.Concurrent.ConcurrentDictionary%602.GetOrAdd%2A>를 호출하고, 항목을 찾지 못한 다음, valueFactory 대리자를 호출하여 추가할 새 항목을 만듭니다.  
  
 2\) threadB가 <xref:System.Collections.Concurrent.ConcurrentDictionary%602.GetOrAdd%2A>를 동시에 호출하고 해당 valueFactory 대리자가 호출되어 threadA보다 먼저 내부 잠금에 도달하므로 threadB의 새 키\-값 쌍이 사전에 추가됩니다.  
  
 3\) threadA의 사용자 대리자가 완료되고 스레드가 잠금에 도달하지만 이제는 해당 항목이 이미 존재하는 것으로 표시됩니다.  
  
 4\) threadA가 "Get"을 수행하고 이전에 threadB에 의해 추가된 데이터를 반환합니다.  
  
 따라서 <xref:System.Collections.Concurrent.ConcurrentDictionary%602.GetOrAdd%2A>로 반환된 데이터가 스레드의 valueFactory로 만들어진 것과 동일한 데이터라고 보증할 수 없습니다.  <xref:System.Collections.Concurrent.ConcurrentDictionary%602.AddOrUpdate%2A>를 호출할 때에도 비슷한 이벤트 시퀀스가 발생할 수 있습니다.  
  
## 참고 항목  
 <xref:System.Collections.Concurrent?displayProperty=fullName>   
 [스레드로부터 안전한 컬렉션](../../../../docs/standard/collections/thread-safe/index.md)