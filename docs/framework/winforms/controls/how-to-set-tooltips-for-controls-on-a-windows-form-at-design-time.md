---
title: "방법: 디자인 타임에 Windows Form의 컨트롤에 도구 설명 설정"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- tooltips [Windows Forms], for controls
- examples [Windows Forms], tooltips
ms.assetid: c4b60637-4c0a-44c2-a103-f66dff887936
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b296dc6ce929733d6e076cfa676ea6ab5624f45c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time"></a>방법: 디자인 타임에 Windows Form의 컨트롤에 도구 설명 설정
설정할 수 있습니다는 <xref:System.Windows.Forms.ToolTip> 코드에서 또는 Windows Forms 디자이너에서 문자열입니다. 에 대 한 자세한 내용은 <xref:System.Windows.Forms.ToolTip> 구성 요소 참조 [ToolTip 구성 요소 개요](../../../../docs/framework/winforms/controls/tooltip-component-overview-windows-forms.md)합니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.  
  
### <a name="to-set-a-tooltip-programmatically"></a>프로그래밍 방식으로 도구 설명을 설정 하려면  
  
1.  도구 설명을 표시 하는 컨트롤을 추가 합니다.  
  
2.  사용 하 여는 <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> 의 메서드는 <xref:System.Windows.Forms.ToolTip> 구성 요소입니다.  
  
    ```vb  
    ' In this example, Button1 is the control to display the ToolTip.  
    ToolTip1.SetToolTip(Button1, "Save changes")  
    ```  
  
    ```csharp  
    // In this example, button1 is the control to display the ToolTip.  
    toolTip1.SetToolTip(button1, "Save changes");  
    ```  
  
    ```cpp  
    // In this example, button1 is the control to display the ToolTip.  
    toolTip1->SetToolTip(button1, "Save changes");  
    ```  
  
### <a name="to-set-a-tooltip-in-the-designer"></a>디자이너에서 도구 설명을 설정 하려면  
  
1.  폼에 <xref:System.Windows.Forms.ToolTip> 구성 요소를 추가합니다.  
  
2.  도구 설명 표시 되거나 폼에 추가 하는 컨트롤을 선택 합니다.  
  
3.  에 **속성** 창의 설정는 **ToolTip1의 도구 설명** 텍스트의 적절 한 문자열로 값입니다.  
  
## <a name="see-also"></a>참고 항목  
 [ToolTip 구성 요소 개요](../../../../docs/framework/winforms/controls/tooltip-component-overview-windows-forms.md)  
 [방법: Windows Forms ToolTip 구성 요소의 지연 변경](../../../../docs/framework/winforms/controls/how-to-change-the-delay-of-the-windows-forms-tooltip-component.md)  
 [ToolTip 구성 요소](../../../../docs/framework/winforms/controls/tooltip-component-windows-forms.md)
