---
title: "방법: 컨트롤의 배경에 텍스트 그리기 | Microsoft Docs"
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
  - "배경, 텍스트 그리기"
  - "컨트롤, 배경에 텍스트 그리기"
  - "그리기, 컨트롤 배경에 텍스트"
  - "텍스트, 컨트롤 배경에 그리기"
  - "입력 체계, 컨트롤 배경에 텍스트 그리기"
ms.assetid: 686d8fba-f61c-4974-a871-c635d67a7f69
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# 방법: 컨트롤의 배경에 텍스트 그리기
텍스트 문자열을 <xref:System.Windows.Media.FormattedText> 개체로 변환한 다음 개체를 컨트롤의 <xref:System.Windows.Media.DrawingContext>에 그려서 컨트롤의 배경에 직접 텍스트를 그릴 수 있습니다.  또한 <xref:System.Windows.Controls.Canvas> 및 <xref:System.Windows.Controls.StackPanel>처럼 <xref:System.Windows.Controls.Panel>에서 파생된 개체의 배경에 그리기 위해 이 방법을 사용할 수 있습니다.  
  
 ![텍스트를 배경으로 표시하는 컨트롤](../../../../docs/framework/wpf/advanced/media/drawtext2background01.png "DrawText2Background01")  
사용자 지정 텍스트 배경이 있는 컨트롤의 예  
  
## 예제  
 컨트롤의 배경에 그리려면 새 <xref:System.Windows.Media.DrawingBrush> 개체를 만들고 변환된 텍스트를 개체의 <xref:System.Windows.Media.DrawingContext>에 그리십시오.  그런 다음 새 <xref:System.Windows.Media.DrawingBrush>를 컨트롤의 배경 속성에 할당합니다.  
  
 다음 코드 예제에서는 <xref:System.Windows.Media.FormattedText> 개체를 만들고 <xref:System.Windows.Controls.Label> 및 <xref:System.Windows.Controls.Button> 개체의 배경에 그리는 방법을 보여 줍니다.  
  
 [!code-csharp[DrawTextToControlBackground#DrawTextToControlBackground1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawTextToControlBackground/CSHARP/Window1.xaml.cs#drawtexttocontrolbackground1)]  
  
## 참고 항목  
 <xref:System.Windows.Media.FormattedText>   
 [서식 있는 텍스트 그리기](../../../../docs/framework/wpf/advanced/drawing-formatted-text.md)