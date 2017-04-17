---
title: "Splitter 컨트롤 개요(Windows Forms) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "Splitter"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Splitter 컨트롤[Windows Forms], Splitter 컨트롤 정보"
ms.assetid: e2b6ab83-dfdd-40ec-9762-850702c82dcb
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Splitter 컨트롤 개요(Windows Forms)
> [!IMPORTANT]
>  <xref:System.Windows.Forms.SplitContainer>는 이전 버전의 <xref:System.Windows.Forms.Splitter> 컨트롤에 새로운 기능이 추가된 것으로, 이전 컨트롤을 대체합니다. 그러나 이전 버전과의 호환성 및 앞으로의 사용 가능성을 고려하여 <xref:System.Windows.Forms.Splitter>를 유지하도록 선택할 수 있습니다.  
  
 Windows Forms <xref:System.Windows.Forms.Splitter> 컨트롤은 런타임에 도킹된 컨트롤의 크기를 조정하는 데 사용됩니다.  <xref:System.Windows.Forms.Splitter> 컨트롤은 데이터 창에 표시되는 정보의 너비가 수시로 변하는 Windows 탐색기와 같이 제공할 데이터의 길이가 변하는 컨트롤을 가진 폼에 자주 사용됩니다.  
  
## 분할자 컨트롤 사용  
 분할자 컨트롤로 크기를 조정할 수 있는 컨트롤의 도킹되지 않은 가장자리에 마우스 포인터를 가져가면 컨트롤의 크기를 조정할 수 있도록 포인터 모양이 변경됩니다.  분할자 컨트롤을 사용하면 분할자 컨트롤의 바로 앞에 도킹된 컨트롤의 크기를 조정할 수 있습니다.  따라서 런타임에서 도킹된 컨트롤의 크기를 조정하려면 컨테이너의 한쪽 가장자리에 크기 조정할 컨트롤을 도킹한 다음 분할자 컨트롤을 해당 컨테이너의 같은 쪽에 도킹합니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.SplitContainer>   
 [방법: Windows Forms에 컨트롤 도킹](../../../../docs/framework/winforms/controls/how-to-dock-controls-on-windows-forms.md)   
 [Windows Forms에 사용할 수 있는 컨트롤](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)