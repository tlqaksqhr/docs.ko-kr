---
title: "방법: Enter 키를 누르는 시점 감지 | Microsoft Docs"
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
  - "Enter 키, 검색"
  - "keys, 입력"
ms.assetid: a66f39d2-ef4a-43a5-b454-a4ea0fe88655
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# 방법: Enter 키를 누르는 시점 감지
이 예제에서는 키보드의 <xref:System.Windows.Input.Key> 키를 누르는 시점을 감지하는 방법을 보여 줍니다.  
  
 이 예제는 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 파일과 코드 숨김 파일로 구성됩니다.  
  
## 예제  
 사용자가 <xref:System.Windows.Controls.TextBox>에서 <xref:System.Windows.Input.Key> 키를 누르면 텍스트 상자의 입력이 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]의 다른 영역에 나타납니다.  
  
 다음 [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)]에서는 <xref:System.Windows.Controls.StackPanel>, <xref:System.Windows.Controls.TextBlock> 및 <xref:System.Windows.Controls.TextBox>로 구성된 사용자 인터페이스를 만듭니다.  
  
 [!code-xml[keydown#KeyDownUI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/KeyDown/CSharp/Window1.xaml#keydownui)]  
  
 다음 코드 숨김에서는 <xref:System.Windows.UIElement.KeyDown> 이벤트 처리기를 만듭니다.  사용자가 누른 키가 <xref:System.Windows.Input.Key> 키이면 <xref:System.Windows.Controls.TextBlock>에 메시지가 표시됩니다.  
  
 [!code-csharp[keydown#KeyDownSample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/KeyDown/CSharp/Window1.xaml.cs#keydownsample)]
 [!code-vb[keydown#KeyDownSample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/KeyDown/VisualBasic/Window1.xaml.vb#keydownsample)]  
  
## 참고 항목  
 [입력 개요](../../../../docs/framework/wpf/advanced/input-overview.md)   
 [라우트된 이벤트 개요](../../../../docs/framework/wpf/advanced/routed-events-overview.md)