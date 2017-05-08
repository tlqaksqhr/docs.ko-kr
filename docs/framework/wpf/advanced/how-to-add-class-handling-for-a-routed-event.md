---
title: "방법: 라우트된 이벤트에 대한 클래스 처리 추가 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "클래스 처리기, 라우트된 이벤트"
  - "라우트된 이벤트, 클래스 처리기"
  - "task_core_add_class_handling_routed_event"
ms.assetid: 15b7b06c-9112-4ee5-b30a-65d10c5c5df6
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# 방법: 라우트된 이벤트에 대한 클래스 처리 추가
라우트된 이벤트는 경로 내의 임의의 노드에 있는 클래스 처리기 또는 인스턴스 처리기를 통해 처리할 수 있습니다.  클래스 처리기는 인스턴스 처리기보다 먼저 호출되며 이벤트가 인스턴스 처리되지 않도록 하거나 기본 클래스가 소유하는 이벤트에 대해 다른 이벤트 특정 동작을 발생시키기 위해 클래스 구현에서 사용할 수 있습니다.  이 예제에서는 클래스 처리기 구현에 사용되며 서로 밀접한 관련이 있는 두 가지 방법을 보여 줍니다.  
  
## 예제  
 이 예제에서는 <xref:System.Windows.Controls.Canvas> 패널에 기반을 둔 사용자 지정 클래스를 사용합니다.  응용 프로그램에서는 기본적으로, 사용자 지정 클래스가 자식 요소 클래스 또는 자식 요소 클래스의 인스턴스 처리기가 호출되기 전에 마우스 왼쪽 단추 클릭을 가로채거나 이를 처리된 것으로 표시하는 등의 동작을 해당 자식 요소에서 발생시킨다고 가정합니다.  
  
 <xref:System.Windows.UIElement> 클래스는 단순히 이벤트를 재정의하여 <xref:System.Windows.UIElement.PreviewMouseLeftButtonDown> 이벤트를 클래스에서 처리할 수 있도록 지원하는 가상 메서드를 노출합니다.  클래스 계층 구조 내에서 이러한 가상 메서드를 사용할 수만 있다면 이는 클래스 처리를 구현하는 가장 간단한 방법입니다.  다음 코드에서는 <xref:System.Windows.Controls.Canvas>에서 파생된 "MyEditContainer" 내에 구현된 <xref:System.Windows.UIElement.OnPreviewMouseLeftButtonDown%2A>을 보여 줍니다.  이 구현에서는 해당 인수에 이벤트가 처리된 것으로 표시한 다음 코드를 추가하여 소스 요소에 기본적인 가시적 변경을 제공합니다.  
  
 [!code-csharp[ClassHandling#OnStarClassHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ClassHandling/CSharp/SDKSampleLibrary/class1.cs#onstarclasshandler)]
 [!code-vb[ClassHandling#OnStarClassHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ClassHandling/visualbasic/sdksamplelibrary/class1.vb#onstarclasshandler)]  
  
 기본 클래스에서 또는 해당 특정 메서드에 대해 가상 메서드를 사용할 수 없는 경우 <xref:System.Windows.EventManager> 클래스의 유틸리티 메서드인 <xref:System.Windows.EventManager.RegisterClassHandler%2A>를 사용하여 클래스 처리를 직접 추가할 수 있습니다.  이 메서드는 클래스 처리를 추가하는 클래스의 정적 초기화 내에서만 호출되어야 합니다.  이 예제에서는 <xref:System.Windows.UIElement.PreviewMouseLeftButtonDown>에 대한 또 다른 처리기를 추가하며 이 경우 등록된 클래스가 사용자 지정 클래스입니다.  반면 가상 메서드를 사용할 때는 등록된 클래스가 실제로는 <xref:System.Windows.UIElement> 기본 클래스입니다.  기본 클래스와 서브클래스가 각각 클래스 처리를 등록하는 경우에는 서브클래스 처리기가 먼저 호출됩니다.  먼저 이 처리기가 해당 메시지 상자를 표시한 다음 가상 메서드 처리기의 시각적 변경 내용이 표시되는 것이 응용 프로그램의 동작입니다.  
  
 [!code-csharp[ClassHandling#StaticAndRegisterClassHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ClassHandling/CSharp/SDKSampleLibrary/class1.cs#staticandregisterclasshandler)]
 [!code-vb[ClassHandling#StaticAndRegisterClassHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ClassHandling/visualbasic/sdksamplelibrary/class1.vb#staticandregisterclasshandler)]  
  
## 참고 항목  
 <xref:System.Windows.EventManager>   
 [라우트된 이벤트를 처리된 것으로 표시 및 클래스 처리](../../../../docs/framework/wpf/advanced/marking-routed-events-as-handled-and-class-handling.md)   
 [라우트된 이벤트 처리](../../../../docs/framework/wpf/advanced/how-to-handle-a-routed-event.md)   
 [라우트된 이벤트 개요](../../../../docs/framework/wpf/advanced/routed-events-overview.md)