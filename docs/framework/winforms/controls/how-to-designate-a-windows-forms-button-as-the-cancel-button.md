---
title: "방법: Windows Forms Button을 취소 단추로 지정"
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
- buttons [Windows Forms], cancel buttons
- Button control [Windows Forms], designating as cancel button
ms.assetid: 252f0834-e54b-44d9-96f7-ee5f50e94f2c
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f3f61828b4c8b65ae984685610d6d8609953376a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-designate-a-windows-forms-button-as-the-cancel-button"></a><span data-ttu-id="cbebe-102">방법: Windows Forms Button을 취소 단추로 지정</span><span class="sxs-lookup"><span data-stu-id="cbebe-102">How to: Designate a Windows Forms Button as the Cancel Button</span></span>
<span data-ttu-id="cbebe-103">모든 Windows Form에서 지정할 수 있습니다는 <xref:System.Windows.Forms.Button> 컨트롤이 취소 단추 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbebe-103">On any Windows Form, you can designate a <xref:System.Windows.Forms.Button> control to be the cancel button.</span></span> <span data-ttu-id="cbebe-104">어느 것을 폼에 다른 컨트롤에 포커스가 ESC 키를 누를 때마다 취소 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbebe-104">A cancel button is clicked whenever the user presses the ESC key, regardless of which other control on the form has the focus.</span></span> <span data-ttu-id="cbebe-105">빠르게 모든 작업에 사용 하지 않고도 작업을 종료할 수 있도록 프로그래밍할 때 일반적으로 이러한 단추를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbebe-105">Such a button is usually programmed to enable the user to quickly exit an operation without committing to any action.</span></span>  
  
### <a name="to-designate-the-cancel-button"></a><span data-ttu-id="cbebe-106">취소 단추를 지정 하려면</span><span class="sxs-lookup"><span data-stu-id="cbebe-106">To designate the cancel button</span></span>  
  
1.  <span data-ttu-id="cbebe-107">폼의 설정 <xref:System.Windows.Forms.Form.CancelButton%2A> 속성을 적절 한 <xref:System.Windows.Forms.Button> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbebe-107">Set the form's <xref:System.Windows.Forms.Form.CancelButton%2A> property to the appropriate <xref:System.Windows.Forms.Button> control.</span></span>  
  
    ```vb  
    Private Sub SetCancelButton(ByVal myCancelBtn As Button)  
       Me.CancelButton = myCancelBtn  
    End Sub  
    ```  
  
    ```csharp  
    private void SetCancelButton(Button myCancelBtn)  
    {  
       this.CancelButton = myCancelBtn;  
    }  
    ```  
  
    ```cpp  
    private:  
       void SetCancelButton(Button ^ myCancelBtn)  
       {  
          this->CancelButton = myCancelBtn;  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="cbebe-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cbebe-108">See Also</span></span>  
 <xref:System.Windows.Forms.Form.CancelButton%2A>  
 [<span data-ttu-id="cbebe-109">Button 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="cbebe-109">Button Control Overview</span></span>](../../../../docs/framework/winforms/controls/button-control-overview-windows-forms.md)  
 [<span data-ttu-id="cbebe-110">Windows Forms Button 컨트롤 선택 방법</span><span class="sxs-lookup"><span data-stu-id="cbebe-110">Ways to Select a Windows Forms Button Control</span></span>](../../../../docs/framework/winforms/controls/ways-to-select-a-windows-forms-button-control.md)  
 [<span data-ttu-id="cbebe-111">방법: Windows Forms 단추 클릭에 응답</span><span class="sxs-lookup"><span data-stu-id="cbebe-111">How to: Respond to Windows Forms Button Clicks</span></span>](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)  
 [<span data-ttu-id="cbebe-112">방법: Windows Forms Button을 적용 단추로 지정</span><span class="sxs-lookup"><span data-stu-id="cbebe-112">How to: Designate a Windows Forms Button as the Accept Button</span></span>](../../../../docs/framework/winforms/controls/how-to-designate-a-windows-forms-button-as-the-accept-button.md)  
 [<span data-ttu-id="cbebe-113">Button 컨트롤</span><span class="sxs-lookup"><span data-stu-id="cbebe-113">Button Control</span></span>](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)
