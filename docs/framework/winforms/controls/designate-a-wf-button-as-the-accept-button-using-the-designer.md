---
title: '방법: 디자이너를 사용하여 Windows Forms 단추를 적용 단추로 지정'
ms.date: 03/30/2017
helpviewer_keywords:
- buttons [Windows Forms], default on Windows Forms
- Accept button on Windows Forms
- Button control [Windows Forms], designating as default
- Windows Forms controls, default button on form
ms.assetid: a1da0590-755f-49f2-aca7-609fac6351bf
ms.openlocfilehash: aade1b6e988fc4b43f7ad9cfb58382302c875d37
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33527045"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-accept-button-using-the-designer"></a>방법: 디자이너를 사용하여 Windows Forms 단추를 적용 단추로 지정
모든 Windows Form에서 지정할 수 있습니다는 <xref:System.Windows.Forms.Button> 컨트롤이 기본 단추 라고도 적용 단추로 표시 될 수 있습니다. ENTER 키를 누를 때마다 어느 것을 폼에 다른 컨트롤에 포커스가 기본 단추를 클릭할 됩니다. 포커스가 있는 컨트롤은 다른 단추 경우 예외-포커스가 있는 단추를 클릭 합니다 즉,-여러 줄 텍스트 상자 또는 ENTER 키를 트래핑 하는 사용자 지정 컨트롤입니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.  
  
### <a name="to-designate-the-accept-button"></a>적용 단추를 지정 하려면  
  
1.  단추가 포함 된 폼을 선택 합니다.  
  
2.  에 **속성** 창의 설정 양식의 <xref:System.Windows.Forms.Form.AcceptButton%2A> 속성을는 <xref:System.Windows.Forms.Button> 컨트롤의 이름입니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.Form.AcceptButton%2A>  
 [Button 컨트롤 개요](../../../../docs/framework/winforms/controls/button-control-overview-windows-forms.md)  
 [Windows Forms Button 컨트롤 선택 방법](../../../../docs/framework/winforms/controls/ways-to-select-a-windows-forms-button-control.md)  
 [방법: Windows Forms 단추 클릭에 응답](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)  
 [방법: 디자이너를 사용하여 Windows Forms 단추를 취소 단추로 지정](../../../../docs/framework/winforms/controls/designate-a-wf-button-as-the-cancel-button-using-the-designer.md)  
 [Button 컨트롤](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)
