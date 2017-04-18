---
title: "방법: Loaded 이벤트 처리 | Microsoft Docs"
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
  - "이벤트, 로드됨"
  - "Loaded 이벤트"
  - "XAML, Loaded 이벤트"
ms.assetid: 0cf8d003-8441-4df4-807a-6db09347e829
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# 방법: Loaded 이벤트 처리
이 예제에서는 <xref:System.Windows.FrameworkElement.Loaded?displayProperty=fullName> 이벤트를 처리하는 방법과 이 이벤트를 처리하는 적절한 시나리오를 보여 줍니다.  페이지가 로드되면 처리기가 <xref:System.Windows.Controls.Button>을 만듭니다.  
  
## 예제  
 다음 예제에서는 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 및 코드 숨김 파일을 함께 사용합니다.  
  
 [!code-xml[FELoaded#XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FELoaded/CSharp/default.xaml#xaml)]  
  
 [!code-csharp[FELoaded#Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FELoaded/CSharp/default.xaml.cs#handler)]
 [!code-vb[FELoaded#Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FELoaded/VisualBasic/default.xaml.vb#handler)]  
  
## 참고 항목  
 <xref:System.Windows.FrameworkElement>   
 [개체 수명 이벤트](../../../../docs/framework/wpf/advanced/object-lifetime-events.md)   
 [라우트된 이벤트 개요](../../../../docs/framework/wpf/advanced/routed-events-overview.md)   
 [방법 항목](../../../../docs/framework/wpf/advanced/base-elements-how-to-topics.md)