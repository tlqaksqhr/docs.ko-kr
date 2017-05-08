---
title: "방법: 이미지가 있는 단추 만들기 | Microsoft Docs"
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
  - "Button 컨트롤[WPF], 만들기"
ms.assetid: 607a193c-4098-4dd8-8dc0-51256cec2020
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# 방법: 이미지가 있는 단추 만들기
이 예제에서는 <xref:System.Windows.Controls.Button>에 이미지를 포함하는 방법을 보여 줍니다.  
  
## 예제  
 다음 예제에서는 두 개의 <xref:System.Windows.Controls.Button> 컨트롤을 만듭니다.  한 <xref:System.Windows.Controls.Button>에는 텍스트가 포함되고 다른 단추에는 이미지가 포함됩니다.  이미지를 data라는 폴더에 있습니다. 이 폴더는 예제에서 프로젝트 폴더의 하위 폴더입니다.  사용자가 이미지가 있는 <xref:System.Windows.Controls.Button>을 클릭하면 다른 <xref:System.Windows.Controls.Button>의 배경과 텍스트가 변경됩니다.  
  
 이 예제에서는 태그를 사용하여 <xref:System.Windows.Controls.Button> 컨트롤을 만들고 코드를 사용하여 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 이벤트 처리기를 작성합니다.  
  
 [!code-xml[BtnColor#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BtnColor/CSharp/Pane1.xaml#4)]  
  
 [!code-csharp[BtnColor#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BtnColor/CSharp/Pane1.xaml.cs#6)]
 [!code-vb[BtnColor#6](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BtnColor/VisualBasic/Pane1.xaml.vb#6)]  
  
## 참고 항목  
 [컨트롤](../../../../docs/framework/wpf/controls/index.md)   
 [컨트롤 라이브러리](../../../../docs/framework/wpf/controls/control-library.md)