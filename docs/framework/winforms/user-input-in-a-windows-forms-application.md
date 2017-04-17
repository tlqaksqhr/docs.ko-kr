---
title: "Windows Forms 응용 프로그램의 사용자 입력 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Windows Forms, 사용자 입력"
ms.assetid: 9d61fa96-70f7-4754-885a-49a4a6316bdb
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Windows Forms 응용 프로그램의 사용자 입력
Windows Forms에서 사용자 입력은 Windows 메시지 형식으로 응용 프로그램에 전송됩니다.  재정의 가능한 일련의 메서드는 응용 프로그램, 폼 및 컨트롤 수준에서 이러한 메시지를 처리합니다.  이러한 메서드가 마우스 및 키보드 메시지를 수신하면 해당 마우스 또는 키보드 입력에 대한 정보를 얻기 위해 처리할 수 있는 이벤트를 발생시킵니다.  많은 경우 Windows Forms 응용 프로그램에서는 이러한 이벤트를 처리하여 모든 사용자 입력을 간단히 처리할 수 있습니다.  그렇지 않은 경우 응용 프로그램에서는 응용 프로그램, 폼 또는 컨트롤이 특정 메시지를 수신하기 전에 이러한 메시지를 차단하기 위해 메시지를 처리하는 메서드 중 하나를 재정의해야 할 수 있습니다.  
  
## 마우스 및 키보드 이벤트  
 모든 Windows Forms 컨트롤은 마우스 및 키보드 입력과 관련된 이벤트 집합을 상속합니다.  예를 들어, 컨트롤은 <xref:System.Windows.Forms.Control.KeyPress> 이벤트를 처리하여 눌린 키의 문자 코드를 확인하거나 <xref:System.Windows.Forms.Control.MouseClick> 이벤트를 처리하여 마우스 클릭의 위치를 확인할 수 있습니다.  마우스 및 키보드 이벤트에 대한 자세한 내용은 [키보드 이벤트 사용](../../../docs/framework/winforms/using-keyboard-events.md) 및 [Windows Forms의 마우스 이벤트](../../../docs/framework/winforms/mouse-events-in-windows-forms.md)를 참조하십시오.  
  
## 사용자 입력 메시지를 처리하는 메서드  
 폼과 컨트롤은 메시지 큐의 서로 다른 지점에서 Windows 메시지를 처리하는 <xref:System.Windows.Forms.IMessageFilter> 인터페이스 및 재정의 가능한 일련의 메서드에 액세스할 수 있습니다.  이러한 메서드에는 모두 Windows 메시지의 하위 수준 세부 정보를 캡슐화하는 <xref:System.Windows.Forms.Message> 매개 변수가 포함되어 있습니다.  이러한 메서드를 구현하거나 재정의하여 메시지를 검사한 다음에는 메시지를 사용하거나 메시지 큐의 다음 사용자에게 전달합니다.  다음 표에서는 Windows Forms의 모든 Windows 메시지를 처리하는 메서드를 보여 줍니다.  
  
|메서드|참고|  
|---------|--------|  
|<xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A>|이 메서드는 응용 프로그램 수준에서 대기 중인\(게시된\) Windows 메시지를 차단합니다.|  
|<xref:System.Windows.Forms.Control.PreProcessMessage%2A>|이 메서드는 Windows 메시지가 처리되기 전에 폼 수준과 컨트롤 수준에서 해당 메시지를 차단합니다.|  
|<xref:System.Windows.Forms.Control.WndProc%2A>|이 메서드는 폼 수준과 컨트롤 수준에서 Windows 메시지를 처리합니다.|  
|<xref:System.Windows.Forms.Control.DefWndProc%2A>|이 메서드는 폼 수준과 컨트롤 수준에서 Windows 메시지에 대해 기본 처리를 수행하며  창의 최소 기능을 제공합니다.|  
|<xref:System.Windows.Forms.Control.OnNotifyMessage%2A>|이 메서드는 메시지가 처리된 다음에 폼 수준과 컨트롤 수준에서 해당 메시지를 차단합니다.  이 메서드를 호출하려면 <xref:System.Windows.Forms.ControlStyles> 스타일 비트를 설정해야 합니다.|  
  
 키보드 및 마우스 메시지는 이러한 메시지 형식과 관련된 재정의 가능한 추가 메서드 집합으로 처리할 수도 있습니다.  자세한 내용은 [키보드 입력 작동 방식](../../../docs/framework/winforms/how-keyboard-input-works.md) 및 [Windows Forms에서 마우스 입력이 작동하는 방식](../../../docs/framework/winforms/how-mouse-input-works-in-windows-forms.md)을 참조하십시오.  
  
## 참고 항목  
 [Windows Forms에 사용자 입력](../../../docs/framework/winforms/user-input-in-windows-forms.md)   
 [Windows Forms 응용 프로그램의 키보드 입력](../../../docs/framework/winforms/keyboard-input-in-a-windows-forms-application.md)   
 [Windows Forms 응용 프로그램의 마우스 입력](../../../docs/framework/winforms/mouse-input-in-a-windows-forms-application.md)