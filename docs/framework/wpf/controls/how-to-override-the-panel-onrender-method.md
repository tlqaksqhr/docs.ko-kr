---
title: "방법: Panel의 OnRender 메서드 재정의 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "overriding OnRender method"
  - "Panel control, overriding OnRender method"
  - "OnRender method"
  - "controls, Panel, overriding OnRender method"
helpviewer_keywords: 
  - "OnRender 메서드, 재정의"
  - "Panel 컨트롤의 OnRender 메서드 재정의"
  - "Panel 컨트롤, OnRender 메서드 재정의"
ms.assetid: 57397834-a085-4e36-90ab-416fad98f341
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# 방법: Panel의 OnRender 메서드 재정의
이 예제에서는 레이아웃 요소에 사용자 지정 그래픽 효과를 추가하기 위해 <xref:System.Windows.Controls.Panel>의 <xref:System.Windows.Controls.Panel.OnRender%2A> 메서드를 재정의하는 방법을 보여 줍니다.  
  
## 예제  
 렌더링된 패널 요소에 그래픽 효과를 추가하려면 <xref:System.Windows.Controls.Panel.OnRender%2A> 메서드를 사용합니다.  예를 들어 이 메서드를 통해 사용자 지정 테두리나 배경 효과를 추가할 수 있습니다.  <xref:System.Windows.Media.DrawingContext> 개체가 인수로 전달되어 도형, 텍스트, 이미지 또는 동영상을 그리는 메서드를 제공합니다.  따라서 이 메서드는 Panel 개체를 사용자 지정하려는 경우 유용합니다.  
  
 [!code-csharp[LightWeightCustomPanel#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LightWeightCustomPanel/CSharp/OffsetPanel.cs#1)]
 [!code-vb[LightWeightCustomPanel#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/LightWeightCustomPanel/visualbasic/offsetpanel.vb#1)]  
  
## 참고 항목  
 <xref:System.Windows.Controls.Panel>   
 [Panel 개요](../../../../docs/framework/wpf/controls/panels-overview.md)   
 [Custom Radial Panel 샘플](http://go.microsoft.com/fwlink/?LinkID=159982)   
 [방법 항목](../../../../docs/framework/wpf/controls/panel-how-to-topics.md)