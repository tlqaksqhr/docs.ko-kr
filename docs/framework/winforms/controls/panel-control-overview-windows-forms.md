---
title: Panel 컨트롤 개요(Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- Panel
helpviewer_keywords:
- grouping controls [Windows Forms], Panel control
- Panel control [Windows Forms], about Panel control
ms.assetid: b6b83636-2c39-4dad-89d6-f0fa41049a74
ms.openlocfilehash: 1ba766629f923b091459531ce74d28dca4b4ea0f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33539351"
---
# <a name="panel-control-overview-windows-forms"></a>Panel 컨트롤 개요(Windows Forms)
Windows Forms <xref:System.Windows.Forms.Panel> 컨트롤은 다른 컨트롤에 대 한 식별 가능한 그룹화를 제공 하는 데 사용 됩니다. 일반적으로 폼 함수로 세분화 하 패널을 사용 합니다. 예를 들어 어떤 야간 운송 같은 메일링 옵션을 지정 하는 주문 양식과 해야 합니다. 패널에 있는 모든 옵션을 그룹화 하면 오류가 논리 시각적 표시 합니다. 디자인 타임에 컨트롤을 쉽게 이동할 수 있습니다. 모든-이동 하는 경우는 <xref:System.Windows.Forms.Panel> 모든 포함 된 컨트롤이, 너무 제어 합니다. 패널에 그룹화 된 컨트롤을 통해 액세스할 수는 <xref:System.Windows.Forms.Control.Controls%2A> 속성입니다. 이 속성의 컬렉션을 반환 <xref:System.Windows.Forms.Control> 되므로 컨트롤을 캐스팅 해야 일반적으로 인스턴스를 특정 형식으로 이러한 방식으로 검색 합니다.  
  
## <a name="panel-versus-groupbox"></a>GroupBox와 패널  
 <xref:System.Windows.Forms.Panel> 제어는 비슷합니다는 <xref:System.Windows.Forms.GroupBox> 제어; 그러나만 <xref:System.Windows.Forms.Panel> 컨트롤에서 스크롤 막대를 가질 수 있습니다 및만 해당는 <xref:System.Windows.Forms.GroupBox> 컨트롤 캡션을 표시 합니다.  
  
## <a name="key-properties"></a>키 속성  
 스크롤 막대를 표시 하려면 설정는 <xref:System.Windows.Forms.ScrollableControl.AutoScroll%2A> 속성을 `true`합니다. 설정 하 여 패널의 모양을 사용자 지정할 수도 있습니다는 <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.BackgroundImage%2A>, 및 <xref:System.Windows.Forms.Panel.BorderStyle%2A> 속성입니다. 대 한 자세한 내용은 <xref:System.Windows.Forms.Control.BackColor%2A> 및 <xref:System.Windows.Forms.Control.BackgroundImage%2A> 속성 참조 [하는 방법: 패널의 배경 설정](../../../../docs/framework/winforms/controls/how-to-set-the-background-of-a-windows-forms-panel.md)합니다. <xref:System.Windows.Forms.Panel.BorderStyle%2A> 속성 패널 테두리가 표시 되지으로 작성 된 경우를 결정 (<xref:System.Windows.Forms.BorderStyle.None>), 일반 줄 (<xref:System.Windows.Forms.BorderStyle.FixedSingle>), 또는 음영된 선 (<xref:System.Windows.Forms.BorderStyle.Fixed3D>).  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.Panel>  
 [GroupBox 컨트롤](../../../../docs/framework/winforms/controls/groupbox-control-windows-forms.md)  
 [방법: 디자이너에서 Windows Forms 패널 컨트롤을 사용하여 컨트롤 그룹화](../../../../docs/framework/winforms/controls/group-controls-with-wf-panel-control-using-the-designer.md)  
 [방법: 디자이너를 사용하여 Windows Forms 패널의 배경 설정](../../../../docs/framework/winforms/controls/how-to-set-the-background-of-a-windows-forms-panel-using-the-designer.md)
