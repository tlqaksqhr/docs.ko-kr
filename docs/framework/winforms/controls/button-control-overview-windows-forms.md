---
title: "Button 컨트롤 개요(Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: Button
helpviewer_keywords:
- Button control [Windows Forms], about Button control
- buttons [Windows Forms], about buttons
ms.assetid: 255b291b-51a9-4a92-a1a4-2400cd82443f
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ff98eb39113a2fa8117d091645ac04526e2983c1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="button-control-overview-windows-forms"></a><span data-ttu-id="b05fc-102">Button 컨트롤 개요(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="b05fc-102">Button Control Overview (Windows Forms)</span></span>
<span data-ttu-id="b05fc-103">사용자는 Windows Forms <xref:System.Windows.Forms.Button> 컨트롤을 클릭하여 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b05fc-103">The Windows Forms <xref:System.Windows.Forms.Button> control allows the user to click it to perform an action.</span></span> <span data-ttu-id="b05fc-104">단추를 클릭하면 눌렀다 놓는 것처럼 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b05fc-104">When the button is clicked, it looks as if it is being pushed in and released.</span></span> <span data-ttu-id="b05fc-105">사용자가 단추를 클릭할 때마다는 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기가 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b05fc-105">Whenever the user clicks a button, the <xref:System.Windows.Forms.Control.Click> event handler is invoked.</span></span> <span data-ttu-id="b05fc-106">에 코드를 넣을 <xref:System.Windows.Forms.Control.Click> 선택한 동작을 수행 하는 이벤트 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="b05fc-106">You place code in the <xref:System.Windows.Forms.Control.Click> event handler to perform any action you choose.</span></span>  
  
 <span data-ttu-id="b05fc-107">단추에 표시 되는 텍스트에 포함 되어는 <xref:System.Windows.Forms.Control.Text%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="b05fc-107">The text displayed on the button is contained in the <xref:System.Windows.Forms.Control.Text%2A> property.</span></span> <span data-ttu-id="b05fc-108">텍스트 단추의 너비를 초과 하는 경우 다음 줄으로 배치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b05fc-108">If your text exceeds the width of the button, it will wrap to the next line.</span></span> <span data-ttu-id="b05fc-109">그러나 클리핑됩니다 컨트롤의 전체 높이 수용할 수 없기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="b05fc-109">However, it will be clipped if the control cannot accommodate its overall height.</span></span> <span data-ttu-id="b05fc-110">자세한 내용은 참조 [하는 방법: Windows Forms 컨트롤에서 텍스트 표시 설정](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b05fc-110">For more information, see [How to: Set the Text Displayed by a Windows Forms Control](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md).</span></span> <span data-ttu-id="b05fc-111"><xref:System.Windows.Forms.Control.Text%2A> 속성에는 사용자가 컨트롤을 함께 ALT 키를 눌러 "클릭" 하도록 허용 하는 액세스 키를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b05fc-111">The <xref:System.Windows.Forms.Control.Text%2A> property can contain an access key, which allows a user to "click" the control by pressing the ALT key with the access key.</span></span> <span data-ttu-id="b05fc-112">자세한 내용은 참조 [하는 방법: 만들 액세스 키에 대 한 Windows Forms 컨트롤](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b05fc-112">For details, see [How to: Create Access Keys for Windows Forms Controls](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md).</span></span> <span data-ttu-id="b05fc-113">텍스트의 표시에 의해 제어 되는 <xref:System.Windows.Forms.Control.Font%2A> 속성 및 <xref:System.Windows.Forms.ButtonBase.TextAlign%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="b05fc-113">The appearance of the text is controlled by the <xref:System.Windows.Forms.Control.Font%2A> property and the <xref:System.Windows.Forms.ButtonBase.TextAlign%2A> property.</span></span>  
  
 <span data-ttu-id="b05fc-114"><xref:System.Windows.Forms.Button> 컨트롤 사용 하 여 이미지를 표시할 수도 <xref:System.Windows.Forms.ButtonBase.Image%2A> 및 <xref:System.Windows.Forms.ButtonBase.ImageList%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="b05fc-114">The <xref:System.Windows.Forms.Button> control can also display images using the <xref:System.Windows.Forms.ButtonBase.Image%2A> and <xref:System.Windows.Forms.ButtonBase.ImageList%2A> properties.</span></span> <span data-ttu-id="b05fc-115">자세한 내용은 참조 [하는 방법: Windows Forms 컨트롤에서 이미지 표시 설정](../../../../docs/framework/winforms/controls/how-to-set-the-image-displayed-by-a-windows-forms-control.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b05fc-115">For more information, see [How to: Set the Image Displayed by a Windows Forms Control](../../../../docs/framework/winforms/controls/how-to-set-the-image-displayed-by-a-windows-forms-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b05fc-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b05fc-116">See Also</span></span>  
 <xref:System.Windows.Forms.Button>  
 [<span data-ttu-id="b05fc-117">방법: Windows Forms 단추 클릭에 응답</span><span class="sxs-lookup"><span data-stu-id="b05fc-117">How to: Respond to Windows Forms Button Clicks</span></span>](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)  
 [<span data-ttu-id="b05fc-118">Windows Forms Button 컨트롤 선택 방법</span><span class="sxs-lookup"><span data-stu-id="b05fc-118">Ways to Select a Windows Forms Button Control</span></span>](../../../../docs/framework/winforms/controls/ways-to-select-a-windows-forms-button-control.md)  
 [<span data-ttu-id="b05fc-119">방법: 디자이너를 사용하여 Windows Forms 단추를 적용 단추로 지정</span><span class="sxs-lookup"><span data-stu-id="b05fc-119">How to: Designate a Windows Forms Button as the Accept Button Using the Designer</span></span>](../../../../docs/framework/winforms/controls/designate-a-wf-button-as-the-accept-button-using-the-designer.md)  
 [<span data-ttu-id="b05fc-120">방법: 디자이너를 사용하여 Windows Forms 단추를 취소 단추로 지정</span><span class="sxs-lookup"><span data-stu-id="b05fc-120">How to: Designate a Windows Forms Button as the Cancel Button Using the Designer</span></span>](../../../../docs/framework/winforms/controls/designate-a-wf-button-as-the-cancel-button-using-the-designer.md)  
 [<span data-ttu-id="b05fc-121">Button 컨트롤</span><span class="sxs-lookup"><span data-stu-id="b05fc-121">Button Control</span></span>](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)
