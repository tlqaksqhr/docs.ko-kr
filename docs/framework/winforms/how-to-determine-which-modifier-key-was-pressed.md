---
title: "방법: 누른 보조키 확인"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- keyboard input
- shift keys
- events [Windows Forms], mouse
- Keys.ControlKey enumeration member
- keys [Windows Forms], control keys
- user input [Windows Forms], checking for keyboard
- keys [Windows Forms], determining last pressed
- keys [Windows Forms], shift keys
- keys [Windows Forms], modifier keys
- control keys
- keys [Windows Forms], alt keys
- alt keys
- Keys.Shift enumeration member
- events [Windows Forms], keyboard
- keyboards [Windows Forms], keyboard input
- Keys.Alt enumeration member
- modifier keys
ms.assetid: 1e184048-0ae3-4067-a200-d4ba31dbc2cb
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6fdc93063bbc8c9428f2f01c6cd5c0578e77ab01
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-determine-which-modifier-key-was-pressed"></a>방법: 누른 보조키 확인
사용자의 키 입력을 허용 하는 응용 프로그램을 만들 때 SHIFT, ALT, CTRL 키 등 보조키를 모니터링 하려는 될 수 있습니다. 보조 키를 누르면 조합에서 다른 키 또는 마우스 클릭, 응용 프로그램이 적절 하 게 응답할 수 있습니다. 예를 들어, "s" 화면에 문자 S를 누를 경우 단순히 발생할 수 있습니다 하지만 CTRL + S 키를 누르면 현재 문서를 저장 될 수 있습니다. 처리 하는 경우는 <xref:System.Windows.Forms.Control.KeyDown> 이벤트는 <xref:System.Windows.Forms.KeyEventArgs.Modifiers%2A> 속성은 <xref:System.Windows.Forms.KeyEventArgs> 수신 처리기 이벤트에 의해 보조 키를 누르면을 지정 합니다. 또는 <xref:System.Windows.Forms.KeyEventArgs.KeyData%2A> 속성 <xref:System.Windows.Forms.KeyEventArgs> 비트 OR 연산자와 함께 모든 보조 키도 누른 문자를 지정 합니다. 그러나 처리 하는 경우는 <xref:System.Windows.Forms.Control.KeyPress> 이벤트 또는 마우스 이벤트를 이벤트 처리기는이 정보를 수신 하지 않습니다. 이 경우에 사용 해야는 <xref:System.Windows.Forms.Control.ModifierKeys%2A> 의 속성은 <xref:System.Windows.Forms.Control> 클래스입니다. 두 경우 모두 적절 한 비트 AND를 수행 해야 <xref:System.Windows.Forms.Keys> 값과 테스트 하는 값입니다. <xref:System.Windows.Forms.Keys> 열거형 변형을 한정자, 각 키의 비트를 수행 해야 하므로 및 올바른 값으로 제공 합니다. SHIFT 키를 나타내는 예를 들어 <xref:System.Windows.Forms.Keys.Shift>, <xref:System.Windows.Forms.Keys.ShiftKey>, <xref:System.Windows.Forms.Keys.RShiftKey> 및 <xref:System.Windows.Forms.Keys.LShiftKey> 보조키 그대로 SHIFT를 테스트 하려면 올바른 값 <xref:System.Windows.Forms.Keys.Shift>합니다. 마찬가지로, 한정자로 보조키 및 alt 키에 대 한 테스트를 사용 해야는 <xref:System.Windows.Forms.Keys.Control> 및 <xref:System.Windows.Forms.Keys.Alt> 값을 각각.  
  
> [!NOTE]
>  Visual Basic 프로그래머를 통해 키 정보에 액세스할 수도 <xref:Microsoft.VisualBasic.Devices.Computer.Keyboard%2A> 속성  
  
### <a name="to-determine-which-modifier-key-was-pressed"></a>누른 보조키 확인 하려면  
  
-   비트를 사용 하 여 `AND` 연산자는 <xref:System.Windows.Forms.Control.ModifierKeys%2A> 속성 및 값의는 <xref:System.Windows.Forms.Keys> 특정 보조 키를 눌렀는지 여부를 결정 하는 열거형입니다. 다음 코드 예제에서는 내에서 SHIFT 키를 눌렀는지 여부를 확인 하는 방법을 보여 줍니다.는 <xref:System.Windows.Forms.Control.KeyPress> 이벤트 처리기입니다.  
  
     [!code-cpp[System.Windows.Forms.DetermineModifierKey#5](../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DetermineModifierKey/cpp/form1.cpp#5)]
     [!code-csharp[System.Windows.Forms.DetermineModifierKey#5](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DetermineModifierKey/CS/form1.cs#5)]
     [!code-vb[System.Windows.Forms.DetermineModifierKey#5](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DetermineModifierKey/VB/form1.vb#5)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.Keys>  
 <xref:System.Windows.Forms.Control.ModifierKeys%2A>  
 [Windows Forms 응용 프로그램의 키보드 입력](../../../docs/framework/winforms/keyboard-input-in-a-windows-forms-application.md)  
 [방법: Visual Basic의 CapsLock을 줄 켜져 있는지 확인](http://msdn.microsoft.com/en-us/91e60f5c-dd61-4222-ba5f-39af803afd8c)
