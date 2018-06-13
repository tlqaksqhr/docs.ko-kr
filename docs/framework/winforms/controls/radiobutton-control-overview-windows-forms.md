---
title: RadioButton 컨트롤 개요(Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- RadioButton
helpviewer_keywords:
- RadioButton control [Windows Forms], about RadioButton control
- RadioButton control [Windows Forms], determining state
- radio buttons [Windows Forms], determining state
- radio buttons [Windows Forms], about radio buttons
ms.assetid: cd11f0c2-d098-4022-adf9-1455bc166a13
ms.openlocfilehash: 397808c055fd5ba5e8a73d47dfc7fee6c0cf2975
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33540083"
---
# <a name="radiobutton-control-overview-windows-forms"></a>RadioButton 컨트롤 개요(Windows Forms)
Windows Forms <xref:System.Windows.Forms.RadioButton> 컨트롤 사용자에 게 한 상호 배타적인 두 개 이상의 옵션 집합을 제공 합니다. 라디오 단추 및 확인란 유사한 기능 나타날 수 있습니다는 중요 한 차이점이: 동일한 그룹에 다른 라디오 단추도 선택할 수 없는 사용자가 라디오 단추를 선택 합니다. 반면에 임의 개수의 확인란을 선택할 수 있습니다. 라디오 단추 그룹 사용자 지정, "여기 하나만 선택할 수 있는 선택 항목 집합이".  
  
## <a name="using-the-control"></a>컨트롤을 사용 하 여  
 때는 <xref:System.Windows.Forms.RadioButton> 컨트롤을 클릭 하 고, 해당 <xref:System.Windows.Forms.RadioButton.Checked%2A> 속성이로 설정 되어 `true` 및 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기가 호출 됩니다. <xref:System.Windows.Forms.RadioButton.CheckedChanged> 이벤트가 발생할 때의 값은 <xref:System.Windows.Forms.RadioButton.Checked%2A> 속성 변경 합니다. 경우는 <xref:System.Windows.Forms.RadioButton.AutoCheck%2A> 속성이 `true` (기본값) 라디오 단추를 선택 하면 그룹의 다른 모든 자동으로 지워집니다. 이 속성은 대개로 설정 `false` 선택한 라디오 단추가 있는지 유효성 검사 코드를 사용 하는 경우 허용 되는 옵션입니다. 으로 설정 된 컨트롤에 표시 되는 텍스트는 <xref:System.Windows.Forms.Control.Text%2A> 속성 선택 키를 표시할 수 있습니다. 선택 키를 선택 하면 컨트롤을 함께 ALT 키를 눌러 "클릭" 수 있습니다. 자세한 내용은 참조 [하는 방법: 만들 액세스 키에 대 한 Windows Forms 컨트롤](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md) 및 [하는 방법: Windows Forms 컨트롤에서 텍스트 표시 설정](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md)합니다.  
  
 <xref:System.Windows.Forms.RadioButton> 제어 하는 경우 눌러진을 선택 된 것으로 표시 되는 명령 단추 처럼 표시는 <xref:System.Windows.Forms.RadioButton.Appearance%2A> 속성이 <xref:System.Windows.Forms.Appearance.Button>합니다. 라디오 단추를 사용 하 여 이미지를 표시할 수도 있습니다는 <xref:System.Windows.Forms.ButtonBase.Image%2A> 및 <xref:System.Windows.Forms.ButtonBase.ImageList%2A> 속성입니다. 자세한 내용은 참조 [하는 방법: Windows Forms 컨트롤에서 이미지 표시 설정](../../../../docs/framework/winforms/controls/how-to-set-the-image-displayed-by-a-windows-forms-control.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.RadioButton>  
 [Panel 컨트롤 개요](../../../../docs/framework/winforms/controls/panel-control-overview-windows-forms.md)  
 [GroupBox 컨트롤 개요](../../../../docs/framework/winforms/controls/groupbox-control-overview-windows-forms.md)  
 [CheckBox 컨트롤 개요](../../../../docs/framework/winforms/controls/checkbox-control-overview-windows-forms.md)  
 [방법: Windows Forms 컨트롤에 대한 선택키 만들기](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md)  
 [방법: Windows Forms 컨트롤에서 표시하는 텍스트 설정](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md)  
 [방법: 기능별로 Windows Forms RadioButton 컨트롤 그룹화](../../../../docs/framework/winforms/controls/how-to-group-windows-forms-radiobutton-controls-to-function-as-a-set.md)  
 [RadioButton 컨트롤](../../../../docs/framework/winforms/controls/radiobutton-control-windows-forms.md)
