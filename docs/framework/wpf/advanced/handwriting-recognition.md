---
title: "필기 인식 | Microsoft Docs"
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
  - "필기 인식"
  - "필기 인식"
ms.assetid: f4e8576d-e731-4bac-9818-22e2ae636636
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# 필기 인식
이 단원에서는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 플랫폼에서 디지털 잉크에 관련된 인식의 기본적인 사항에 대해 설명합니다.  
  
## 인식 솔루션  
 다음 예제에서는 <xref:System.Windows.Ink.InkAnalyzer>를 사용하여 잉크를 인식하는 방법을 보여 줍니다.  
  
> [!NOTE]
>  이 샘플을 사용하려면 시스템에 필기 인식 기능이 설치되어 있어야 합니다.  
  
 Visual Studio 2005에서 InkRecognition이라고 하는 새 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램 프로젝트를 만듭니다.  Window1.xaml 파일의 내용을 다음 XAML 코드로 바꿉니다.  이 코드는 응용 프로그램의 사용자 인터페이스를 렌더링합니다.  
  
 [!code-xml[InkRecognition#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkRecognition/CSharp/Window1.xaml#1)]  
  
 \\Program Files\\Reference Assemblies\\Microsoft\\Tablet PC\\v1.7에 있는 WPF 잉크 분석 어셈블리, IAWinFX.dll, IACore.dll 및 IALoader.dll에 대한 참조를 추가합니다.  코드 숨김 파일의 내용을 다음 코드로 바꿉니다.  
  
 [!code-csharp[InkRecognition#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkRecognition/CSharp/Window1.xaml.cs#2)]
 [!code-vb[InkRecognition#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InkRecognition/VisualBasic/Window1.xaml.vb#2)]  
  
## 참고 항목  
 <xref:System.Windows.Ink.InkAnalyzer>   
 <xref:System.Windows.Ink.AnalysisStatus>   
 <xref:System.Windows.Controls.InkCanvas>