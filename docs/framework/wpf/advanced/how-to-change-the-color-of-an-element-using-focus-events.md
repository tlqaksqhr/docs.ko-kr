---
title: "방법: 포커스 이벤트를 사용하여 요소의 색 변경 | Microsoft Docs"
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
  - "요소 색, 변경"
  - "요소, 색 변경"
  - "포커스 이벤트, 요소 색 변경"
ms.assetid: 7e246802-3625-47a7-ae9d-c8a2a40fd040
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# 방법: 포커스 이벤트를 사용하여 요소의 색 변경
이 예제에서는 <xref:System.Windows.UIElement.GotFocus> 및 <xref:System.Windows.UIElement.LostFocus> 이벤트를 사용하여 요소가 포커스를 얻거나 잃을 때 요소의 색을 변경하는 방법을 보여 줍니다.  
  
 이 예제는 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 파일과 코드 숨김 파일로 구성됩니다.  
  
## 예제  
 다음 [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)]에서는 두 <xref:System.Windows.Controls.Button> 개체로 구성된 사용자 인터페이스를 만들고 <xref:System.Windows.UIElement.GotFocus> 및 <xref:System.Windows.UIElement.LostFocus> 이벤트에 대한 이벤트 처리기를 <xref:System.Windows.Controls.Button> 개체에 연결합니다.  
  
 [!code-xml[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/CSharp/Window1.xaml#gotlostfocussamplexaml)]  
  
 다음 코드 숨김은 <xref:System.Windows.UIElement.GotFocus> 및 <xref:System.Windows.UIElement.LostFocus> 이벤트 처리기를 만듭니다.  <xref:System.Windows.Controls.Button>이 키보드 포커스를 얻으면 <xref:System.Windows.Controls.Button>의 <xref:System.Windows.Controls.Control.Background%2A>가 빨간색으로 변경됩니다.  <xref:System.Windows.Controls.Button>이 키보드 포커스를 잃으면 <xref:System.Windows.Controls.Button>의 <xref:System.Windows.Controls.Control.Background%2A>가 흰색으로 돌아갑니다.  
  
 [!code-csharp[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleEventHandlers](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/CSharp/Window1.xaml.cs#gotlostfocussampleeventhandlers)]
 [!code-vb[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleEventHandlers](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/VisualBasic/Window1.xaml.vb#gotlostfocussampleeventhandlers)]  
  
## 참고 항목  
 [입력 개요](../../../../docs/framework/wpf/advanced/input-overview.md)