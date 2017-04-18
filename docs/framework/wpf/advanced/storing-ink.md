---
title: "잉크 저장 | Microsoft Docs"
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
  - "ISF(Serialize된 잉크 형식)"
  - "잉크, 저장"
  - "ISF(Serialize된 잉크 형식)"
  - "잉크 검색"
  - "잉크 저장"
ms.assetid: a3f6d16b-d682-4680-9965-907332b4d2b8
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# 잉크 저장
<xref:System.Windows.Ink.StrokeCollection.Save%2A> 메서드를 사용하면 잉크를 ISF\(Serialize된 잉크 형식\)로 저장할 수 있습니다.  <xref:System.Windows.Ink.StrokeCollection> 클래스의 생성자는 잉크 데이터를 읽을 수 있도록 합니다.  
  
## 잉크 저장소 및 검색  
 이 단원에서는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 플랫폼에서 잉크를 저장하고 검색하는 방법에 대해 설명합니다.  
  
 다음 예제에서는 사용자에게 파일 저장 대화 상자를 표시하고 <xref:System.Windows.Controls.InkCanvas>의 잉크를 파일로 저장할 수 있는 단추 클릭 이벤트 처리기를 구현합니다.  
  
 [!code-csharp[DigitalInkTopics#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#12)]
 [!code-vb[DigitalInkTopics#12](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#12)]  
  
 다음 예제에서는 사용자에게 파일 열기 대화 상자를 표시하고 파일에서 <xref:System.Windows.Controls.InkCanvas> 요소로 잉크를 읽어들이는 단추 클릭 이벤트 처리기를 구현합니다.  
  
 [!code-csharp[DigitalInkTopics#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#13)]
 [!code-vb[DigitalInkTopics#13](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#13)]  
  
## 참고 항목  
 <xref:System.Windows.Controls.InkCanvas>   
 [Windows Presentation Foundation](../../../../docs/framework/wpf/index.md)