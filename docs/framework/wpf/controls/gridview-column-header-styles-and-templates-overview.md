---
title: "GridView 열 머리글 스타일 및 템플릿 개요 | Microsoft Docs"
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
  - "열 머리글, 사용자 지정"
  - "컨트롤, ListView"
  - "GridView 보기 모드, 열 머리글 사용자 지정"
  - "머리글, 사용자 지정"
  - "ListView 컨트롤[WPF], GridView 열 머리글 스타일"
ms.assetid: 74835674-a39e-4ab5-9418-ad7f6ab7b956
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# GridView 열 머리글 스타일 및 템플릿 개요
이 개요에서는 <xref:System.Windows.Controls.ListView>의 <xref:System.Windows.Controls.GridView> 뷰 모드에서 컨트롤의 열 머리글을 사용자 지정하는 데 사용하는 속성의 우선 순위에 대해 설명합니다.  
  
## GridView에서 열 머리글 사용자 지정  
 <xref:System.Windows.Controls.GridView>에서 열 머리글의 콘텐츠, 레이아웃 및 스타일을 정의하는 속성은 관련된 많은 클래스에서 찾을 수 있습니다.  이러한 속성 중 일부는 그 기능이 비슷하거나 같습니다.  
  
 다음 표의 행에서는 동일한 기능을 수행하는 속성 그룹을 보여 줍니다.  이러한 속성을 사용하여 <xref:System.Windows.Controls.GridView>의 열 머리글을 사용자 지정할 수 있습니다.  관련된 속성의 우선 순위는 왼쪽에서 오른쪽으로 갈수록 높아지며 맨 오른쪽 열의 속성이 우선 순위가 가장 높습니다.  예를 들어 <xref:System.Windows.Controls.GridViewColumnHeader> 개체에 <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A>이 설정되고 관련된 <xref:System.Windows.Controls.GridViewColumn>에 <xref:System.Windows.Controls.GridViewColumn.HeaderTemplateSelector%2A>가 설정된 경우 <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A>의 우선 순위가 더 높습니다.  이 시나리오에서는 <xref:System.Windows.Controls.GridViewColumn.HeaderTemplateSelector%2A>가 아무런 영향을 주지 않습니다.  
  
 **GridView의 열 머리글과 관련된 속성**  
  
|||||  
|-|-|-|-|  
|**클래스**|<xref:System.Windows.Controls.GridView>|<xref:System.Windows.Controls.GridViewColumn>|<xref:System.Windows.Controls.GridViewColumnHeader>|  
|**Context Menu 속성**|<xref:System.Windows.Controls.GridView.ColumnHeaderContextMenu%2A>|해당 없음|<xref:System.Windows.FrameworkElement.ContextMenu%2A>|  
|**ToolTip**<br /><br /> **속성**|<xref:System.Windows.Controls.GridView.ColumnHeaderToolTip%2A>|해당 없음|<xref:System.Windows.FrameworkElement.ToolTip%2A>|  
|**Header Template**<br /><br /> **속성**|<xref:System.Windows.Controls.GridView.ColumnHeaderTemplate%2A> <sup>1</sup>\/<br /><br /> <xref:System.Windows.Controls.GridView.ColumnHeaderTemplateSelector%2A>|<xref:System.Windows.Controls.GridViewColumn.HeaderTemplate%2A> <sup>1</sup>\/<br /><br /> <xref:System.Windows.Controls.GridViewColumn.HeaderTemplateSelector%2A>|<xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> <sup>1</sup>\/<br /><br /> <xref:System.Windows.Controls.ContentControl.ContentTemplateSelector%2A>|  
|**Style 속성**|<xref:System.Windows.Controls.GridView.ColumnHeaderContainerStyle%2A>|<xref:System.Windows.Controls.GridViewColumn.HeaderContainerStyle%2A>|<xref:System.Windows.FrameworkElement.Style%2A>|  
  
 <sup>1</sup> **Header Template 속성**의 경우 템플릿 속성과 템플릿 선택자 속성을 둘 다 설정하는 경우 템플릿 속성의 우선 순위가 더 높습니다.  예를 들어 <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> 속성과 <xref:System.Windows.Controls.ContentControl.ContentTemplateSelector%2A> 속성을 둘 다 설정하면 <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> 속성의 우선 순위가 더 높습니다.  
  
## 참고 항목  
 [방법 항목](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)   
 [ListView 개요](../../../../docs/framework/wpf/controls/listview-overview.md)   
 [GridView 개요](../../../../docs/framework/wpf/controls/gridview-overview.md)