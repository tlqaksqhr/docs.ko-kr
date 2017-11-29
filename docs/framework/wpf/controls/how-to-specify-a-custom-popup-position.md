---
title: "방법: 사용자 지정 팝업 위치 지정"
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
helpviewer_keywords: Popup control [WPF], specifying custom position
ms.assetid: 28c24f39-d3aa-4ee2-b950-384b4a5dab92
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0ab9baca1103adf8de96204bdb1b3353a5456b94
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-specify-a-custom-popup-position"></a>방법: 사용자 지정 팝업 위치 지정
에 대 한 사용자 지정 위치를 지정 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.Primitives.Popup> 제어는 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> 속성이로 설정 된 <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>합니다.  
  
## <a name="example"></a>예제  
 때는 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> 속성이 <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>, <xref:System.Windows.Controls.Primitives.Popup> 호출의 정의 된 인스턴스는 <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> 위임 합니다. 대상 영역의 왼쪽된 위 모퉁이의 왼쪽된 위 모퉁이 기준으로 가능한 지점 집합을 반환 하는이 대리자는 <xref:System.Windows.Controls.Primitives.Popup>합니다. <xref:System.Windows.Controls.Primitives.Popup> 최상의 가시성을 제공 하는 지점에 배치 됩니다.  
  
 위치를 정의 하는 방법을 보여 주는 다음 예제는 <xref:System.Windows.Controls.Primitives.Popup> 설정 하 여는 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> 속성을 <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>합니다. 만들고 할당 하는 방법을 보여 줍니다는 <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> 배치 하기 위해 대리자는 <xref:System.Windows.Controls.Primitives.Popup>합니다.  두 콜백 대리자 반환 <xref:System.Windows.Controls.Primitives.CustomPopupPlacement> 개체입니다.  경우는 <xref:System.Windows.Controls.Primitives.Popup> 화면 가장자리에 첫 번째 위치에 의해 숨겨져는 <xref:System.Windows.Controls.Primitives.Popup> 두 번째 위치에 배치 됩니다.  
  
 [!code-xaml[PopupCustomPlacement#CustomPlacement](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml#customplacement)]  
  
 [!code-csharp[PopupCustomPlacement#DelegateInstance](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml.cs#delegateinstance)]
 [!code-vb[PopupCustomPlacement#DelegateInstance](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PopupCustomPlacement/visualbasic/window1.xaml.vb#delegateinstance)]  
  
 [!code-csharp[PopupCustomPlacement#DelegateDefinition](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml.cs#delegatedefinition)]
 [!code-vb[PopupCustomPlacement#DelegateDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PopupCustomPlacement/visualbasic/window1.xaml.vb#delegatedefinition)]  
  
 전체 샘플을 참조 하십시오. [팝업 배치 샘플](http://go.microsoft.com/fwlink/?LinkID=160032)합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Controls.Primitives.Popup>  
 [팝업 개요](../../../../docs/framework/wpf/controls/popup-overview.md)  
 [방법 항목](../../../../docs/framework/wpf/controls/popup-how-to-topics.md)
