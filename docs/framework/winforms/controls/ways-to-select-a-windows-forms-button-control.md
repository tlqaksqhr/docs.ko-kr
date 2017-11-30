---
title: "Windows Forms Button 컨트롤 선택 방법"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Button control [Windows Forms], selecting
ms.assetid: fe2fc058-5118-4f70-b264-6147d64a7a8d
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 08b5359446a80da257f5afec07cc70e3d4aad46b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ways-to-select-a-windows-forms-button-control"></a><span data-ttu-id="25d57-102">Windows Forms Button 컨트롤 선택 방법</span><span class="sxs-lookup"><span data-stu-id="25d57-102">Ways to Select a Windows Forms Button Control</span></span>
<span data-ttu-id="25d57-103">다음과 같은 방법으로 Windows Forms 단추를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25d57-103">A Windows Forms button can be selected in the following ways:</span></span>  
  
-   <span data-ttu-id="25d57-104">마우스를 사용 하 여 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="25d57-104">Use a mouse to click the button.</span></span>  
  
-   <span data-ttu-id="25d57-105">단추의 호출 <xref:System.Windows.Forms.Control.Click> 코드의에서 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="25d57-105">Invoke the button's <xref:System.Windows.Forms.Control.Click> event in code.</span></span>  
  
-   <span data-ttu-id="25d57-106">TAB 키를 누르거나 단추에 포커스를 이동 하 고 스페이스바 또는 ENTER 키를 눌러 단추를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="25d57-106">Move the focus to the button by pressing the TAB key, and then choose the button by pressing the SPACEBAR or ENTER.</span></span>  
  
-   <span data-ttu-id="25d57-107">단추에 대 한 액세스 키 (ALT + 밑줄이 그어진된 문자)를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="25d57-107">Press the access key (ALT + the underlined letter) for the button.</span></span> <span data-ttu-id="25d57-108">선택 키에 대 한 자세한 내용은 참조 [하는 방법: 만들 액세스 키에 대 한 Windows Forms 컨트롤](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="25d57-108">For more information about access keys, see [How to: Create Access Keys for Windows Forms Controls](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md).</span></span>  
  
-   <span data-ttu-id="25d57-109">단추가 폼의 "동의" 단추 경우 ENTER 키를 누르면 선택 단추를 선택, 다른 컨트롤에 포커스가 있는 경우에-다른 단추, 여러 줄 텍스트 상자 또는 enter 키를 트래핑 하는 사용자 지정 컨트롤 다른 제어 하는 경우를 제외 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25d57-109">If the button is the "accept" button of the form, pressing ENTER chooses the button, even if another control has the focus — except if that other control is another button, a multi-line text box, or a custom control that traps the enter key.</span></span>  
  
-   <span data-ttu-id="25d57-110">단추가 폼의 "취소" 단추가 경우 ESC 키를 누르면 선택 단추를 선택, 다른 컨트롤에 포커스가 있는 경우에 합니다.</span><span class="sxs-lookup"><span data-stu-id="25d57-110">If the button is the "cancel" button of the form, pressing ESC chooses the button, even if another control has the focus.</span></span>  
  
-   <span data-ttu-id="25d57-111">호출 된 <xref:System.Windows.Forms.Button.PerformClick%2A> 메서드를 프로그래밍 방식으로 단추를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="25d57-111">Call the <xref:System.Windows.Forms.Button.PerformClick%2A> method to select the button programmatically.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25d57-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="25d57-112">See Also</span></span>  
 [<span data-ttu-id="25d57-113">Button 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="25d57-113">Button Control Overview</span></span>](../../../../docs/framework/winforms/controls/button-control-overview-windows-forms.md)  
 [<span data-ttu-id="25d57-114">방법: Windows Forms 단추 클릭에 응답</span><span class="sxs-lookup"><span data-stu-id="25d57-114">How to: Respond to Windows Forms Button Clicks</span></span>](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)  
 [<span data-ttu-id="25d57-115">Button 컨트롤</span><span class="sxs-lookup"><span data-stu-id="25d57-115">Button Control</span></span>](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)
