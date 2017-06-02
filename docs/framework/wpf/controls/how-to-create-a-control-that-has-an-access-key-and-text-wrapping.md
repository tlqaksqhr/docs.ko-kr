---
title: "방법: 선택키가 있고 텍스트 줄 바꿈을 사용하는 컨트롤 만들기 | Microsoft Docs"
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
  - "선택키, 컨트롤"
  - "컨트롤, 선택키"
  - "컨트롤, 텍스트 줄 바꿈"
  - "keys, 컨트롤"
  - "텍스트 줄 바꿈"
  - "텍스트 래핑"
ms.assetid: 205099d9-2551-4302-a25e-a15af9f67e04
caps.latest.revision: 22
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 19
---
# 방법: 선택키가 있고 텍스트 줄 바꿈을 사용하는 컨트롤 만들기
이 예제에서는 [선택키](GTMT)가 있고 텍스트 줄 바꿈을 지원하는 컨트롤을 만드는 방법을 보여 줍니다.  또한 <xref:System.Windows.Controls.Label> 컨트롤을 사용하여 이러한 개념을 설명합니다.  
  
## 예제  
 **레이블에 텍스트 줄 바꿈 추가**  
  
 <xref:System.Windows.Controls.Label> 컨트롤은 텍스트 줄 바꿈을 지원하지 않습니다.  여러 줄로 줄 바꿈되는 레이블이 필요한 경우 텍스트 줄 바꿈을 지원하는 다른 요소를 중첩시키고 해당 요소를 레이블 내부에 배치할 수 있습니다.  다음 예제에서는 <xref:System.Windows.Controls.TextBlock>을 사용하여 여러 줄의 텍스트로 줄 바꿈되는 레이블을 만드는 방법을 보여 줍니다.  
  
 <!-- TODO: review snippet reference [!code-xml[Label#5](../../../../samples/snippets/xaml/VS_Snippets_Wpf/Label/XAML/Pane1.xaml#5)]  -->
 <!-- TODO: review snippet reference [!code-xml[Label#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Label/CS/Pane1.xaml#5)]  -->  
  
 **레이블에 선택키 및 텍스트 줄 바꿈 추가**  
  
 선택키\(니모닉\)가 있는 <xref:System.Windows.Controls.Label>이 필요한 경우 <xref:System.Windows.Controls.Label> 내부에 있는 <xref:System.Windows.Controls.AccessText> 요소를 사용합니다.  
  
 <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.RadioButton>, <xref:System.Windows.Controls.CheckBox>, <xref:System.Windows.Controls.MenuItem>, <xref:System.Windows.Controls.TabItem>, <xref:System.Windows.Controls.Expander> 및 <xref:System.Windows.Controls.GroupBox> 같은 컨트롤에는 기본 컨트롤 템플릿이 있습니다.  이러한 템플릿에는 <xref:System.Windows.Controls.ContentPresenter>가 포함됩니다.  <xref:System.Windows.Controls.ContentPresenter>에서 설정할 수 있는 속성 중 하나가 <xref:System.Windows.Controls.ContentPresenter.RecognizesAccessKey%2A>\="true"입니다. 이 속성을 사용하면 컨트롤에 대한 선택키를 지정할 수 있습니다.  
  
 다음 예제에서는 선택키가 있고 텍스트 줄 바꿈을 지원하는 <xref:System.Windows.Controls.Label>을 만드는 방법을 보여 줍니다.  텍스트 줄 바꿈을 사용하기 위해 예제에서는 <xref:System.Windows.Controls.AccessText.TextWrapping%2A> 속성을 설정하고 밑줄 문자를 사용하여 선택키를 지정합니다.  이 경우 밑줄 문자 바로 다음에 오는 문자가 선택키가 됩니다.  
  
 <!-- TODO: review snippet reference [!code-xml[Label#4](../../../../samples/snippets/xaml/VS_Snippets_Wpf/Label/XAML/Pane1.xaml#4)]  -->
 <!-- TODO: review snippet reference [!code-xml[Label#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Label/CS/Pane1.xaml#4)]  -->  
  
## 참고 항목  
 [How to: Set the Target Property of a Label](http://msdn.microsoft.com/ko-kr/b24c6977-ebcb-4855-a9bb-3fd4435af8f8)