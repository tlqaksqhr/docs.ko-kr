---
title: "방법: BetweenShowDelay 속성 사용 | Microsoft Docs"
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
  - "BetweenShowDelay 시간 속성"
  - "ToolTip 컨트롤, BetweenShowDelay 시간 속성"
ms.assetid: 984ea76d-f2a2-4326-a02e-f97ec3d036d6
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# 방법: BetweenShowDelay 속성 사용
이 예제에서는 <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> 시간 속성을 사용하여 사용자가 한 도구 설명에서 다른 도구 설명으로 마우스 포인터를 이동할 때 지연 없이 도구 설명이 빠르게 나타나도록 설정하는 방법을 보여 줍니다.  
  
## 예제  
 다음 예제에서는 두 <xref:System.Windows.Shapes.Ellipse> 컨트롤의 도구 설명 모두에 대해 <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A> 속성은 1초\(1000밀리초\)로 설정하고 <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A>는 2초\(2000밀리초\)로 설정합니다.  Ellipse 중 하나에 대한 도구 설명을 표시한 다음 2초 내에 마우스 포인터를 다른 Ellipse로 이동하여 그 위에 계속 두면 두 번째 Ellipse의 도구 설명이 즉시 표시됩니다.  
  
 다음과 같은 시나리오 중 하나에서 <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A>를 적용하면 두 번째 Ellipse의 도구 설명이 1초 후에 나타납니다.  
  
-   두 번째 단추로 이동하는 데 걸린 시간이 2초 이상인 경우  
  
-   첫 번째 Ellipse에 대한 시간 간격의 시작 부분에서 도구 설명이 표시되지 않는 경우  
  
 [!code-xml[ToolTipService#ToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#tooltip)]  
[!code-xml[ToolTipService#NoToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#notooltip)]  
  
## 참고 항목  
 <xref:System.Windows.Controls.ToolTip>   
 <xref:System.Windows.Controls.ToolTipService>   
 [방법 항목](../../../../docs/framework/wpf/controls/tooltip-how-to-topics.md)   
 [도구 설명 개요](../../../../docs/framework/wpf/controls/tooltip-overview.md)