---
title: 사용자 입력 처리
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], user input using code
- custom controls [Windows Forms], keyboard events using code
- custom controls [Windows Forms], mouse events using code
ms.assetid: d9b12787-86f6-4022-8e0f-e12d312c4af2
ms.openlocfilehash: a230611bfbb0a7f21a96de22674377887cc93c2d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33527802"
---
# <a name="handling-user-input"></a>사용자 입력 처리
이 항목에서 제공 하는 기본 키보드 및 마우스 이벤트를 설명 <xref:System.Windows.Forms.Control?displayProperty=nameWithType>합니다. 이벤트를 처리할 경우 컨트롤 작성자는 이벤트에 대리자를 연결하는 대신 보호된 `On`*EventName* 메서드를 재정의해야 합니다. 이벤트의 검토는 [구성 요소에서 이벤트 발생](http://msdn.microsoft.com/library/9aebf605-a87d-470b-b7c8-f9abfc8360a0)을 참조하세요.  
  
> [!NOTE]
>  기본 클래스의 인스턴스는 이벤트와 연결 된 데이터가 없는 경우 <xref:System.EventArgs> 에 인수로 전달 되는 `On` *EventName* 메서드.  
  
## <a name="keyboard-events"></a>키보드 이벤트  
 컨트롤을 처리할 수 있는 일반적인 키보드 이벤트는 <xref:System.Windows.Forms.Control.KeyDown>, <xref:System.Windows.Forms.Control.KeyPress>, 및 <xref:System.Windows.Forms.Control.KeyUp>합니다.  
  
|이벤트 이름|재정의할 메서드|이벤트 설명|  
|----------------|------------------------|--------------------------|  
|`KeyDown`|`void OnKeyDown(KeyEventArgs)`|키를 처음 누를 때 발생합니다.|  
|`KeyPress`|`void OnKeyPress`<br /><br /> `(KeyPressEventArgs)`|키를 누를 때마다 발생합니다. 키를 누르고 있으면는 <xref:System.Windows.Forms.Control.KeyPress> 운영 체제에 의해 정의 된 반복 속도에서 이벤트가 발생 합니다.|  
|`KeyUp`|`void OnKeyUp(KeyEventArgs)`|키를 놓으면 발생합니다.|  
  
> [!NOTE]
>  키보드 입력 처리는 앞의 테이블에서 이벤트를 재정의하는 것보다 더 복잡하며 이 항목의 범위를 벗어납니다. 자세한 내용은 [Windows Forms의 사용자 입력](../../../../docs/framework/winforms/user-input-in-windows-forms.md)을 참조하세요.  
  
## <a name="mouse-events"></a>마우스 이벤트  
 마우스 이벤트는 컨트롤에서 처리할 수 <xref:System.Windows.Forms.Control.MouseDown>, <xref:System.Windows.Forms.Control.MouseEnter>, <xref:System.Windows.Forms.Control.MouseHover>, <xref:System.Windows.Forms.Control.MouseLeave>, <xref:System.Windows.Forms.Control.MouseMove>, 및 <xref:System.Windows.Forms.Control.MouseUp>합니다.  
  
|이벤트 이름|재정의할 메서드|이벤트 설명|  
|----------------|------------------------|--------------------------|  
|`MouseDown`|`void OnMouseDown(MouseEventArgs)`|포인터가 컨트롤 위에 있을 때 마우스 단추를 누르면 발생합니다.|  
|`MouseEnter`|`void OnMouseEnter(EventArgs)`|포인터가 컨트롤의 지역에 먼저 들어가면 발생합니다.|  
|`MouseHover`|`void OnMouseHover(EventArgs)`|포인터로 컨트롤을 가리키면 발생합니다.|  
|`MouseLeave`|`void OnMouseLeave(EventArgs)`|포인터가 컨트롤의 지역을 벗어나면 발생합니다.|  
|`MouseMove`|`void OnMouseMove(MouseEventArgs)`|포인터가 컨트롤의 지역에서 이동하면 발생합니다.|  
|`MouseUp`|`void OnMouseUp(MouseEventArgs)`|포인터가 컨트롤 위에 있거나 포인터가 컨트롤의 지역을 벗어나는 동안 마우스 단추를 놓으면 발생합니다.|  
  
 다음 코드는 재정의의 예를 보여 줍니다.는 <xref:System.Windows.Forms.Control.MouseDown> 이벤트입니다.  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#7](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#7)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#7](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#7)]  
  
 다음 코드는 재정의의 예를 보여 줍니다.는 <xref:System.Windows.Forms.Control.MouseMove> 이벤트입니다.  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#8](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#8)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#8](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#8)]  
  
 다음 코드는 재정의의 예를 보여 줍니다.는 <xref:System.Windows.Forms.Control.MouseUp> 이벤트입니다.  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#9](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#9)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#9](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#9)]  
  
 `FlashTrackBar` 샘플의 전체 소스 코드는 [방법: 진행률을 보여 주는 Windows Forms 컨트롤 만들기](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [Windows Forms 컨트롤의 이벤트](../../../../docs/framework/winforms/controls/events-in-windows-forms-controls.md)  
 [이벤트 정의](../../../../docs/framework/winforms/controls/defining-an-event-in-windows-forms-controls.md)  
 [이벤트](../../../../docs/standard/events/index.md)  
 [Windows Forms에 사용자 입력](../../../../docs/framework/winforms/user-input-in-windows-forms.md)
