---
title: ToolTip 구성 요소 개요(Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- ToolTip
helpviewer_keywords:
- tooltips [Windows Forms], about tooltips
- ToolTip component [Windows Forms], about ToolTip component
ms.assetid: 3fbc6f08-c882-4acd-a960-a08efe3c7e6e
ms.openlocfilehash: e31bb1169eeedd85a92e3bf96318623696020f9b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33535540"
---
# <a name="tooltip-component-overview-windows-forms"></a>ToolTip 구성 요소 개요(Windows Forms)
Windows Forms <xref:System.Windows.Forms.ToolTip> 구성 요소는 사용자가 컨트롤을 가리킬 때 텍스트를 표시합니다. 도구 설명은 모든 컨트롤에 연결될 수 있습니다. 이 구성 요소의 사용 예: 폼에 공간을 절약 하려면 단추에 작은 아이콘을 표시 하 수 단추의 기능을 설명 하는 도구 설명을 사용 합니다.  
  
## <a name="working-with-the-tooltip-component"></a>ToolTip 구성 요소 사용  
 A <xref:System.Windows.Forms.ToolTip> 구성 요소를 제공는 `ToolTip` Windows Form 또는 다른 컨테이너에 여러 컨트롤에는 속성입니다. 예를 들어 하나를 저장 하는 경우 <xref:System.Windows.Forms.ToolTip> 폼에 구성 요소에 대 한 "여기에 이름을 입력"를 표시할 수 있습니다는 <xref:System.Windows.Forms.TextBox> 제어 하 고 "여기를 클릭 ब ा ळ"에 대 한는 <xref:System.Windows.Forms.Button> 제어 합니다.  
  
 주요 메서드는 <xref:System.Windows.Forms.ToolTip> 구성 요소는 <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> 및 <xref:System.Windows.Forms.ToolTip.GetToolTip%2A>합니다. 사용할 수는 <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> 메서드를 컨트롤에 표시할 도구 설명을 설정 합니다. 자세한 내용은 참조 [하는 방법: 디자인 타임에 Windows Form의 컨트롤에 대 한 도구 설명을 설정](../../../../docs/framework/winforms/controls/how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md)합니다. 주요 속성은 <xref:System.Windows.Forms.ToolTip.Active%2A>로 설정 해야 `true` 나타날 도구 설명에 대 한 및 <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A>, 도구 설명 문자열이 표시 되는 시간의 길이 설정 하는, 사용자 표시 도구 설명 컨트롤에서 가리켜야 기간 및 긴 것 방법 다음 도구 설명 창이 나타날을 사용 합니다. 자세한 내용은 참조 [하는 방법: Windows Forms ToolTip 구성 요소의 지연 변경](../../../../docs/framework/winforms/controls/how-to-change-the-delay-of-the-windows-forms-tooltip-component.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.ToolTip>  
 [방법: 디자인 타임에 Windows Form의 컨트롤에 도구 설명 설정](../../../../docs/framework/winforms/controls/how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md)  
 [방법: Windows Forms ToolTip 구성 요소의 지연 변경](../../../../docs/framework/winforms/controls/how-to-change-the-delay-of-the-windows-forms-tooltip-component.md)
