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
# <a name="how-to-designate-a-windows-forms-button-as-the-accept-button-using-the-designer"></a><span data-ttu-id="d3345-102">방법: 디자이너를 사용하여 Windows Forms 단추를 적용 단추로 지정</span><span class="sxs-lookup"><span data-stu-id="d3345-102">How to: Designate a Windows Forms Button as the Accept Button Using the Designer</span></span>
<span data-ttu-id="d3345-103">모든 Windows Form에서 지정할 수 있습니다는 <xref:System.Windows.Forms.Button> 컨트롤이 기본 단추 라고도 적용 단추로 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3345-103">On any Windows Form, you can designate a <xref:System.Windows.Forms.Button> control to be the accept button, also known as the default button.</span></span> <span data-ttu-id="d3345-104">ENTER 키를 누를 때마다 어느 것을 폼에 다른 컨트롤에 포커스가 기본 단추를 클릭할 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3345-104">Whenever the user presses the ENTER key, the default button is clicked regardless of which other control on the form has the focus.</span></span> <span data-ttu-id="d3345-105">포커스가 있는 컨트롤은 다른 단추 경우 예외-포커스가 있는 단추를 클릭 합니다 즉,-여러 줄 텍스트 상자 또는 ENTER 키를 트래핑 하는 사용자 지정 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="d3345-105">The exceptions to this are when the control with focus is another button — in that case, the button with the focus will be clicked — or a multiline text box, or a custom control that traps the ENTER key.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d3345-106">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3345-106">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="d3345-107">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d3345-107">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="d3345-108">자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d3345-108">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-designate-the-accept-button"></a><span data-ttu-id="d3345-109">적용 단추를 지정 하려면</span><span class="sxs-lookup"><span data-stu-id="d3345-109">To designate the accept button</span></span>  
  
1.  <span data-ttu-id="d3345-110">단추가 포함 된 폼을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3345-110">Select the form on which the button resides.</span></span>  
  
2.  <span data-ttu-id="d3345-111">에 **속성** 창의 설정 양식의 <xref:System.Windows.Forms.Form.AcceptButton%2A> 속성을는 <xref:System.Windows.Forms.Button> 컨트롤의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d3345-111">In the **Properties** window, set the form's <xref:System.Windows.Forms.Form.AcceptButton%2A> property to the <xref:System.Windows.Forms.Button> control's name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3345-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d3345-112">See Also</span></span>  
 <xref:System.Windows.Forms.Form.AcceptButton%2A>  
 [<span data-ttu-id="d3345-113">Button 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="d3345-113">Button Control Overview</span></span>](../../../../docs/framework/winforms/controls/button-control-overview-windows-forms.md)  
 [<span data-ttu-id="d3345-114">Windows Forms Button 컨트롤 선택 방법</span><span class="sxs-lookup"><span data-stu-id="d3345-114">Ways to Select a Windows Forms Button Control</span></span>](../../../../docs/framework/winforms/controls/ways-to-select-a-windows-forms-button-control.md)  
 [<span data-ttu-id="d3345-115">방법: Windows Forms 단추 클릭에 응답</span><span class="sxs-lookup"><span data-stu-id="d3345-115">How to: Respond to Windows Forms Button Clicks</span></span>](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)  
 [<span data-ttu-id="d3345-116">방법: 디자이너를 사용하여 Windows Forms 단추를 취소 단추로 지정</span><span class="sxs-lookup"><span data-stu-id="d3345-116">How to: Designate a Windows Forms Button as the Cancel Button Using the Designer</span></span>](../../../../docs/framework/winforms/controls/designate-a-wf-button-as-the-cancel-button-using-the-designer.md)  
 [<span data-ttu-id="d3345-117">Button 컨트롤</span><span class="sxs-lookup"><span data-stu-id="d3345-117">Button Control</span></span>](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)
