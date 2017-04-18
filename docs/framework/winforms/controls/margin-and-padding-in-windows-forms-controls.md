---
title: "Windows Forms 컨트롤의 여백 및 안쪽 여백 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "레이아웃[Windows Forms], 여백 및 안쪽 여백"
  - "Margin 속성[Windows Forms]"
  - "Padding 속성[Windows Forms]"
  - "Windows Forms, 레이아웃"
ms.assetid: 3781b5a1-3085-4072-bed0-44670c23ffdc
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# Windows Forms 컨트롤의 여백 및 안쪽 여백
폼의 정확한 컨트롤 배치는 많은 응용 프로그램에서 우선 순위가 높습니다.  <xref:System.Windows.Forms?displayProperty=fullName> 네임스페이스는 이 목적을 위한 다양한 레이아웃 기능을 제공합니다.  가장 중요한 두 가지 기능은 <xref:System.Windows.Forms.Control.Margin%2A> 및 <xref:System.Windows.Forms.Control.Padding%2A> 속성입니다.  
  
 <xref:System.Windows.Forms.Control.Margin%2A> 속성은 다른 컨트롤을 컨트롤의 테두리에서 지정된 거리에 유지하는 컨트롤 주위의 공간을 정의합니다.  
  
 <xref:System.Windows.Forms.Control.Padding%2A> 속성은 컨트롤의 내용\(예: <xref:System.Windows.Forms.Control.Text%2A> 속성의 값\)을 컨트롤의 테두리에서 지정된 거리에 유지하는 컨트롤 내부의 공간을 정의합니다.  
  
 다음 그림에서는 컨트롤의 <xref:System.Windows.Forms.Control.Padding%2A> 및 <xref:System.Windows.Forms.Control.Margin%2A> 속성을 보여 줍니다.  
  
 ![Windows Forms 컨트롤의 여백 및 안쪽 여백](../../../../docs/framework/winforms/controls/media/vs-winformpadmargin.gif "VS\_WinFormPadMargin")  
  
 Visual Studio에서는 디자인 타임에 이 기능을 지원합니다.  [연습: Padding, Margins 및 AutoSize 속성을 사용하여 Windows Forms 컨트롤 레이아웃](http://msdn.microsoft.com/library/3z3f9e8b\(v=vs.110\))을 참조하세요.  
  
## 참고 항목  
 <xref:System.Windows.Forms.Control.AutoSize%2A>   
 <xref:System.Windows.Forms.Control.Margin%2A>   
 <xref:System.Windows.Forms.Control.Padding%2A>   
 <xref:System.Windows.Forms.Control.LayoutEngine%2A>   
 <xref:System.Windows.Forms.TableLayoutPanel>   
 <xref:System.Windows.Forms.FlowLayoutPanel>