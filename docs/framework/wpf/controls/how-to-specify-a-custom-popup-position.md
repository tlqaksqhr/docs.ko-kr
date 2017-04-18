---
title: "방법: 사용자 지정 팝업 위치 지정 | Microsoft Docs"
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
  - "Popup 컨트롤, 사용자 지정 위치 지정"
ms.assetid: 28c24f39-d3aa-4ee2-b950-384b4a5dab92
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# 방법: 사용자 지정 팝업 위치 지정
이 예제에서는 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> 속성이 <xref:System.Windows.Controls.Primitives.PlacementMode>으로 설정된 경우 <xref:System.Windows.Controls.Primitives.Popup> 컨트롤의 위치를 사용자 지정하는 방법을 보여 줍니다.  
  
## 예제  
 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> 속성이 <xref:System.Windows.Controls.Primitives.PlacementMode>으로 설정되어 있으면 <xref:System.Windows.Controls.Primitives.Popup>이 <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> 대리자의 정의된 인스턴스를 호출합니다.  이 대리자는 대상 영역의 왼쪽 위 모퉁이 및 <xref:System.Windows.Controls.Primitives.Popup>의 왼쪽 위 모퉁이를 기준으로 가능한 일련의 지점을 반환합니다.  <xref:System.Windows.Controls.Primitives.Popup>은 가시도가 가장 높은 지점에 배치됩니다.  
  
 다음 예제에서는 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> 속성을 <xref:System.Windows.Controls.Primitives.PlacementMode>으로 설정하여 <xref:System.Windows.Controls.Primitives.Popup>의 위치를 정의하는 방법을 보여 줍니다.  또한 <xref:System.Windows.Controls.Primitives.Popup>을 배치하기 위해 <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> 대리자를 만들어 할당하는 방법도 보여 줍니다.  콜백 대리자는 두 개의 <xref:System.Windows.Controls.Primitives.CustomPopupPlacement> 개체를 반환합니다.  첫 번째 위치에서 <xref:System.Windows.Controls.Primitives.Popup>이 화면 가장자리에 의해 가려지는 경우 두 번째 위치에 <xref:System.Windows.Controls.Primitives.Popup>이 배치됩니다.  
  
 [!code-xml[PopupCustomPlacement#CustomPlacement](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml#customplacement)]  
  
 [!code-csharp[PopupCustomPlacement#DelegateInstance](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml.cs#delegateinstance)]
 [!code-vb[PopupCustomPlacement#DelegateInstance](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PopupCustomPlacement/visualbasic/window1.xaml.vb#delegateinstance)]  
  
 [!code-csharp[PopupCustomPlacement#DelegateDefinition](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml.cs#delegatedefinition)]
 [!code-vb[PopupCustomPlacement#DelegateDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PopupCustomPlacement/visualbasic/window1.xaml.vb#delegatedefinition)]  
  
 전체 샘플을 보려면 [Popup Placement 샘플](http://go.microsoft.com/fwlink/?LinkID=160032)을 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.Controls.Primitives.Popup>   
 [Popup 개요](../../../../docs/framework/wpf/controls/popup-overview.md)   
 [방법 항목](../../../../docs/framework/wpf/controls/popup-how-to-topics.md)