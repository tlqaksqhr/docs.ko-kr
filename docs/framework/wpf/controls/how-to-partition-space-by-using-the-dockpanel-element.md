---
title: "방법: DockPanel 요소를 사용하여 공간 분할 | Microsoft Docs"
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
  - "컨트롤[WPF], DockPanel"
  - "DockPanel 컨트롤, 공간 분할"
  - "공간 분할"
ms.assetid: a219b9e5-b205-4438-89b5-0a137ac463ab
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# 방법: DockPanel 요소를 사용하여 공간 분할
다음 예제에서는 <xref:System.Windows.Controls.DockPanel> 요소를 사용하여 간단한 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 프레임워크를 만듭니다.  <xref:System.Windows.Controls.DockPanel>은 사용할 수 있는 공간을 여러 자식 요소로 분할합니다.  
  
## 예제  
 이 예제에서는 [연결된 속성](GTMT)인 <xref:System.Windows.Controls.DockPanel.Dock%2A> 속성을 사용하여 분할된 공간의 <xref:System.Windows.Controls.Dock> 위치에 동일한 두 <xref:System.Windows.Controls.Border> 요소를 도킹합니다.  셋째 <xref:System.Windows.Controls.Border> 요소는 너비가 200픽셀로 설정된 상태로 <xref:System.Windows.Controls.Dock>에 도킹됩니다.  넷째 <xref:System.Windows.Controls.Border>는 화면의 <xref:System.Windows.Controls.Dock>에 도킹됩니다.  마지막 <xref:System.Windows.Controls.Border> 요소는 자동으로 남은 공간을 채웁니다.  
  
 [!code-cpp[DockPanelOvwSample#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/DockPanelOvwSample/CPP/DockPanel_Ovw_Sample.cpp#1)]
 [!code-csharp[DockPanelOvwSample#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DockPanelOvwSample/CSharp/DockPanel_Ovw_Sample.cs#1)]
 [!code-vb[DockPanelOvwSample#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DockPanelOvwSample/VisualBasic/dockpanel_vb.vb#1)]
 [!code-xml[DockPanelOvwSample#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DockPanelOvwSample/XAML/default.xaml#1)]  
  
> [!NOTE]
>  기본적으로 <xref:System.Windows.Controls.DockPanel> 요소의 마지막 자식은 할당되지 않은 나머지 영역을 채웁니다.  이 동작을 방지하려면 `LastChildFill="False"`를 설정하십시오.  
  
 컴파일된 응용 프로그램의 새로운 UI 모습은 다음과 같습니다.  
  
 ![일반적인 DockPanel 시나리오](../../../../docs/framework/wpf/controls/media/panel-intro-dockpanel.png "panel\_intro\_dockpanel")  
  
## 참고 항목  
 <xref:System.Windows.Controls.DockPanel>   
 [Panel 개요](../../../../docs/framework/wpf/controls/panels-overview.md)