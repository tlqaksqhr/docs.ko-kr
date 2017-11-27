---
title: "GridView 열 머리글 스타일 및 템플릿 개요"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- column headers [WPF], customizing
- ListView controls [WPF], GridView column header styles
- controls [WPF], ListView
- headers [WPF], customizing
- GridView view mode [WPF], customizing column headers
ms.assetid: 74835674-a39e-4ab5-9418-ad7f6ab7b956
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ad0f7cacc8256e060bb12611bd1818b694e1e6dc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="gridview-column-header-styles-and-templates-overview"></a>GridView 열 머리글 스타일 및 템플릿 개요
이 개요에서는의 열 머리글에 사용자 지정 하는 속성에 대 한 우선 순위는 <xref:System.Windows.Controls.GridView> 의 보기 모드는 <xref:System.Windows.Controls.ListView> 제어 합니다.  
  
## <a name="customizing-a-column-header-in-a-gridview"></a>GridView에서 열 머리글을 사용자 지정  
 내용, 레이아웃 및 열 머리글의 스타일을 정의 하는 속성은 <xref:System.Windows.Controls.GridView> 여러 관련된 클래스에는 찾을 수 있습니다. 이러한 속성 중 일부는 동일 하거나 유사한 기능을 되었습니다.  
  
 다음 테이블에 행 그룹은 동일한 기능을 수행 하는 속성을 보여 줍니다. 열 머리글을 사용자 지정 하려면 이러한 속성을 사용할 수는 <xref:System.Windows.Controls.GridView>합니다. 가장 멀리 오른쪽 열에 속성의 가장 높은 우선 순위에 있는 오른쪽에서 왼쪽으로의 관련된 속성에 대 한 우선 순위는 합니다. 예를 들어 경우는 <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> 에 설정 되어는 <xref:System.Windows.Controls.GridViewColumnHeader> 개체 및 <xref:System.Windows.Controls.GridViewColumn.HeaderTemplateSelector%2A> 연결 설정 <xref:System.Windows.Controls.GridViewColumn>, <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> 우선적으로 적용 합니다. 이 시나리오는 <xref:System.Windows.Controls.GridViewColumn.HeaderTemplateSelector%2A> 영향을 주지 않습니다.  
  
 **GridView에서 열 머리글에 대 한 관련된 속성**  
  
|||||  
|-|-|-|-|  
|**클래스**|<xref:System.Windows.Controls.GridView>|<xref:System.Windows.Controls.GridViewColumn>|<xref:System.Windows.Controls.GridViewColumnHeader>|  
|**상황에 맞는 메뉴 속성**|<xref:System.Windows.Controls.GridView.ColumnHeaderContextMenu%2A>|적용할 수 없음|<xref:System.Windows.FrameworkElement.ContextMenu%2A>|  
|**ToolTip**<br /><br /> **속성**|<xref:System.Windows.Controls.GridView.ColumnHeaderToolTip%2A>|적용할 수 없음|<xref:System.Windows.FrameworkElement.ToolTip%2A>|  
|**헤더 서식 파일**<br /><br /> **속성**|<xref:System.Windows.Controls.GridView.ColumnHeaderTemplate%2A> <sup>1</sup>/<br /><br /> <xref:System.Windows.Controls.GridView.ColumnHeaderTemplateSelector%2A>|<xref:System.Windows.Controls.GridViewColumn.HeaderTemplate%2A> <sup>1</sup>/<br /><br /> <xref:System.Windows.Controls.GridViewColumn.HeaderTemplateSelector%2A>|<xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> <sup>1</sup>/<br /><br /> <xref:System.Windows.Controls.ContentControl.ContentTemplateSelector%2A>|  
|**스타일 속성**|<xref:System.Windows.Controls.GridView.ColumnHeaderContainerStyle%2A>|<xref:System.Windows.Controls.GridViewColumn.HeaderContainerStyle%2A>|<xref:System.Windows.FrameworkElement.Style%2A>|  
  
 <sup>1</sup>에 대 한 **헤더 템플릿 속성**템플릿을 템플릿 선택기 속성, 서식 파일 속성은 우선 순위를 설정 하는 경우, 합니다. 예를 들어, 모두 설정 하면는 <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> 및 <xref:System.Windows.Controls.ContentControl.ContentTemplateSelector%2A> 속성는 <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> 속성이 우선 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [방법 항목](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)  
 [ListView 개요](../../../../docs/framework/wpf/controls/listview-overview.md)  
 [GridView 개요](../../../../docs/framework/wpf/controls/gridview-overview.md)
