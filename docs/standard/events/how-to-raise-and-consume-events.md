---
title: "방법: 이벤트 발생 및 사용"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- events [.NET Framework], raising
- raising events
- events [.NET Framework], samples
ms.assetid: 42afade7-3a02-4f2e-868b-95845f302f8f
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d052c865a554977ce5c8b0a347337d9d9b92fc57
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-raise-and-consume-events"></a>방법: 이벤트 발생 및 사용
이 항목의 예제에서는 이벤트로 작업하는 방법을 보여 줍니다. 여기서 <xref:System.EventHandler> 대리자, <xref:System.EventHandler%601> 대리자 및 사용자 지정 대리자의 예제를 통해 데이터를 사용하거나 사용하지 않는 이벤트를 설명합니다.  
  
 에 설명 된 개념을 사용 하는 예제는 [이벤트](../../../docs/standard/events/index.md) 문서.  
  
## <a name="example"></a>예제  
 첫 번째 예제에서는 데이터가 없는 이벤트를 발생시키고 사용하는 방법을 보여 줍니다. 이벤트의 이름이 `Counter`인 `ThresholdReached`라는 클래스를 포함합니다. 이 이벤트는 카운터 값이 같거나 임계값을 초과할 때 발생합니다. 이벤트 데이터가 제공되지 않았으므로 <xref:System.EventHandler> 대리자는 이벤트와 연결됩니다.  
  
 [!code-csharp[EventsOverview#5](../../../samples/snippets/csharp/VS_Snippets_CLR/eventsoverview/cs/programnodata.cs#5)]
 [!code-vb[EventsOverview#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/eventsoverview/vb/module1nodata.vb#5)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 데이터를 제공하는 이벤트를 발생시키고 사용하는 방법을 보여 줍니다. <xref:System.EventHandler%601> 대리자가 이벤트와 연결되었으며 사용자 지정 이벤트 데이터 개체의 인스턴스가 제공되었습니다.  
  
 [!code-cpp[EventsOverview#6](../../../samples/snippets/cpp/VS_Snippets_CLR/eventsoverview/cpp/programwithdata.cpp#6)]
 [!code-csharp[EventsOverview#6](../../../samples/snippets/csharp/VS_Snippets_CLR/eventsoverview/cs/programwithdata.cs#6)]
 [!code-vb[EventsOverview#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/eventsoverview/vb/module1withdata.vb#6)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 이벤트의 대리자를 선언하는 방법을 보여 줍니다. 대리자의 이름은 `ThresholdReachedEventHandler`입니다. 이는 단지 예를 든 것이며, 일반적으로 이벤트에 대한 대리자를 선언할 필요가 없습니다. <xref:System.EventHandler> 또는 <xref:System.EventHandler%601> 대리자 중 하나를 사용할 수 있기 때문입니다. 대리자는 제네릭을 사용할 수 없는 레거시 코드에서 클래스를 사용할 수 있는 경우와 같이 드문 시나리오에서만 선언해야 합니다.  
  
 [!code-csharp[EventsOverview#7](../../../samples/snippets/csharp/VS_Snippets_CLR/eventsoverview/cs/programwithdelegate.cs#7)]
 [!code-vb[EventsOverview#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/eventsoverview/vb/module1withdelegate.vb#7)]  
  
## <a name="see-also"></a>참고 항목  
 [이벤트](../../../docs/standard/events/index.md)
