---
title: "사용자 입력 처리 | Microsoft Docs"
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
  - "사용자 지정 컨트롤[Windows Forms], 코드를 사용하는 키보드 이벤트"
  - "사용자 지정 컨트롤[Windows Forms], 코드를 사용하는 마우스 이벤트"
  - "사용자 지정 컨트롤[Windows Forms], 코드를 사용하는 사용자 입력"
ms.assetid: d9b12787-86f6-4022-8e0f-e12d312c4af2
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# 사용자 입력 처리
이 항목에서는 <xref:System.Windows.Forms.Control?displayProperty=fullName>에서 제공하는 기본 키보드 및 마우스 이벤트에 대해 설명합니다.  이벤트를 처리할 경우 컨트롤 작성자는 이벤트에 대리자를 연결하는 대신 보호된 `On`*EventName* 메서드를 재정의해야 합니다.  이벤트를 검토하려면 [구성 요소에서 이벤트 발생시키기](../Topic/Raising%20Events%20from%20a%20Component.md)를 참조하십시오.  
  
> [!NOTE]
>  이벤트에 데이터가 연결되어 있지 않으면 기본 클래스 <xref:System.EventArgs>의 인스턴스가 `On`*EventName* 메서드에 인수로 전달됩니다.  
  
## 키보드 이벤트  
 컨트롤에서 처리할 수 있는 공용 키보드 이벤트는 <xref:System.Windows.Forms.Control.KeyDown>, <xref:System.Windows.Forms.Control.KeyPress> 및 <xref:System.Windows.Forms.Control.KeyUp>입니다.  
  
|이벤트 이름|재정의할 메서드|이벤트 설명|  
|------------|--------------|------------|  
|`KeyDown`|`void OnKeyDown(KeyEventArgs)`|키를 맨 처음 눌렀을 때만 발생합니다.|  
|`KeyPress`|`void OnKeyPress`<br /><br /> `(KeyPressEventArgs)`|키를 누를 때마다 발생합니다.  키를 누르고 있으면 운영 체제에서 정의한 반복 속도로 <xref:System.Windows.Forms.Control.KeyPress> 이벤트가 발생합니다.|  
|`KeyUp`|`void OnKeyUp(KeyEventArgs)`|키를 놓으면 발생합니다.|  
  
> [!NOTE]
>  키보드 입력을 처리하는 것은 앞에 있는 표의 이벤트를 재정의하는 것보다 복잡하고 이 항목에서 다룰 수 없습니다.  자세한 내용은 [Windows Forms에 사용자 입력](../../../../docs/framework/winforms/user-input-in-windows-forms.md)을 참조하십시오.  
  
## 마우스 이벤트  
 컨트롤에서 처리할 수 있는 마우스 이벤트는 <xref:System.Windows.Forms.Control.MouseDown>, <xref:System.Windows.Forms.Control.MouseEnter>, <xref:System.Windows.Forms.Control.MouseHover>, <xref:System.Windows.Forms.Control.MouseLeave>, <xref:System.Windows.Forms.Control.MouseMove> 및 <xref:System.Windows.Forms.Control.MouseUp>입니다.  
  
|이벤트 이름|재정의할 메서드|이벤트 설명|  
|------------|--------------|------------|  
|`MouseDown`|`void OnMouseDown(MouseEventArgs)`|포인터가 컨트롤 위에 있는 동안 마우스 단추를 누르면 발생합니다.|  
|`MouseEnter`|`void OnMouseEnter(EventArgs)`|포인터가 맨 처음 컨트롤 영역에 들어갈 경우 발생합니다.|  
|`MouseHover`|`void OnMouseHover(EventArgs)`|포인터가 컨트롤을 가리킬 경우 발생합니다.|  
|`MouseLeave`|`void OnMouseLeave(EventArgs)`|포인터가 컨트롤 영역을 벗어날 경우 발생합니다.|  
|`MouseMove`|`void OnMouseMove(MouseEventArgs)`|포인터가 컨트롤 영역에서 이동할 경우 발생합니다.|  
|`MouseUp`|`void OnMouseUp(MouseEventArgs)`|포인터가 컨트롤 위에 있거나 컨트롤 영역을 벗어나 있을 때 마우스 단추를 놓으면 발생합니다.|  
  
 다음 코드 부분에서는 <xref:System.Windows.Forms.Control.MouseDown> 이벤트를 재정의하는 예제를 보여 줍니다.  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#7](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#7)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#7](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#7)]  
  
 다음 코드 부분에서는 <xref:System.Windows.Forms.Control.MouseMove> 이벤트를 재정의하는 예제를 보여 줍니다.  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#8](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#8)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#8](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#8)]  
  
 다음 코드 부분에서는 <xref:System.Windows.Forms.Control.MouseUp> 이벤트를 재정의하는 예제를 보여 줍니다.  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#9](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#9)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#9](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#9)]  
  
 `FlashTrackBar` 샘플의 전체 소스 코드를 보려면 [방법: 진행률을 보여 주는 Windows Forms 컨트롤 만들기](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md)를 참조하십시오.  
  
## 참고 항목  
 [Windows Forms 컨트롤의 이벤트](../../../../docs/framework/winforms/controls/events-in-windows-forms-controls.md)   
 [이벤트 정의](../../../../docs/framework/winforms/controls/defining-an-event-in-windows-forms-controls.md)   
 [이벤트](../../../../docs/standard/events/index.md)   
 [Windows Forms에 사용자 입력](../../../../docs/framework/winforms/user-input-in-windows-forms.md)