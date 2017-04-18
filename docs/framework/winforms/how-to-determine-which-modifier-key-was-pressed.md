---
title: "방법: 누른 보조키 확인 | Microsoft Docs"
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
  - "Alt 키"
  - "Ctrl 키"
  - "이벤트[Windows Forms], 키보드"
  - "이벤트[Windows Forms], 마우스"
  - "키보드 입력"
  - "키보드, 키보드 입력"
  - "keys, Alt 키"
  - "keys, Ctrl 키"
  - "keys, 마지막으로 누른 키 확인"
  - "keys, 보조키"
  - "keys, Shift 키"
  - "Keys.Alt 열거형 멤버"
  - "Keys.ControlKey 열거형 멤버"
  - "Keys.Shift 열거형 멤버"
  - "보조키"
  - "Shift 키"
  - "사용자 입력, 키보드 확인"
ms.assetid: 1e184048-0ae3-4067-a200-d4ba31dbc2cb
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# 방법: 누른 보조키 확인
사용자의 키 입력을 받아들이는 응용 프로그램을 만들 때 Shift, Alt 및 Ctrl 키와 같은 보조키를 모니터링할 필요가 있습니다.  보조키를 다른 키 또는 마우스 클릭과 함께 누르면 응용 프로그램에서 적절하게 응답할 수 있습니다.  예를 들어, S 문자를 누르면 화면에 "S"가 나타나지만 Ctrl\+S를 누르면 현재 문서가 저장됩니다.  <xref:System.Windows.Forms.Control.KeyDown> 이벤트를 처리하면 이벤트 처리기가 받은 <xref:System.Windows.Forms.KeyEventArgs>의 <xref:System.Windows.Forms.KeyEventArgs.Modifiers%2A> 속성에 따라 누르는 보조키가 지정됩니다.  또는 <xref:System.Windows.Forms.KeyEventArgs>의 <xref:System.Windows.Forms.KeyEventArgs.KeyData%2A> 속성에 따라 누르는 문자 및 비트 OR와 함께 사용할 보조키가 지정됩니다.  그러나 <xref:System.Windows.Forms.Control.KeyPress> 이벤트 또는 마우스 이벤트를 처리할 경우 이벤트 처리기에서 이 정보를 받지 않습니다.  이 경우에는 <xref:System.Windows.Forms.Control> 클래스의 <xref:System.Windows.Forms.Control.ModifierKeys%2A> 속성을 사용해야 합니다.  어떤 경우든 적절한 <xref:System.Windows.Forms.Keys> 값과 테스트할 값의 비트 AND를 수행해야 합니다.  <xref:System.Windows.Forms.Keys> 열거형에서는 변형된 보조키를 각각 제공하므로 올바른 값과 비트 AND를 수행하는 것이 중요합니다.  예를 들어, Shift 키는 <xref:System.Windows.Forms.Keys>, <xref:System.Windows.Forms.Keys>, <xref:System.Windows.Forms.Keys> 및 <xref:System.Windows.Forms.Keys>로 표시되며, Shift 키를 보조키로 테스트할 올바른 값은 <xref:System.Windows.Forms.Keys>입니다.  마찬가지로, Ctrl 키와 Alt 키를 보조키로 테스트하려면 <xref:System.Windows.Forms.Keys> 값과 <xref:System.Windows.Forms.Keys> 값을 각각 사용해야 합니다.  
  
> [!NOTE]
>  Visual Basic 프로그래머는 <xref:Microsoft.VisualBasic.Devices.Computer.Keyboard%2A> 속성을 사용하여 키 정보에 액세스할 수도 있습니다.  
  
### 누른 보조키를 확인하려면  
  
-   <xref:System.Windows.Forms.Control.ModifierKeys%2A> 속성 및 <xref:System.Windows.Forms.Keys> 열거형 값에 비트 `AND` 연산자를 사용하여 특정 보조키를 눌렀는지 확인합니다.  다음 코드 예제에서는 <xref:System.Windows.Forms.Control.KeyPress> 이벤트 처리기 내에서 Shift 키를 눌렀는지 확인하는 방법을 보여 줍니다.  
  
     [!code-cpp[System.Windows.Forms.DetermineModifierKey#5](../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DetermineModifierKey/cpp/form1.cpp#5)]
     [!code-csharp[System.Windows.Forms.DetermineModifierKey#5](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DetermineModifierKey/CS/form1.cs#5)]
     [!code-vb[System.Windows.Forms.DetermineModifierKey#5](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DetermineModifierKey/VB/form1.vb#5)]  
  
## 참고 항목  
 <xref:System.Windows.Forms.Keys>   
 <xref:System.Windows.Forms.Control.ModifierKeys%2A>   
 [Windows Forms 응용 프로그램의 키보드 입력](../../../docs/framework/winforms/keyboard-input-in-a-windows-forms-application.md)   
 [How to: Determine If CapsLock is On in Visual Basic](http://msdn.microsoft.com/ko-kr/91e60f5c-dd61-4222-ba5f-39af803afd8c)