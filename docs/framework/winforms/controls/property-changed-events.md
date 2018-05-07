---
title: 속성 변경 이벤트
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], property changes (using code)
- properties [Windows Forms], changes
ms.assetid: 268039ec-5aaa-4d76-b902-acccb036c850
ms.openlocfilehash: f4e6a6267df88cdd33a58093f276c6005209f38d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="property-changed-events"></a>속성 변경 이벤트
원하는 경우 라는 속성이 알림을 보내도록 컨트롤 *PropertyName* 명명 된 이벤트를 정의 하는 변경 내용을 *PropertyName* `Changed` 라는 이름의 메서드 `On` *PropertyName* `Changed` 이벤트를 발생 시키는 합니다. 단어를 추가할 Windows Forms의 명명 규칙은 *Changed* 속성의 이름입니다. 속성 변경 이벤트에 대 한 관련된 이벤트 대리자 형식이 <xref:System.EventHandler>, 이벤트 데이터 형식이 고 <xref:System.EventArgs>합니다. 기본 클래스 <xref:System.Windows.Forms.Control> 와 같은 대부분의 속성 변경 이벤트를 정의 <xref:System.Windows.Forms.Control.BackColorChanged>, <xref:System.Windows.Forms.Control.BackgroundImageChanged>, <xref:System.Windows.Forms.Control.FontChanged>, <xref:System.Windows.Forms.Control.LocationChanged>, 등입니다. 이벤트에 대 한 배경 정보를 참조 하십시오. [이벤트](../../../../docs/standard/events/index.md) 및 [Windows Forms 컨트롤의 이벤트](../../../../docs/framework/winforms/controls/events-in-windows-forms-controls.md)합니다.  
  
 속성 변경 이벤트는 변경에 응답 하는 이벤트 처리기를 연결 하는 컨트롤의 소비자 수 있기 때문에 유용 합니다. 컨트롤을 발생 시킨 속성 변경 이벤트에 응답 하는 경우 해당 재정의 `On` *PropertyName* `Changed` 메서드가 아닌 이벤트에 대리자를 연결 합니다. 일반적으로 컨트롤 그리기 화면의의 일부 또는 전부를 다시 그리기 하거나 다른 속성을 업데이트 하 여 속성 변경 이벤트에 응답 합니다.  
  
 다음 예제와 방법을 `FlashTrackBar` 일부에서 상속 된 속성 변경 이벤트에 응답 하는 사용자 지정 컨트롤 <xref:System.Windows.Forms.Control>합니다. 전체 샘플을 참조 하십시오. [하는 방법: Windows Forms 컨트롤을 표시 진행률 만들기](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md)합니다.  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#2)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#2)]  
  
## <a name="see-also"></a>참고 항목  
 [이벤트](../../../../docs/standard/events/index.md)  
 [Windows Forms 컨트롤의 이벤트](../../../../docs/framework/winforms/controls/events-in-windows-forms-controls.md)  
 [Windows Forms 컨트롤의 속성](../../../../docs/framework/winforms/controls/properties-in-windows-forms-controls.md)
