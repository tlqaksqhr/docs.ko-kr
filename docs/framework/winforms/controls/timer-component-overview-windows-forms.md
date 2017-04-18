---
title: "Timer 구성 요소 개요(Windows Forms) | Microsoft Docs"
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
  - "Timer"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Timer 구성 요소[Windows Forms], Timer 구성 요소 정보"
  - "타이머, 타이머 정보"
ms.assetid: e672c05b-a8b6-4b26-9e4d-9223aa9e3873
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Timer 구성 요소 개요(Windows Forms)
Windows Forms <xref:System.Windows.Forms.Timer>는 정기적으로 이벤트를 발생시키는 구성 요소입니다.  이 구성 요소는 Windows Forms 환경에서 사용하도록 되어 있습니다.  서버 환경에 적합한 타이머가 필요한 경우에는 [Introduction to Server\-Based Timers](http://msdn.microsoft.com/ko-kr/adc0bc0a-a519-4812-bafc-fb9d1a5801fc)를 참조하십시오.  
  
## 주요 속성, 메서드 및 이벤트  
 간격의 길이는 <xref:System.Windows.Forms.Timer.Interval%2A> 속성에서 밀리초 단위의 값으로 정의합니다.  구성 요소가 활성화되면 매 간격마다 <xref:System.Windows.Forms.Timer.Tick> 이벤트가 발생합니다.  실행될 코드를 여기에 추가합니다.  자세한 내용은 [방법: Windows Forms Timer 구성 요소를 사용하여 설정된 간격마다 프로시저 실행](../../../../docs/framework/winforms/controls/run-procedures-at-set-intervals-with-wf-timer-component.md)를 참조하십시오.  <xref:System.Windows.Forms.Timer> 구성 요소의 주요 메서드는 타이머를 설정 및 해제하는 <xref:System.Windows.Forms.Timer.Start%2A> 및 <xref:System.Windows.Forms.Timer.Stop%2A>입니다.  타이머가 꺼진 후에는 다시 설정되며 <xref:System.Windows.Forms.Timer> 구성 요소를 일시적으로 중지시킬 수는 없습니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.Timer>   
 [Timer 구성 요소](../../../../docs/framework/winforms/controls/timer-component-windows-forms.md)   
 [Windows Forms Timer 구성 요소의 Interval 속성에 대한 제한 사항](../../../../docs/framework/winforms/controls/limitations-of-the-timer-component-interval-property.md)