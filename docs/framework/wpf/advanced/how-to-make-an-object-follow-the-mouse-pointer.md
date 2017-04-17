---
title: "방법: 마우스 포인터를 따라 개체 이동 | Microsoft Docs"
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
  - "커서(마우스 포인터), 개체가 따라오도록 만들기"
  - "마우스 포인터(커서) 따라가기"
  - "마우스 포인터(커서), 개체가 따라오도록 만들기"
ms.assetid: 50b20415-14bc-405c-baf3-2fb254fffde3
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# 방법: 마우스 포인터를 따라 개체 이동
이 예제에서는 화면 위에서 마우스 포인터를 이동할 때 개체의 크기를 변경하는 방법을 보여 줍니다.  
  
 예제에는 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]를 만드는 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 파일과 이벤트 처리기를 만드는 코드 숨김 파일이 포함됩니다.  
  
## 예제  
 다음 [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)]에서는 <xref:System.Windows.Controls.StackPanel> 내부에 <xref:System.Windows.Shapes.Ellipse>로 구성된 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]를 만들고 <xref:System.Windows.UIElement.MouseMove> 이벤트에 대한 이벤트 처리기를 연결합니다.  
  
 [!code-xml[mouseMoveWithPointer#MouseMoveWithPointerXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/mouseMoveWithPointer/CSharp/Window1.xaml#mousemovewithpointerxaml)]  
  
 다음 코드 숨김에서는 <xref:System.Windows.UIElement.MouseMove> 이벤트 처리기를 만듭니다.  마우스 포인터를 이동하면 <xref:System.Windows.Shapes.Ellipse>의 높이와 너비가 증가하거나 감소합니다.  
  
 [!code-csharp[mouseMoveWithPointer#MouseMovePointerGetPosition](../../../../samples/snippets/csharp/VS_Snippets_Wpf/mouseMoveWithPointer/CSharp/Window1.xaml.cs#mousemovepointergetposition)]
 [!code-vb[mouseMoveWithPointer#MouseMovePointerGetPosition](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/mouseMoveWithPointer/VisualBasic/Window1.xaml.vb#mousemovepointergetposition)]  
  
## 참고 항목  
 [입력 개요](../../../../docs/framework/wpf/advanced/input-overview.md)