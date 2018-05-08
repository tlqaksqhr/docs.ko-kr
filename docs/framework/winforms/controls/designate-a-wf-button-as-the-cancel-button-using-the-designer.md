---
title: '방법: 디자이너를 사용하여 Windows Forms 단추를 취소 단추로 지정'
ms.date: 03/30/2017
helpviewer_keywords:
- buttons [Windows Forms], cancel buttons
- Button control [Windows Forms], designating as cancel button
ms.assetid: 30e77d9c-d565-4ab5-a84a-62c043af8822
ms.openlocfilehash: e94553a31ecdbf325c12815aa7a782cb68b95f19
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-designate-a-windows-forms-button-as-the-cancel-button-using-the-designer"></a>방법: 디자이너를 사용하여 Windows Forms 단추를 취소 단추로 지정
모든 Windows Form에서 지정할 수 있습니다는 <xref:System.Windows.Forms.Button> 컨트롤이 취소 단추 표시 될 수 있습니다. 어느 것을 폼에 다른 컨트롤에 포커스가 ESC 키를 누를 때마다 취소 단추를 클릭 합니다. 빠르게 모든 작업에 사용 하지 않고도 작업을 종료할 수 있도록 프로그래밍할 때 일반적으로 이러한 단추를 사용 합니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.  
  
### <a name="to-designate-the-cancel-button"></a>취소 단추를 지정 하려면  
  
1.  단추가 포함 된 폼을 선택 합니다.  
  
2.  에 **속성** 창의 설정 양식의 <xref:System.Windows.Forms.Form.CancelButton%2A> 속성을는 <xref:System.Windows.Forms.Button> 컨트롤의 이름입니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.Form.CancelButton%2A>  
 [Button 컨트롤 개요](../../../../docs/framework/winforms/controls/button-control-overview-windows-forms.md)  
 [Windows Forms Button 컨트롤 선택 방법](../../../../docs/framework/winforms/controls/ways-to-select-a-windows-forms-button-control.md)  
 [방법: Windows Forms 단추 클릭에 응답](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)  
 [방법: 디자이너를 사용하여 Windows Forms 단추를 적용 단추로 지정](../../../../docs/framework/winforms/controls/designate-a-wf-button-as-the-accept-button-using-the-designer.md)  
 [Button 컨트롤](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)
