---
title: "Windows Forms 응용 프로그램의 사용자 입력"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Windows Forms, user input
ms.assetid: 9d61fa96-70f7-4754-885a-49a4a6316bdb
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: fb6f832b77404b57ab22e4ac472e7707f0e10dd5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="user-input-in-a-windows-forms-application"></a>Windows Forms 응용 프로그램의 사용자 입력
Windows Forms에서 사용자 입력 Windows 메시지 형식으로의 응용 프로그램에 전송 됩니다. 응용 프로그램 폼에서 이러한 메시지를 처리 하 고 수준을 제어 하는 일련의 재정의 가능한 메서드 합니다. 이러한 메서드는 마우스 및 키보드 메시지를 수신 하는 경우 마우스에 대 한 정보를 얻거나 키보드 입력을 처리할 수 있는 이벤트를 발생 시킵니다. 대부분의 경우에서 Windows Forms 응용 프로그램은 이러한 이벤트를 처리 하 여 모든 사용자 입력을 처리 수입니다. 다른 경우에 응용 프로그램은 응용 프로그램, 폼 또는 컨트롤에서 수신 하기 전에 특정 메시지를 차단 하기 위해 메시지를 처리 하는 메서드 중 하나를 재정의 해야 할 수 있습니다.  
  
## <a name="mouse-and-keyboard-events"></a>마우스 및 키보드 이벤트  
 모든 Windows Forms 컨트롤의 마우스 및 키보드 입력와 관련 된 이벤트 집합을 상속 합니다. 예를 들어 한 컨트롤에서 처리할 수는 <xref:System.Windows.Forms.Control.KeyPress> 는 눌린 키의 문자 코드를 확인 하는 이벤트 또는 컨트롤을 처리할 수는 <xref:System.Windows.Forms.Control.MouseClick> 클릭 마우스의 위치를 결정 하는 이벤트입니다. 마우스 및 키보드 이벤트에 대 한 자세한 내용은 참조 하십시오. [키보드 이벤트를 사용 하 여](../../../docs/framework/winforms/using-keyboard-events.md) 및 [Windows Forms의 마우스 이벤트](../../../docs/framework/winforms/mouse-events-in-windows-forms.md)합니다.  
  
## <a name="methods-that-process-user-input-messages"></a>사용자 입력된 메시지를 처리 하는 메서드  
 폼 및 컨트롤에 대 한 액세스 권한이 <xref:System.Windows.Forms.IMessageFilter> 인터페이스 및 메시지 큐의 여러 지점에서 Windows 메시지를 처리 하는 재정의 가능한 메서드 집합이 있습니다. 모든는 이러한 메서드는 <xref:System.Windows.Forms.Message> Windows 메시지의 하위 수준 세부 정보를 캡슐화 하는 매개 변수입니다. 구현 하거나 메시지에서 확인 된 메시지를 사용 하거나 메시지 큐에서 다음 소비자에 전달 하도록 이러한 메서드를 재정의할 수 있습니다. 다음 표에서 Windows Forms에서 모든 Windows 메시지를 처리 하는 메서드를 제공 합니다.  
  
|메서드|참고|  
|------------|-----------|  
|<xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A>|이 메서드는 응용 프로그램 수준에서 대기 중인된 (게시 라고도 함) Windows 메시지를 차단합니다.|  
|<xref:System.Windows.Forms.Control.PreProcessMessage%2A>|이 메서드는 처리 전에 폼과 컨트롤 수준에서 Windows 메시지를 차단 합니다.|  
|<xref:System.Windows.Forms.Control.WndProc%2A>|이 메서드는 폼과 컨트롤 수준에서 Windows 메시지를 처리합니다.|  
|<xref:System.Windows.Forms.Control.DefWndProc%2A>|이 메서드는 폼과 컨트롤 수준에서 Windows 메시지의 기본 처리를 수행합니다. 창의 최소 기능을 제공 합니다.|  
|<xref:System.Windows.Forms.Control.OnNotifyMessage%2A>|처리 된 후이 메서드는 폼과 컨트롤 수준에서 메시지를 차단 합니다. <xref:System.Windows.Forms.ControlStyles.EnableNotifyMessage> 이 메서드를 호출할 수에 대 한 스타일 비트를 설정 해야 합니다.|  
  
 키보드 및 마우스 메시지의 해당 유형의 메시지에만 적용 되는 재정의 가능한 메서드가 추가 집합으로 처리 됩니다. 자세한 내용은 참조 [키보드 입력 작동 방식](../../../docs/framework/winforms/how-keyboard-input-works.md) 및 [Windows Forms의 마우스 입력 방법](../../../docs/framework/winforms/how-mouse-input-works-in-windows-forms.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Windows Forms에 사용자 입력](../../../docs/framework/winforms/user-input-in-windows-forms.md)  
 [Windows Forms 응용 프로그램의 키보드 입력](../../../docs/framework/winforms/keyboard-input-in-a-windows-forms-application.md)  
 [Windows Forms 응용 프로그램의 마우스 입력](../../../docs/framework/winforms/mouse-input-in-a-windows-forms-application.md)
