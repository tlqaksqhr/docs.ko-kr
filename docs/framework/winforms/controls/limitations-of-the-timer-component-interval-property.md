---
title: "Windows Forms Timer 구성 요소의 Interval 속성에 대한 제한 사항 | Microsoft Docs"
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
  - "Interval 속성, 제한 사항"
  - "Timer 구성 요소[Windows Forms], Interval 속성 제한 사항"
  - "타이머, 이벤트 간격"
  - "타이머, Windows 기반"
ms.assetid: 7e5fb513-77e7-4046-a8e8-aab94e61ca0f
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Windows Forms Timer 구성 요소의 Interval 속성에 대한 제한 사항
Windows Forms <xref:System.Windows.Forms.Timer> 구성 요소에는 각 타이머 이벤트 사이의 시간을 밀리초 단위로 지정하는 <xref:System.Windows.Forms.Timer.Interval%2A> 속성이 있습니다.  이 구성 요소가 비활성화되어 있지 않으면 타이머는 거의 같은 간격으로 계속 <xref:System.Windows.Forms.Timer.Tick> 이벤트를 받습니다.  
  
 이 구성 요소는 Windows Forms 환경에서 사용하도록 되어 있습니다.  서버 환경에 적합한 타이머가 필요한 경우에는 [Introduction to Server\-Based Timers](http://msdn.microsoft.com/ko-kr/adc0bc0a-a519-4812-bafc-fb9d1a5801fc)를 참조하십시오.  
  
## Interval 속성  
 <xref:System.Windows.Forms.Timer.Interval%2A> 속성에는 다음과 같이 <xref:System.Windows.Forms.Timer> 구성 요소를 프로그래밍할 때 고려해야 할 몇 가지 제한 사항이 있습니다.  
  
-   사용자 응용 프로그램이나 다른 응용 프로그램에서 긴 루프, 과도한 계산 및 드라이브, 네트워크 또는 포트 액세스와 같이 시스템에 무리한 요구를 할 경우에는 해당 응용 프로그램에서 <xref:System.Windows.Forms.Timer.Interval%2A> 속성에 지정된 간격만큼 자주 타이머 이벤트를 발생시키지 않습니다.  
  
-   간격 측정 시간은 정확하지 않을 수 있습니다.  정확하게 하려면 내부에서 누적되는 시간을 추적하지 않고 타이머에서 필요에 따라 시스템 시계를 확인해야 합니다.  
  
-   <xref:System.Windows.Forms.Timer.Interval%2A> 속성의 정밀도는 밀리초입니다.  일부 컴퓨터에서는 해상도가 밀리초보다 큰 고해상도 카운터를 제공합니다.  이러한 카운터의 사용 가능 여부는 컴퓨터의 프로세스 하드웨어에 따라 달라집니다.  자세한 내용은 Microsoft 기술 자료\(http:\/\/support.microsoft.com\)의 172338 문서 "How To Use QueryPerformanceCounter to Time Code"를 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.Forms.Timer>   
 [Timer 구성 요소](../../../../docs/framework/winforms/controls/timer-component-windows-forms.md)   
 [Timer 구성 요소 개요](../../../../docs/framework/winforms/controls/timer-component-overview-windows-forms.md)