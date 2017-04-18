---
title: "방법: 프로그래밍 방식으로 TextWrapping 속성 변경 | Microsoft Docs"
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
  - "문서, 프로그래밍 방식으로 TextWrapping 속성 변경"
  - "TextWrapping 속성, 프로그래밍 방식으로 변경"
ms.assetid: 30d25554-4c82-4df9-a8d6-35683a4a13bb
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# 방법: 프로그래밍 방식으로 TextWrapping 속성 변경
## 예제  
 다음 코드 예제에서는 <xref:System.Windows.Controls.TextBlock.TextWrapping%2A> 속성의 값을 프로그래밍 방식으로 변경하는 방법을 보여 줍니다.  
  
 세 개의 <xref:System.Windows.Controls.Button> 요소가 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]의 <xref:System.Windows.Controls.StackPanel> 요소 내에 배치됩니다. <xref:System.Windows.Controls.Button>의 각 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 이벤트는 코드에서 이벤트 처리기와 대응합니다.  이벤트 처리기는 단추를 클릭할 때 `txt2`에 적용할 <xref:System.Windows.Controls.TextBlock.TextWrapping%2A> 값과 동일한 이름을 사용합니다.  또한 `txt1`의 텍스트\([!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]에 표시되지 않은 <xref:System.Windows.Controls.TextBlock>\)가 속성의 변경을 나타내기 위해 업데이트됩니다.  
  
 [!code-xml[TextWrapProperty#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextWrapProperty/VisualBasic/Pane1.xaml#1)]  
  
 [!code-csharp[TextWrapProperty#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextWrapProperty/CSharp/Window1.xaml.cs#2)]
 [!code-vb[TextWrapProperty#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextWrapProperty/VisualBasic/Pane1.xaml.vb#2)]  
  
## 참고 항목  
 <xref:System.Windows.Controls.TextBlock.TextWrapping%2A>   
 <xref:System.Windows.TextWrapping>