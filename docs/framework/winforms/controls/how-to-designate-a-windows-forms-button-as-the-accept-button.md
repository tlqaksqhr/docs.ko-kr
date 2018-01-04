---
title: "방법: Windows Forms 단추를 적용 단추로 지정"
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
- buttons [Windows Forms], default on Windows Forms
- Accept button on Windows Forms
- Button control [Windows Forms], designating as default
- Windows Forms controls, default button on form
ms.assetid: 22cc9da6-b913-4e04-9554-dee443ac5c3a
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 80503cd6fc2fc1c624cdd2aeb1ca3f699ffd9832
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-designate-a-windows-forms-button-as-the-accept-button"></a>방법: Windows Forms 단추를 적용 단추로 지정
모든 Windows Form에서 지정할 수 있습니다는 <xref:System.Windows.Forms.Button> 컨트롤이 기본 단추 라고도 적용 단추로 표시 될 수 있습니다. ENTER 키를 누를 때마다 어느 것을 폼에 다른 컨트롤에 포커스가 기본 단추를 클릭할 됩니다.  
  
> [!NOTE]
>  포커스가 있는 컨트롤은 다른 단추 경우 예외-포커스가 있는 단추를 클릭 합니다 즉,-여러 줄 텍스트 상자 또는 ENTER 키를 트래핑 하는 사용자 지정 컨트롤입니다.  
  
### <a name="to-designate-the-accept-button"></a>적용 단추를 지정 하려면  
  
1.  폼의 설정 <xref:System.Windows.Forms.Form.AcceptButton%2A> 속성을 적절 한 <xref:System.Windows.Forms.Button> 제어 합니다.  
  
    ```vb  
    Private Sub SetDefault(ByVal myDefaultBtn As Button)  
      Me.AcceptButton = myDefaultBtn   
    End Sub  
    ```  
  
    ```csharp  
    private void SetDefault(Button myDefaultBtn)  
    {  
       this.AcceptButton = myDefaultBtn;  
    }  
    ```  
  
    ```cpp  
    private:  
       void SetDefault(Button ^ myDefaultBtn)  
       {  
          this->AcceptButton = myDefaultBtn;  
       }  
    ```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.Form.AcceptButton%2A>  
 [Button 컨트롤 개요](../../../../docs/framework/winforms/controls/button-control-overview-windows-forms.md)  
 [Windows Forms Button 컨트롤 선택 방법](../../../../docs/framework/winforms/controls/ways-to-select-a-windows-forms-button-control.md)  
 [방법: Windows Forms 단추 클릭에 응답](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)  
 [방법: Windows Forms Button을 취소 단추로 지정](../../../../docs/framework/winforms/controls/how-to-designate-a-windows-forms-button-as-the-cancel-button.md)  
 [Button 컨트롤](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)
