---
title: "키보드 입력 작동 방식"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- keyboard input [Windows Forms], about keyboard input
- keyboards [Windows Forms], keyboard input
- Windows Forms, keyboard input
ms.assetid: 9a29433c-a180-49bb-b74c-d187786584c8
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f45d01da6f9a851a0e51f9d614e84a3fba91e4d3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-keyboard-input-works"></a>키보드 입력 작동 방식
Windows Forms에서는 Windows 메시지에 대한 응답으로 키보드 이벤트를 발생시켜 키보드 입력을 처리합니다. 대부분의 Windows Forms 응용 프로그램에서는 키보드 이벤트를 처리하여 키보드 입력을 단독으로 처리합니다. 그러나 키가 컨트롤에 도달하기 전에 키를 가로채는 등의 고급 키보드 입력 시나리오를 구현하려면 키보드 메시지가 작동하는 방식을 알아야 합니다. 이 항목에서는 Windows Forms에서 인식하는 키 데이터 형식을 설명하고 키보드 메시지가 라우팅되는 방법에 대한 개요를 설명합니다. 키보드 이벤트에 대한 자세한 내용은 [키보드 이벤트 사용](../../../docs/framework/winforms/using-keyboard-events.md)을 참조하세요.  
  
## <a name="types-of-keys"></a>키 형식  
 Windows Forms는 키보드 입력 비트으로 표현 되는 가상 키 코드와 식별 <xref:System.Windows.Forms.Keys> 열거 합니다. 와 <xref:System.Windows.Forms.Keys> 열거형 일련의 결과적으로 단일 값의 키 누름된을 결합할 수 있습니다. 이러한 값은 WM_KEYDOWN 및 WM_SYSKEYDOWN Windows 메시지와 함께 제공되는 값에 해당합니다. 대부분의 물리적 키 누름을 처리 하 여 검색할 수 있습니다는 <xref:System.Windows.Forms.Control.KeyDown> 또는 <xref:System.Windows.Forms.Control.KeyUp> 이벤트입니다. 문자 키의 하위 집합을가 <xref:System.Windows.Forms.Keys> 열거 하며 WM_CHAR 및 wm_syschar입니다 Windows 메시지를 함께 사용 해야 하는 값에 해당 합니다. 누른된 키 조합을 문자에 결과가 처리 하 여 문자를 검색할 수 있습니다는 <xref:System.Windows.Forms.Control.KeyPress> 이벤트입니다. 사용할 수 있습니다 <xref:Microsoft.VisualBasic.Devices.Keyboard>, Visual Basic 프로그래밍 인터페이스는 키를 눌렀는지를 검색 하 고 키 보냅니다를으로 노출 합니다. 자세한 내용은 [키보드에 액세스](~/docs/visual-basic/developing-apps/programming/computer-resources/accessing-the-keyboard.md)를 참조하세요.  
  
## <a name="order-of-keyboard-events"></a>키보드 이벤트의 순서  
 앞에서 설명한 대로 한 컨트롤에서 발생할 수 있는 키보드 관련 이벤트는 세 가지입니다. 다음 시퀀스는 키보드 이벤트의 일반적인 순서를 보여 줍니다.  
  
1.  사용자 키 "를" 밀어, 디스패치, 키는 전처리 및 <xref:System.Windows.Forms.Control.KeyDown> 이벤트가 발생 합니다.  
  
2.  "A" 키를 보유 하는 사용자, 디스패치, 키는 전처리 및 <xref:System.Windows.Forms.Control.KeyPress> 이벤트가 발생 합니다.  
  
     이 이벤트는 사용자가 키를 누르고 있을 때 여러 차례 발생합니다.  
  
3.  "A" 키를 키는 전처리 사용자 릴리스 디스패치 및 <xref:System.Windows.Forms.Control.KeyUp> 이벤트가 발생 합니다.  
  
## <a name="preprocessing-keys"></a>키 전처리  
 키보드 메시지 처리는 다른 메시지와 같이 <xref:System.Windows.Forms.Control.WndProc%2A> 폼 이나 컨트롤의 메서드. 그러나 하기 바로 전에 메시지를 처리는 <xref:System.Windows.Forms.Control.PreProcessMessage%2A> 메서드 특수 문자 키 및 물리적 키를 처리 하는 재정의 될 수 있는 하나 이상의 메서드를 호출 합니다. 이러한 메서드를 재정의하여 컨트롤에서 메시지를 처리하기 전에 특정 키를 감지하고 필터링할 수 있습니다. 다음 표에서는 수행할 작업과 이와 관련하여 발생하는 메서드를 메서드 발생 순서에 따라 보여 줍니다.  
  
### <a name="preprocessing-for-a-keydown-event"></a>KeyDown 이벤트의 전처리  
  
|작업|관련 메서드|노트|  
|------------|--------------------|-----------|  
|액셀러레이터 키나 메뉴 바로 가기 같은 명령 키를 확인합니다.|<xref:System.Windows.Forms.Control.ProcessCmdKey%2A>|이 메서드는 일반 키보다 우선되는 명령 키를 처리합니다. 이 메서드가 `true`를 반환하는 경우 키 메시지가 디스패치되지 않고 키 이벤트도 발생하지 않습니다. 반환 하는 경우 `false`, <xref:System.Windows.Forms.Control.IsInputKey%2A> 라고`.`|  
|발생 시켜야 하는 일반 문자 키 또는 전처리가 필요한 특수 키인지를 확인 한 <xref:System.Windows.Forms.Control.KeyDown> 이벤트 컨트롤에 전달 하 고 있습니다.|<xref:System.Windows.Forms.Control.IsInputKey%2A>|메서드에서 반환 되 면 `true`, 컨트롤은 일반 문자 및 <xref:System.Windows.Forms.Control.KeyDown> 이벤트가 발생 합니다. 경우 `false`, <xref:System.Windows.Forms.Control.ProcessDialogKey%2A> 호출 됩니다. **참고:** 처리할 수는 컨트롤은 키 또는 키의 조합을 가져옵니다 되도록는 <xref:System.Windows.Forms.Control.PreviewKeyDown> 이벤트 집합과 <xref:System.Windows.Forms.PreviewKeyDownEventArgs.IsInputKey%2A> 의 <xref:System.Windows.Forms.PreviewKeyDownEventArgs> 를 `true` 키 또는 키를 모두에 대 한 합니다.|  
|탐색 키(Esc, Tab, Enter 또는 화살표 키)를 확인합니다.|<xref:System.Windows.Forms.Control.ProcessDialogKey%2A>|이 메서드는 컨트롤 내에서 컨트롤과 부모 컨트롤 간의 포커스 전환과 같은 특수 기능을 담당하는 실제 키를 처리합니다. 즉시 제어할 키를 처리 하지 않을 경우의 <xref:System.Windows.Forms.Control.ProcessDialogKey%2A> 등 계층의 맨 위에 있는 컨트롤에 부모 컨트롤에서 호출 됩니다. 이 메서드에서 `true`를 반환하면 전처리는 완료되지만 키 이벤트는 생성되지 않습니다. 반환 하는 경우 `false`, <xref:System.Windows.Forms.Control.KeyDown> 이벤트가 발생 합니다.|  
  
### <a name="preprocessing-for-a-keypress-event"></a>KeyPress 이벤트의 전처리  
  
|작업|관련 메서드|노트|  
|------------|--------------------|-----------|  
|키가 컨트롤에서 전처리되어야 하는 일반 문자인지 여부를 확인합니다.|<xref:System.Windows.Forms.Control.IsInputChar%2A>|이 메서드가 반환 하는 경우 일반 문자는 문자에는, `true`, <xref:System.Windows.Forms.Control.KeyPress> 이벤트가 발생 하 고 전처리 더 이상 발생 합니다. 그렇지 않으면 <xref:System.Windows.Forms.Control.ProcessDialogChar%2A> 호출 됩니다.|  
|문자가 단추의 &OK와 같은 니모닉인지 확인하려면 선택합니다.|<xref:System.Windows.Forms.Control.ProcessDialogChar%2A>|이 메서드를 비슷합니다 <xref:System.Windows.Forms.Control.ProcessDialogKey%2A>, 컨트롤 계층 구조 호출 됩니다. 컨트롤이 컨테이너 컨트롤 경우 확인 니모닉 호출 하 여 <xref:System.Windows.Forms.Control.ProcessMnemonic%2A> 자체 및 해당 자식 컨트롤에 있습니다. 경우 <xref:System.Windows.Forms.Control.ProcessDialogChar%2A> 반환 `true`, <xref:System.Windows.Forms.Control.KeyPress> 이벤트가 발생 하지 않습니다.|  
  
## <a name="processing-keyboard-messages"></a>키보드 메시지 전처리  
 키보드 메시지 도달 범위는 <xref:System.Windows.Forms.Control.WndProc%2A> 메서드는 재정의할 수 있는 메서드 집합에 의해 처리 된 폼 이나 컨트롤의 합니다. 이러한 각 방법의 반환을 <xref:System.Boolean> 키보드 메시지 처리 및 컨트롤에서 사용 된 있는지 여부를 지정 하는 값입니다. 이러한 메서드 중 한 메서드에서 `true`를 반환하면 메시지가 처리된 것으로 간주됩니다. 그러므로 컨트롤의 기본 또는 부모에 추가 처리를 위한 메시지를 전달하지 않습니다. 그렇지 않은 경우에는 메시지가 메시지 큐에 유지되고 컨트롤의 기본 또는 부모의 다른 메서드에서 처리됩니다. 다음 표에서는 키보드 메시지를 처리하는 메서드를 보여 줍니다.  
  
|메서드|참고|  
|------------|-----------|  
|<xref:System.Windows.Forms.Control.ProcessKeyMessage%2A>|받는 모든 키보드 메시지를 처리 하는이 메서드는 <xref:System.Windows.Forms.Control.WndProc%2A> 컨트롤의 메서드.|  
|<xref:System.Windows.Forms.Control.ProcessKeyPreview%2A>|이 메서드는 키보드 메시지를 컨트롤의 부모에 보냅니다. 경우 <xref:System.Windows.Forms.Control.ProcessKeyPreview%2A> 반환 `true`, 그렇지 않으면 키 이벤트가 생성 됩니다 <xref:System.Windows.Forms.Control.ProcessKeyEventArgs%2A> 라고 합니다.|  
|<xref:System.Windows.Forms.Control.ProcessKeyEventArgs%2A>|이 메서드는 <xref:System.Windows.Forms.Control.KeyDown>, <xref:System.Windows.Forms.Control.KeyPress>, 및 <xref:System.Windows.Forms.Control.KeyUp> 이벤트 적절 하 게 합니다.|  
  
## <a name="overriding-keyboard-methods"></a>키보드 메서드 재정의  
 키보드 메시지를 전처리하고 처리할 때 재정의할 수 있는 여러 가지 메서드가 있지만 그중 다음과 같은 메서드가 특히 많이 사용됩니다. 다음 표에서는 수행할 작업과 키보드 메서드를 재정의할 수 있는 가장 좋은 방법을 보여 줍니다. 메서드 재정의에 대 한 자세한 내용은 참조 하십시오. [파생 클래스의 속성 및 메서드 재정의](~/docs/visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md#overriding-properties-and-methods-in-derived-classes)합니다.  
  
|작업|메서드|  
|----------|------------|  
|탐색 키를 가로채 고 발생 시키는 <xref:System.Windows.Forms.Control.KeyDown> 이벤트입니다. Tab 키와 Enter 키를 텍스트 상자에서 처리하려는 경우를 예를 들어보겠습니다.|<xref:System.Windows.Forms.Control.IsInputKey%2A>을 재정의합니다. **참고:** 처리할 수 있습니다는 <xref:System.Windows.Forms.Control.PreviewKeyDown> 이벤트 집합과 <xref:System.Windows.Forms.PreviewKeyDownEventArgs.IsInputKey%2A> 의 <xref:System.Windows.Forms.PreviewKeyDownEventArgs> 를 `true` 키 또는 키를 모두에 대 한 합니다.|  
|컨트롤에서 특수 입력 키나 탐색 키에 대한 처리를 수행합니다. 예를 들어 목록 컨트롤에서 화살표 키를 사용하여 선택한 항목을 변경할 수 있습니다.|<xref:System.Windows.Forms.Control.ProcessDialogKey%2A>를 재정의합니다.|  
|탐색 키를 가로채 고 발생 시키는 <xref:System.Windows.Forms.Control.KeyPress> 이벤트입니다. 예를 들어 스핀 상자 컨트롤에서 화살표 키를 여러 차례 눌러 항목 전체를 빠르게 진행할 수 있습니다.|<xref:System.Windows.Forms.Control.IsInputChar%2A>을 재정의합니다.|  
|수행 하는 동안 입력 또는 탐색 특수 처리는 <xref:System.Windows.Forms.Control.KeyPress> 이벤트입니다. 예를 들어, 목록 컨트롤에서 "r" 키를 누른 채로 r 문자로 시작하는 항목 사이를 건너뛸 수 있습니다.|<xref:System.Windows.Forms.Control.ProcessDialogChar%2A>를 재정의합니다.|  
|사용자 지정 니모닉 처리를 수행합니다. 예를 들어 도구 모음에 포함된, 소유자가 그린 단추의 니모닉을 처리할 수 있습니다.|<xref:System.Windows.Forms.Control.ProcessMnemonic%2A>을 재정의합니다.|  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.Keys>  
 <xref:System.Windows.Forms.Control.WndProc%2A>  
 <xref:System.Windows.Forms.Control.PreProcessMessage%2A>  
 [My.Computer.Keyboard 개체](~/docs/visual-basic/language-reference/objects/my-computer-keyboard-object.md)  
 [키보드에 액세스](~/docs/visual-basic/developing-apps/programming/computer-resources/accessing-the-keyboard.md)  
 [키보드 이벤트 사용](../../../docs/framework/winforms/using-keyboard-events.md)
