---
title: "방법: 끌어 온 GridView 열 머리글의 스타일 만들기 | Microsoft Docs"
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
  - "ListView 컨트롤, 스타일 지정"
ms.assetid: 0b999645-0313-4b33-80b9-19ece08b5459
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# 방법: 끌어 온 GridView 열 머리글의 스타일 만들기
이 예제에서는 사용자가 열의 위치를 변경할 때 끌어 온 <xref:System.Windows.Controls.GridViewColumnHeader>의 모양을 변경하는 방법을 보여 줍니다.  
  
## 예제  
 <xref:System.Windows.Controls.GridView>를 보기 모드로 사용하는 <xref:System.Windows.Controls.ListView>의 다른 위치로 열 머리글을 끌면 열이 새 위치로 이동합니다.  열 머리글을 끄는 동안에는 원래 머리글 이외에 헤더의 부동 복사본이 나타납니다.  <xref:System.Windows.Controls.GridView>의 열 머리글은 <xref:System.Windows.Controls.GridViewColumnHeader> 개체로 표현됩니다.  
  
 부동 머리글과 원래 머리글 모두의 모양을 사용자 지정하려면 <xref:System.Windows.Controls.ControlTemplate.Triggers%2A>를 설정하여 <xref:System.Windows.Controls.GridViewColumnHeader> <xref:System.Windows.Style>을 수정할 수 있습니다.  이 <xref:System.Windows.Controls.ControlTemplate.Triggers%2A>는 <xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A> 속성 값이 `true`이고 <xref:System.Windows.Controls.GridViewColumnHeader.Role%2A> 속성 값이 <xref:System.Windows.Controls.GridViewColumnHeaderRole>일 때 적용됩니다.  
  
 마우스가 <xref:System.Windows.Controls.GridViewColumnHeader>에 있을 때 사용자가 마우스 버튼을 누르고 있으면 <xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A> 속성 값이 `true`로 변경됩니다.  마찬가지로 사용자가 끌기 작업을 시작하면 <xref:System.Windows.Controls.GridViewColumnHeader.Role%2A> 속성이 <xref:System.Windows.Controls.GridViewColumnHeaderRole>으로 변경됩니다.  
  
 다음 예제에서는 <xref:System.Windows.Controls.ControlTemplate.Triggers%2A>를 설정하여 사용자가 열을 새 위치로 끌어 올 때 원래 머리글과 부동 머리글의 <xref:System.Windows.Controls.Control.Foreground%2A> 및 <xref:System.Windows.Controls.Control.Background%2A> 색을 변경하는 방법을 보여 줍니다.  
  
 [!code-xml[ListViewHeaderRoleStyle#GVCHControlTemplateStart](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#gvchcontroltemplatestart)]  
[!code-xml[ListViewHeaderRoleStyle#ControlTemplateTriggersStart](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#controltemplatetriggersstart)]  
[!code-xml[ListViewHeaderRoleStyle#IsPressed](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#ispressed)]  
[!code-xml[ListViewHeaderRoleStyle#Floating](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#floating)]  
[!code-xml[ListViewHeaderRoleStyle#ControlTemplateTriggersEnd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#controltemplatetriggersend)]  
[!code-xml[ListViewHeaderRoleStyle#GVCHControlTemplateEnd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#gvchcontroltemplateend)]  
  
## 참고 항목  
 <xref:System.Windows.Controls.GridViewColumnHeader>   
 <xref:System.Windows.Controls.GridViewColumnHeaderRole>   
 <xref:System.Windows.Controls.ListView>   
 <xref:System.Windows.Controls.GridView>   
 [방법 항목](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)   
 [ListView 개요](../../../../docs/framework/wpf/controls/listview-overview.md)   
 [GridView 개요](../../../../docs/framework/wpf/controls/gridview-overview.md)