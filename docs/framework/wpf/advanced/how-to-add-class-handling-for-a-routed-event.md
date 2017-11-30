---
title: "방법: 라우트된 이벤트에 대한 클래스 처리 추가"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- routed events [WPF], class handlers
- task_core_add_class_handling_routed_properties [WPF]
- class handlers [WPF], routed events
ms.assetid: 15b7b06c-9112-4ee5-b30a-65d10c5c5df6
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: abbbdce0ca12c4d8bdd12f616bf49c3d6f66f441
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-add-class-handling-for-a-routed-event"></a>방법: 라우트된 이벤트에 대한 클래스 처리 추가
클래스 처리기 또는 경로의 지정 된 노드에서 인스턴스 처리기에 의해 라우트된 이벤트를 처리할 수 있습니다. 클래스 처리기 먼저 호출 되며 및 인스턴스 처리에서 이벤트를 억제 또는 기본 클래스에서 소유 하는 이벤트에 다른 이벤트 특정 동작을 클래스 구현에서 사용할 수 있습니다. 이 예제에는 클래스 처리기를 구현 하기 위한 밀접 한 관련이 있는 두 가지 기술을 보여 줍니다.  
  
## <a name="example"></a>예제  
 이 예제에 따라 사용자 지정 클래스를 사용 하 여 <xref:System.Windows.Controls.Canvas> 패널입니다. 응용 프로그램의 기본 전제는 사용자 지정 클래스는 마우스 왼쪽된 단추 클릭을 차단 하 고 처리 된 것으로, 자식 요소 클래스 또는 인스턴스 처리기에서 호출 될 전에 표시를 포함 하 여 해당 자식 요소에 있는 동작을 소개 합니다.  
  
 <xref:System.Windows.UIElement> 클래스 처리에 있는 가상 메서드를 노출 하는 클래스는 <xref:System.Windows.UIElement.PreviewMouseLeftButtonDown> 단순히 이벤트를 재정의 하 여 이벤트입니다. 이것이 가상 메서드를 클래스의 계층 구조에서 사용할 수 있는 경우 클래스 처리를 구현 하는 가장 간단한 방법은입니다. 다음 코드는 <xref:System.Windows.UIElement.OnPreviewMouseLeftButtonDown%2A> 는 "MyEditContainer"에서 파생 된 구현 <xref:System.Windows.Controls.Canvas>합니다. 구현에서 이벤트 인수를 처리 하는 것으로 표시 하 고 기본 화면상의 변화는 소스 요소를 제공 하는 코드를 추가 합니다.  
  
 [!code-csharp[ClassHandling#OnStarClassHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ClassHandling/CSharp/SDKSampleLibrary/class1.cs#onstarclasshandler)]
 [!code-vb[ClassHandling#OnStarClassHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ClassHandling/visualbasic/sdksamplelibrary/class1.vb#onstarclasshandler)]  
  
 클래스 처리의는 유틸리티 메서드를 사용 하 여 직접 추가할 수 더 가상 기본 클래스에서 또는 해당 특정 방법에 대해 표시 되 면는 <xref:System.Windows.EventManager> 클래스 <xref:System.Windows.EventManager.RegisterClassHandler%2A>합니다. 이 메서드는 클래스 처리를 추가 하는 클래스의 정적 초기화 내만 호출 해야 합니다. 이 예제에서는 다른 처리기에 대 한 추가 <xref:System.Windows.UIElement.PreviewMouseLeftButtonDown> ,이 경우 등록 된 클래스는 사용자 지정 클래스. 반대로 가상 메서드를 사용 하는 경우 등록 된 클래스는 실제로 <xref:System.Windows.UIElement> 기본 클래스입니다. 기본 클래스 및 하위 클래스는 각 등록할 클래스 처리에 있는 경우에는 서브 클래스 처리기는 먼저 호출 됩니다. 응용 프로그램에서 동작 우선이 처리기는 해당 메시지 상자를 표시 하 고는 가상 메서드의 처리기의 시각적 변경 내용이 다음 표시 되는 것입니다.  
  
 [!code-csharp[ClassHandling#StaticAndRegisterClassHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ClassHandling/CSharp/SDKSampleLibrary/class1.cs#staticandregisterclasshandler)]
 [!code-vb[ClassHandling#StaticAndRegisterClassHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ClassHandling/visualbasic/sdksamplelibrary/class1.vb#staticandregisterclasshandler)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.EventManager>  
 [라우트된 이벤트를 처리된 것으로 표시 및 클래스 처리](../../../../docs/framework/wpf/advanced/marking-routed-events-as-handled-and-class-handling.md)  
 [라우트된 이벤트 처리](../../../../docs/framework/wpf/advanced/how-to-handle-a-routed-event.md)  
 [라우트된 이벤트 개요](../../../../docs/framework/wpf/advanced/routed-events-overview.md)
