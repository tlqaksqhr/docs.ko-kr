---
title: "방법: ScrollBar의 Thumb 크기 사용자 지정 | Microsoft Docs"
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
  - "엄지 단추 크기 사용자 지정"
  - "ScrollBar 컨트롤"
  - "엄지 단추 크기"
ms.assetid: fa32b866-5ca1-4e73-85e7-2ac64b80d194
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# 방법: ScrollBar의 Thumb 크기 사용자 지정
이 항목에서는 <xref:System.Windows.Controls.Primitives.ScrollBar>의 <xref:System.Windows.Controls.Primitives.Thumb>을 고정 크기로 설정하는 방법과 <xref:System.Windows.Controls.Primitives.ScrollBar>의 <xref:System.Windows.Controls.Primitives.Thumb>에 대한 최소 크기를 지정하는 방법을 설명합니다.  
  
## 예제  
  
## 설명  
 다음 예제에서는 고정 크기의 <xref:System.Windows.Controls.Primitives.Thumb>을 갖는 <xref:System.Windows.Controls.Primitives.ScrollBar>를 만듭니다.  예제에서는 <xref:System.Windows.Controls.Primitives.Thumb>의 <xref:System.Windows.Controls.Primitives.Track.ViewportSize%2A> 속성을 <xref:System.Double.NaN>으로 설정하고 <xref:System.Windows.Controls.Primitives.Thumb>의 높이를 설정합니다.  고정 너비의 <xref:System.Windows.Controls.Primitives.Thumb>이 있는 가로 <xref:System.Windows.Controls.Primitives.ScrollBar>를 만들려면 <xref:System.Windows.Controls.Primitives.Thumb>의 너비를 설정합니다.  
  
## 코드  
 [!code-xml[ScrollBarCustomThumbSize#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ScrollBarCustomThumbSize/CS/Window1.xaml#1)]  
  
## 설명  
 다음 예제에서는 최소 크기의 <xref:System.Windows.Controls.Primitives.Thumb>을 갖는 <xref:System.Windows.Controls.Primitives.ScrollBar>를 만듭니다.  예제에서는 <xref:System.Windows.SystemParameters.VerticalScrollBarButtonHeightKey%2A>의 값을 설정합니다.  최소 너비의 <xref:System.Windows.Controls.Primitives.Thumb>이 있는 가로 <xref:System.Windows.Controls.Primitives.ScrollBar>를 만들려면 <xref:System.Windows.SystemParameters.HorizontalScrollBarButtonWidthKey%2A>를 설정합니다.  
  
## 코드  
 [!code-xml[ScrollBarCustomThumbSize#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ScrollBarCustomThumbSize/CS/Window1.xaml#2)]  
  
## 참고 항목  
 [ScrollBar 스타일 및 템플릿](../../../../docs/framework/wpf/controls/scrollbar-styles-and-templates.md)