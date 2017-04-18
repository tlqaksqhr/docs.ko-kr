---
title: "키보드 입력 작동 방식 | Microsoft Docs"
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
  - "키보드 입력, 키보드 입력 정보"
  - "키보드, 키보드 입력"
  - "Windows Forms, 키보드 입력"
ms.assetid: 9a29433c-a180-49bb-b74c-d187786584c8
caps.latest.revision: 20
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 20
---
# 키보드 입력 작동 방식
Windows Forms에서는 Windows 메시지에 대한 응답으로 키보드 이벤트를 발생시켜 키보드 입력을 처리합니다.  대부분의 Windows Forms 응용 프로그램에서는 키보드 이벤트를 처리하여 키보드 입력을 단독으로 처리합니다.  그러나 키가 컨트롤에 도달하기 전에 키를 가로채는 등의 고급 키보드 입력 시나리오를 구현하려면 키보드 메시지가 작동하는 방식을 알아야 합니다.  이 항목에서는 Windows Forms에서 인식하는 키 데이터 형식을 설명하고 키보드 메시지가 라우팅되는 방법에 대한 개요를 설명합니다.  키보드 이벤트에 대한 자세한 내용은 [키보드 이벤트 사용](../../../docs/framework/winforms/using-keyboard-events.md)을 참조하십시오.  
  
## 키 형식  
 Windows Forms에서는 키보드 입력을 비트 <xref:System.Windows.Forms.Keys> 열거형으로 나타내는 가상 키 코드로 식별합니다.  <xref:System.Windows.Forms.Keys> 열거형을 사용하면 눌려진 일련의 키를 결합하여 단일 값을 만들 수 있습니다.  이러한 값은 WM\_KEYDOWN 및 WM\_SYSKEYDOWN Windows 메시지와 함께 제공되는 값에 해당합니다.  <xref:System.Windows.Forms.Control.KeyDown> 또는 <xref:System.Windows.Forms.Control.KeyUp> 이벤트를 처리하여 실제로 눌려진 키를 대부분 감지할 수 있습니다.  문자 키는 <xref:System.Windows.Forms.Keys> 열거형의 하위 집합이며 WM\_CHAR 및 WM\_SYSCHAR Windows 메시지와 함께 제공되는 값에 해당합니다.  눌려진 키를 결합하여 문자가 만들어지는 경우에는 <xref:System.Windows.Forms.Control.KeyPress> 이벤트를 처리하여 해당 문자를 감지할 수 있습니다.  또는 Visual Basic 프로그래밍 인터페이스에서 노출되는 <xref:Microsoft.VisualBasic.Devices.Keyboard>를 사용하여 눌려진 키를 확인하고 키를 보낼 수 있습니다.  자세한 내용은 [Accessing the Keyboard](../Topic/Accessing%20the%20Keyboard%20\(Visual%20Basic\).md)를 참조하십시오.  
  
## 키보드 이벤트의 순서  
 앞에서 설명한 대로 한 컨트롤에서 발생할 수 있는 키보드 관련 이벤트는 세 가지입니다.  다음 시퀀스는 키보드 이벤트의 일반적인 순서를 보여 줍니다.  
  
1.  사용자가 "a" 키를 누르면 해당 키가 전처리되고 디스패치된 다음 <xref:System.Windows.Forms.Control.KeyDown> 이벤트가 발생합니다.  
  
2.  사용자가 "a" 키를 누르고 있으면 해당 키가 전처리되고 디스패치된 다음 <xref:System.Windows.Forms.Control.KeyPress> 이벤트가 발생합니다.  
  
     이 이벤트는 사용자가 키를 누르고 있을 때 여러 차례 발생합니다.  
  
3.  사용자가 "a" 키를 놓으면 해당 키가 전처리되고 디스패치된 다음 <xref:System.Windows.Forms.Control.KeyUp> 이벤트가 발생합니다.  
  
## 키 전처리  
 다른 메시지와 마찬가지로 키보드 메시지는 폼이나 컨트롤의 <xref:System.Windows.Forms.Control.WndProc%2A> 메서드에서 처리됩니다.  그러나 키보드 메시지를 처리하기 전에 <xref:System.Windows.Forms.Control.PreProcessMessage%2A> 메서드는 특수 문자 키와 실제 키를 처리하도록 재정의할 수 있는 메서드를 하나 이상 호출합니다.  이러한 메서드를 재정의하여 컨트롤에서 메시지를 처리하기 전에 특정 키를 감지하고 필터링할 수 있습니다.  다음 표에서는 수행할 작업과 발생하는 관련 메서드를 메서드 발생 순서에 따라 보여 줍니다.  
  
### KeyDown 이벤트의 전처리  
  
|동작|관련 메서드|참고|  
|--------|------------|--------|  
|액셀러레이터 키나 메뉴 바로 가기 같은 명령 키를 확인합니다.|<xref:System.Windows.Forms.Control.ProcessCmdKey%2A>|이 메서드는 일반 키보다 우선되는 명령 키를 처리합니다.  이 메서드가 `true`를 반환하는 경우 키 메시지가 디스패치되지 않고 키 이벤트도 발생하지 않습니다.  `false`를 반환하는 경우에는 <xref:System.Windows.Forms.Control.IsInputKey%2A>가 호출됩니다`.`|  
|전처리가 필요한 특수 키인지 아니면 <xref:System.Windows.Forms.Control.KeyDown> 이벤트를 발생시켜 컨트롤에 디스패치해야 하는 일반 문자 키인지 확인합니다.|<xref:System.Windows.Forms.Control.IsInputKey%2A>|이 메서드가 `true`를 반환하는 경우에는 컨트롤이 일반 문자이고 <xref:System.Windows.Forms.Control.KeyDown> 이벤트가 발생합니다.  `false`를 반환하는 경우에는 <xref:System.Windows.Forms.Control.ProcessDialogKey%2A>가 호출됩니다. **Note:**  컨트롤에서 키나 키 조합을 받도록 하려면 <xref:System.Windows.Forms.Control.PreviewKeyDown> 이벤트를 처리한 다음 원하는 키나 키 조합에 대해 <xref:System.Windows.Forms.PreviewKeyDownEventArgs>의 <xref:System.Windows.Forms.PreviewKeyDownEventArgs.IsInputKey%2A>를 `true`로 설정합니다.|  
|탐색 키\(Esc, Tab, Enter 또는 화살표 키\)인지 확인합니다.|<xref:System.Windows.Forms.Control.ProcessDialogKey%2A>|이 메서드는 컨트롤 내에서 컨트롤과 부모 컨트롤 간의 포커스 전환과 같은 특수 기능을 담당하는 실제 키를 처리합니다.  현재 컨트롤에서 키를 처리하지 않으면 <xref:System.Windows.Forms.Control.ProcessDialogKey%2A>가 부모 컨트롤에서 호출되고 계층 구조의 최상위 컨트롤에까지 이같은 호출 방식이 적용됩니다.  이 메서드에서 `true`를 반환하면 전처리는 완료되지만 키 이벤트는 생성되지 않습니다.  `false`를 반환하면 <xref:System.Windows.Forms.Control.KeyDown> 이벤트가 발생합니다.|  
  
### KeyPress 이벤트의 전처리  
  
|동작|관련 메서드|참고|  
|--------|------------|--------|  
|키가 컨트롤에서 전처리되어야 하는 일반 문자인지 여부를 확인합니다.|<xref:System.Windows.Forms.Control.IsInputChar%2A>|문자가 일반 문자인 경우 이 메서드는 `true`를 반환하고 <xref:System.Windows.Forms.Control.KeyPress> 이벤트가 발생하지만 추가적인 전처리 작업은 발생하지 않습니다.  일반 문자가 아닌 경우에는 <xref:System.Windows.Forms.Control.ProcessDialogChar%2A>가 호출됩니다.|  
|문자가 단추의 &OK와 같은 니모닉인지 여부를 확인합니다.|<xref:System.Windows.Forms.Control.ProcessDialogChar%2A>|이 메서드는 <xref:System.Windows.Forms.Control.ProcessDialogKey%2A>와 비슷하게 컨트롤 계층 구조를 올라가며 호출됩니다.  컨트롤이 컨테이너 컨트롤인 경우 이 메서드는 컨트롤과 그 자식 컨트롤에 대해 <xref:System.Windows.Forms.Control.ProcessMnemonic%2A>을 호출하여 니모닉을 확인합니다.  <xref:System.Windows.Forms.Control.ProcessDialogChar%2A>가 `true`를 반환하는 경우 <xref:System.Windows.Forms.Control.KeyPress> 이벤트가 발생하지 않습니다.|  
  
## 키보드 메시지 전처리  
 폼이나 컨트롤의 <xref:System.Windows.Forms.Control.WndProc%2A> 메서드에 도달한 키보드 메시지는 재정의할 수 있는 메서드 집합에 의해 처리됩니다.  이러한 메서드는 각각 키보드 메시지가 처리되어 컨트롤에서 사용되었는지 여부를 지정하는 <xref:System.Boolean> 값을 반환합니다.  이러한 메서드 중 한 메서드에서 `true`가 반환되면 해당 메시지가 처리된 것으로 간주되므로 추가 처리를 위해 컨트롤의 기본 또는 부모에 메시지가 전달되지 않습니다.  그렇지 않은 경우에는 메시지가 메시지 큐에 유지되고 컨트롤의 기본 또는 부모의 다른 메서드에서 처리됩니다.  다음 표에서는 키보드 메시지를 처리하는 메서드를 보여 줍니다.  
  
|메서드|참고|  
|---------|--------|  
|<xref:System.Windows.Forms.Control.ProcessKeyMessage%2A>|이 메서드는 컨트롤의 <xref:System.Windows.Forms.Control.WndProc%2A> 메서드에서 받은 모든 키보드 메시지를 처리합니다.|  
|<xref:System.Windows.Forms.Control.ProcessKeyPreview%2A>|이 메서드는 키보드 메시지를 컨트롤의 부모에게 보냅니다.  <xref:System.Windows.Forms.Control.ProcessKeyPreview%2A>가 `true`를 반환하면 키 이벤트가 생성되지 않고, 그렇지 않은 경우에는 <xref:System.Windows.Forms.Control.ProcessKeyEventArgs%2A>가 호출됩니다.|  
|<xref:System.Windows.Forms.Control.ProcessKeyEventArgs%2A>|이 메서드는 <xref:System.Windows.Forms.Control.KeyDown>, <xref:System.Windows.Forms.Control.KeyPress> 및 <xref:System.Windows.Forms.Control.KeyUp> 이벤트를 적절하게 발생시킵니다.|  
  
## 키보드 메서드 재정의  
 키보드 메시지를 전처리하고 처리할 때 재정의할 수 있는 여러 가지 메서드가 있지만 그 중 다음과 같은 메서드가 특히 많이 사용됩니다.  다음 표에서는 수행할 작업과 키보드 메서드를 재정의할 수 있는 가장 좋은 방법을 보여 줍니다.  메서드 재정의에 대한 자세한 내용은 [NOT IN BUILD: Overriding Properties and Methods](http://msdn.microsoft.com/ko-kr/2167e8f5-1225-4b13-9ebd-02591ba90213)를 참조하십시오.  
  
|Task|메서드|  
|----------|---------|  
|탐색 키를 가로채고 <xref:System.Windows.Forms.Control.KeyDown> 이벤트를 발생시킵니다.  예를 들어 Tab 키와 Enter 키를 텍스트 상자에서 처리해야 할 수 있습니다.|<xref:System.Windows.Forms.Control.IsInputKey%2A>를 재정의합니다. **Note:**  또는 <xref:System.Windows.Forms.Control.PreviewKeyDown> 이벤트를 처리하고 원하는 키에 대해 <xref:System.Windows.Forms.PreviewKeyDownEventArgs>의 <xref:System.Windows.Forms.PreviewKeyDownEventArgs.IsInputKey%2A>를 `true`로 설정할 수 있습니다.|  
|컨트롤에서 특수 입력 키나 탐색 키에 대한 처리를 수행합니다.  예를 들어, 목록 컨트롤에서 화살표 키를 사용하여 선택한 항목을 변경할 수 있습니다.|<xref:System.Windows.Forms.Control.ProcessDialogKey%2A>를 재정의합니다.|  
|탐색 키를 가로채고 <xref:System.Windows.Forms.Control.KeyPress> 이벤트를 발생시킵니다.  예를 들어, 스핀 상자 컨트롤에서 화살표 키를 여러 차례 눌러 항목 전체를 빠르게 진행할 수 있습니다.|<xref:System.Windows.Forms.Control.IsInputChar%2A>를 재정의합니다.|  
|<xref:System.Windows.Forms.Control.KeyPress> 이벤트 중 특수 입력 키나 탐색 키에 대한 처리를 수행합니다.  예를 들어, 목록 컨트롤에서 "r" 키를 누른 채로 r 문자로 시작하는 항목 사이를 건너뛸 수 있습니다.|<xref:System.Windows.Forms.Control.ProcessDialogChar%2A>를 재정의합니다.|  
|사용자 지정 니모닉 처리를 수행합니다. 예를 들어, 도구 모음에 포함된 소유자가 그린 단추의 니모닉을 처리할 수 있습니다.|<xref:System.Windows.Forms.Control.ProcessMnemonic%2A>를 재정의합니다.|  
  
## 참고 항목  
 <xref:System.Windows.Forms.Keys>   
 <xref:System.Windows.Forms.Control.WndProc%2A>   
 <xref:System.Windows.Forms.Control.PreProcessMessage%2A>   
 [My.Computer.Keyboard Object](../../../ocs/visual-basic/language-reference/objects/my-computer-keyboard-object.md)   
 [Accessing the Keyboard](../Topic/Accessing%20the%20Keyboard%20\(Visual%20Basic\).md)   
 [키보드 이벤트 사용](../../../docs/framework/winforms/using-keyboard-events.md)