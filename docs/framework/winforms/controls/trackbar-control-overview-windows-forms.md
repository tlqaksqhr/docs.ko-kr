---
title: "TrackBar 컨트롤 개요(Windows Forms) | Microsoft Docs"
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
  - "TrackBar"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "슬라이더 컨트롤, 슬라이더 컨트롤 정보"
  - "슬라이더, 슬라이더 정보"
  - "TrackBar 컨트롤[Windows Forms], TrackBar 컨트롤 정보"
ms.assetid: 95910ecb-8a4c-4776-89fa-206c89ed6973
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# TrackBar 컨트롤 개요(Windows Forms)
"slider" 컨트롤이라고도 하는 Windows Forms <xref:System.Windows.Forms.TrackBar> 컨트롤은 많은 양의 정보를 탐색하거나 숫자 설정을 시각적으로 조정하는 데 사용됩니다.  <xref:System.Windows.Forms.TrackBar> 컨트롤은 슬라이더라고 하는 엄지 단추 부분과 눈금 부분으로 구성되어 있습니다.  엄지 단추는 조정할 수 있는 부분이며  엄지 단추의 위치는 <xref:System.Windows.Forms.TrackBar.Value%2A> 속성으로 결정됩니다.  눈금은 일정한 간격을 두고 배치되어 있는 시각적 표시기입니다.  트랙 표시줄은 지정된 증가값만큼 이동하며 가로 또는 세로 방향으로 맞출 수 있습니다.  예를 들어 트랙 표시줄을 사용하여 커서 깜박임 속도나 마우스 속도를 제어할 수 있습니다.  
  
## 키 속성  
 <xref:System.Windows.Forms.TrackBar> 컨트롤의 주요 속성은 <xref:System.Windows.Forms.TrackBar.Value%2A>, <xref:System.Windows.Forms.TrackBar.TickFrequency%2A>, <xref:System.Windows.Forms.TrackBar.Minimum%2A> 및 <xref:System.Windows.Forms.TrackBar.Maximum%2A>입니다.  <xref:System.Windows.Forms.TrackBar.TickFrequency%2A>는 눈금 사이의 간격을 말하고  <xref:System.Windows.Forms.TrackBar.Minimum%2A>과 <xref:System.Windows.Forms.TrackBar.Maximum%2A>은 트랙 표시줄에 나타낼 수 있는 최소값\/최대값을 말합니다.  
  
 이 외에 <xref:System.Windows.Forms.TrackBar.SmallChange%2A>와 <xref:System.Windows.Forms.TrackBar.LargeChange%2A> 속성도 중요합니다.  <xref:System.Windows.Forms.TrackBar.SmallChange%2A> 속성의 값은 왼쪽 화살표 또는 오른쪽 화살표 키를 누를 때 엄지 단추가 이동하는 위치를 나타내는 숫자이고  <xref:System.Windows.Forms.TrackBar.LargeChange%2A> 속성의 값은 Page Up 또는 Page Down 키를 누르거나 엄지 단추의 한 쪽에서 트랙 표시줄에 마우스를 대고 클릭할 때 엄지 단추가 이동하는 위치를 나타내는 숫자입니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.TrackBar>   
 [TrackBar 컨트롤](../../../../docs/framework/winforms/controls/trackbar-control-windows-forms.md)