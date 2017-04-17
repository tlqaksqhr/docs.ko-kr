---
title: "방법: 요소 및 컨트롤의 여백 설정 | Microsoft Docs"
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
  - "Margin 속성, 설정"
  - "속성, Margin 속성"
  - "설정, Margin 속성"
ms.assetid: 70ebee01-6f87-4352-8dd4-402c65eaaed6
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# 방법: 요소 및 컨트롤의 여백 설정
이 예제에서는 코드 숨김의 여백에 대한 기존 속성 값을 변경하여 <xref:System.Windows.FrameworkElement.Margin%2A> 속성을 설정하는 방법을 설명합니다.  <xref:System.Windows.FrameworkElement.Margin%2A> 속성은 <xref:System.Windows.FrameworkElement> 기본 요소의 속성이며, 따라서 다양한 컨트롤 및 기타 요소에서 상속합니다.  
  
 이 예제는 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]로 작성되었으며 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]에서 참조하는 코드 숨김 파일이 있습니다.  코드 숨김은 [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)] 및 [!INCLUDE[TLA#tla_visualb](../../../../includes/tlasharptla-visualb-md.md)] 버전에서 모두 표시됩니다.  
  
## 예제  
 [!code-xml[FEMarginProgrammatic#XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FEMarginProgrammatic/CSharp/default.xaml#xaml)]  
  
 [!code-csharp[FEMarginProgrammatic#Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FEMarginProgrammatic/CSharp/default.xaml.cs#handler)]
 [!code-vb[FEMarginProgrammatic#Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FEMarginProgrammatic/VisualBasic/default.xaml.vb#handler)]