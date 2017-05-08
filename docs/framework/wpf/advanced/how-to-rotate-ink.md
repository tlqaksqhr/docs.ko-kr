---
title: "방법: 잉크 회전 | Microsoft Docs"
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
  - "잉크, 회전"
  - "잉크 회전"
ms.assetid: fac36cc9-dd01-41ca-9bde-9d33e3790bbe
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# 방법: 잉크 회전
## 예제  
 다음 예제에서는 잉크를 <xref:System.Windows.Controls.InkCanvas>에서 <xref:System.Windows.Controls.InkPresenter>가 포함된 <xref:System.Windows.Controls.Canvas>에 복사합니다.  응용 프로그램은 잉크를 복사할 때 잉크를 시계 방향으로 90도 회전합니다.  
  
 [!code-xml[HowToRotateInk#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToRotateInk/CSharp/Window1.xaml#1)]  
  
 [!code-csharp[HowToRotateInk#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToRotateInk/CSharp/Window1.xaml.cs#2)]  
  
## 예제  
 다음 예제는 <xref:System.Windows.Controls.InkPresenter>에서 스트로크를 회전하는 사용자 지정 <xref:System.Windows.Documents.Adorner>입니다.  
  
 [!code-csharp[AdornerForStrokes#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdornerForStrokes/CSharp/RotatingAdornerForStrokes.cs#1)]
 [!code-vb[AdornerForStrokes#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdornerForStrokes/VisualBasic/RotatingAdornerForStrokes.vb#1)]  
  
 다음 예제는 <xref:System.Windows.Controls.InkPresenter>를 정의하고 잉크로 채우는 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 파일입니다.  `Window_Loaded` 이벤트 처리기는 <xref:System.Windows.Controls.InkPresenter>에 사용자 지정 표시기\(Adorner\)를 추가합니다.  
  
 [!code-xml[AdornerForStrokes#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdornerForStrokes/CSharp/Window1.xaml#2)]  
  
 [!code-csharp[AdornerForStrokes#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdornerForStrokes/CSharp/Window1.xaml.cs#3)]
 [!code-vb[AdornerForStrokes#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdornerForStrokes/VisualBasic/Window1.xaml.vb#3)]