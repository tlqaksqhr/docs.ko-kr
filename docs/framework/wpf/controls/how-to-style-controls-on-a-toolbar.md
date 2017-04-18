---
title: "방법: ToolBar 컨트롤의 스타일 지정 | Microsoft Docs"
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
  - "도구 모음의 컨트롤 사용자 지정"
  - "도구 모음의 컨트롤 스타일 지정"
  - "도구 모음"
ms.assetid: ba6ae056-d6a9-4c24-90f8-467ab0bc0b1a
caps.latest.revision: 4
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 4
---
# 방법: ToolBar 컨트롤의 스타일 지정
<xref:System.Windows.Controls.ToolBar>는 <xref:System.Windows.ResourceKey> 개체를 정의하여 <xref:System.Windows.Controls.ToolBar> 내의 컨트롤 스타일을 지정합니다.  <xref:System.Windows.Controls.ToolBar>에 있는 컨트롤의 스타일을 지정하려면 스타일의 `x:key` 특성을 <xref:System.Windows.Controls.ToolBar>에 정의되어 있는 <xref:System.Windows.ResourceKey>로 설정합니다.  
  
 <xref:System.Windows.Controls.ToolBar>는 다음 <xref:System.Windows.ResourceKey> 개체를 정의합니다.  
  
-   <xref:System.Windows.Controls.ToolBar.ButtonStyleKey%2A>  
  
-   <xref:System.Windows.Controls.ToolBar.CheckBoxStyleKey%2A>  
  
-   <xref:System.Windows.Controls.ToolBar.ComboBoxStyleKey%2A>  
  
-   <xref:System.Windows.Controls.ToolBar.MenuStyleKey%2A>  
  
-   <xref:System.Windows.Controls.ToolBar.RadioButtonStyleKey%2A>  
  
-   <xref:System.Windows.Controls.ToolBar.SeparatorStyleKey%2A>  
  
-   <xref:System.Windows.Controls.ToolBar.TextBoxStyleKey%2A>  
  
-   <xref:System.Windows.Controls.ToolBar.ToggleButtonStyleKey%2A>  
  
## 예제  
 다음 예제에서는 <xref:System.Windows.Controls.ToolBar> 내의 컨트롤에 대한 스타일을 정의합니다.  
  
 [!code-xml[ToolBar_snip#ToolBarAllStyles](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolBar_snip/CS/pane1.xaml#toolbarallstyles)]  
[!code-xml[ToolBar_snip#ToolBar](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolBar_snip/CS/pane1.xaml#toolbar)]  
  
## 참고 항목  
 [스타일 지정 및 템플릿](../../../../docs/framework/wpf/controls/styling-and-templating.md)