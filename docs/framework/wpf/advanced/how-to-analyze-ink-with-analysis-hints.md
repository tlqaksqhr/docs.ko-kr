---
title: "방법: 분석 힌트를 사용하여 잉크 분석 | Microsoft Docs"
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
  - "AnalysisHintNode 개체"
  - "잉크 분석"
  - "잉크, AnalysisHintNode 개체"
  - "잉크, 분석"
ms.assetid: d4421ed4-77f5-4640-829e-9f1de50b2ff2
caps.latest.revision: 4
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 4
---
# 방법: 분석 힌트를 사용하여 잉크 분석
<xref:System.Windows.Ink.AnalysisHintNode>는 자신이 첨부되어 있는 <xref:System.Windows.Ink.InkAnalyzer>에 대한 힌트를 제공합니다.  힌트는 <xref:System.Windows.Ink.AnalysisHintNode>의 <xref:System.Windows.Ink.ContextNode.Location%2A> 속성으로 지정된 영역에 적용되며 잉크 분석기에 추가 컨텍스트를 제공하여 인식 정확도를 높여 줍니다.  <xref:System.Windows.Ink.InkAnalyzer>는 힌트 영역 내에서 가져온 잉크를 분석할 때 이 컨텍스트 정보를 적용합니다.  
  
## 예제  
 다음 예제는 잉크 입력을 받는 폼에서 여러 <xref:System.Windows.Ink.AnalysisHintNode> 개체를 사용하는 응용 프로그램입니다.  이 응용 프로그램에서는 <xref:System.Windows.Ink.AnalysisHintNode.Factoid%2A> 속성을 사용하여 폼의 각 항목에 대한 컨텍스트 정보를 제공합니다.  응용 프로그램은 배경 분석을 사용하여 잉크를 분석하고 사용자가 잉크 추가를 멈추면 5초 후 폼에서 모든 잉크를 지웁니다.  
  
 [!code-xml[HowToAnalyzeInk#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToAnalyzeInk/CSharp/FormAnalyzer.xaml#1)]  
  
 [!code-csharp[HowToAnalyzeInk#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToAnalyzeInk/CSharp/FormAnalyzer.xaml.cs#2)]
 [!code-vb[HowToAnalyzeInk#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToAnalyzeInk/VisualBasic/FormAnalyzer.xaml.vb#2)]