---
title: "방법: 이벤트 발생 및 사용 | Microsoft Docs"
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
  - "이벤트[.NET Framework], 발생"
  - "이벤트[.NET Framework], 샘플"
  - "이벤트 발생"
ms.assetid: 42afade7-3a02-4f2e-868b-95845f302f8f
caps.latest.revision: 13
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 13
---
# 방법: 이벤트 발생 및 사용
이 항목의 예제에서는 이벤트를 사용하는 방법을 보여줍니다.  여기선 <xref:System.EventHandler> 대리자, <xref:System.EventHandler%601> 대리자 및 데이터와 또는 데이터와 관계 없이 이벤트를 설명하기 위한 사용자 지정 대리자에 대한 예를 포함합니다.  
  
 예제에서는 [이벤트](../../../docs/standard/events/index.md) 문서에서 기술하고 있는 개념을 사용합니다.  
  
## 예제  
 첫 번째 예제에서는 데이터가 없는 이벤트를 발생 시키고 사용하는 방법에 대해 보여줍니다.  이것은 `ThresholdReached`. 이벤트를 가지는 `Counter` 클래스를 포함합니다.  이 이벤트는 카운터 값이 같거나 또는 임계값을 초과할 때 발생합니다.  <xref:System.EventHandler> 대리자는 해당 이벤트와 연결됩니다. 왜냐하면 어떠한 이벤트 데이터도 제공되지 않기 때문입니다.  
  
 [!code-csharp[EventsOverview#5](../../../samples/snippets/csharp/VS_Snippets_CLR/eventsoverview/cs/programnodata.cs#5)]
 [!code-vb[EventsOverview#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/eventsoverview/vb/module1nodata.vb#5)]  
  
## 예제  
 다음 예제에서는 데이터를 제공하는 이벤트를 발생 시키고 사용하는 방법에 대해 보여줍니다.  <xref:System.EventHandler%601> 대리자가 이벤트를 통해 연결되고, 사용자 지정 이벤트 데이터 개체의 인스턴스가 제공됩니다.  
  
 [!code-cpp[EventsOverview#6](../../../samples/snippets/cpp/VS_Snippets_CLR/eventsoverview/cpp/programwithdata.cpp#6)]
 [!code-csharp[EventsOverview#6](../../../samples/snippets/csharp/VS_Snippets_CLR/eventsoverview/cs/programwithdata.cs#6)]
 [!code-vb[EventsOverview#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/eventsoverview/vb/module1withdata.vb#6)]  
  
## 예제  
 다음 예제에서는 이벤트의 대리자를 선언하는 방법을 보여줍니다.  대리자의 이름은 `ThresholdReachedEventHandler` 입니다.  이는 단지 예를 든 것일 뿐입니다.  일반적으로 이벤트에 대한 대리자를 선언할 필요가 없습니다. 왜냐하면 <xref:System.EventHandler> 또는 <xref:System.EventHandler%601> 대리인중 중 하나를 사용할 수 있기 때문입니다.  대리자는 제네릭을 사용할 수 없는 레거시 코드를 사용할 수 있는 클래스를 확인 하는 경우 같이 드문 경우에만 선언해야 합니다.  
  
 [!code-csharp[EventsOverview#7](../../../samples/snippets/csharp/VS_Snippets_CLR/eventsoverview/cs/programwithdelegate.cs#7)]
 [!code-vb[EventsOverview#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/eventsoverview/vb/module1withdelegate.vb#7)]  
  
## 참고 항목  
 [이벤트](../../../docs/standard/events/index.md)