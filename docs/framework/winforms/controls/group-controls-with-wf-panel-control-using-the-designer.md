---
title: '방법: 디자이너에서 Windows Forms 패널 컨트롤을 사용하여 컨트롤 그룹화'
ms.date: 03/30/2017
helpviewer_keywords:
- Panel control [Windows Forms], grouping controls
- controls [Windows Forms], grouping
- Windows Forms controls, grouping
ms.assetid: 7e1cd708-fdb1-49d8-9ca2-5640b276bf2e
ms.openlocfilehash: 1cf4519a9aaaa1c4f0df321ab38c3f543c87b2a2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33525625"
---
# <a name="how-to-group-controls-with-the-windows-forms-panel-control-using-the-designer"></a><span data-ttu-id="4d40b-102">방법: 디자이너에서 Windows Forms 패널 컨트롤을 사용하여 컨트롤 그룹화</span><span class="sxs-lookup"><span data-stu-id="4d40b-102">How to: Group Controls with the Windows Forms Panel Control Using the Designer</span></span>
<span data-ttu-id="4d40b-103">Windows Forms <xref:System.Windows.Forms.Panel> 컨트롤은 다른 컨트롤을 그룹화 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d40b-103">Windows Forms <xref:System.Windows.Forms.Panel> controls are used to group other controls.</span></span> <span data-ttu-id="4d40b-104">컨트롤을 그룹화 하는 방법은 세 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d40b-104">There are three reasons to group controls.</span></span> <span data-ttu-id="4d40b-105">하나는 시각적으로 관련 된 일반 사용자 인터페이스;에 대 한 폼 요소 그룹화 프로그래밍 방식으로 그룹화, 라디오 단추의 예를 들어 다른 스냅숏이 마지막은 디자인 타임에 컨트롤을 한 단위로 이동입니다.</span><span class="sxs-lookup"><span data-stu-id="4d40b-105">One is visual grouping of related form elements for a clear user interface; another is programmatic grouping, of radio buttons for example; the last is for moving the controls as a unit at design time.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4d40b-106">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d40b-106">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="4d40b-107">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4d40b-107">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="4d40b-108">자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4d40b-108">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-create-a-group-of-controls"></a><span data-ttu-id="4d40b-109">컨트롤의 그룹을 만들려면</span><span class="sxs-lookup"><span data-stu-id="4d40b-109">To create a group of controls</span></span>  
  
1.  <span data-ttu-id="4d40b-110">끌어서는 <xref:System.Windows.Forms.Panel> 에서 제어는 **Windows Forms** 폼으로 도구 상자 탭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d40b-110">Drag a <xref:System.Windows.Forms.Panel> control from the **Windows Forms** tab of the Toolbox onto a form.</span></span>  
  
2.  <span data-ttu-id="4d40b-111">패널 내부 각 그리기 패널에 다른 컨트롤을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d40b-111">Add other controls to the panel, drawing each inside the panel.</span></span>  
  
     <span data-ttu-id="4d40b-112">패널에 포함 하려는 기존 컨트롤을 사용 하는 경우에 모든 컨트롤에 선택 클립보드에 잘라낸 수 있습니다는 <xref:System.Windows.Forms.Panel> 컨트롤을 선택한 다음 패널에 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="4d40b-112">If you have existing controls that you want to enclose in a panel, you can select all the controls, cut them to the Clipboard, select the <xref:System.Windows.Forms.Panel> control, and then paste them into the panel.</span></span> <span data-ttu-id="4d40b-113">패널에 직접를 끌어 올 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d40b-113">You can also drag them into the panel.</span></span>  
  
3.  <span data-ttu-id="4d40b-114">(선택 사항) 패널에 테두리를 추가 하려면 설정 해당 <xref:System.Windows.Forms.BorderStyle> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="4d40b-114">(Optional) If you want to add a border to a panel, set its <xref:System.Windows.Forms.BorderStyle> property.</span></span> <span data-ttu-id="4d40b-115">장소: <xref:System.Windows.Forms.BorderStyle.Fixed3D>, <xref:System.Windows.Forms.BorderStyle.FixedSingle>, 및 <xref:System.Windows.Forms.BorderStyle.None>합니다.</span><span class="sxs-lookup"><span data-stu-id="4d40b-115">There are three choices: <xref:System.Windows.Forms.BorderStyle.Fixed3D>, <xref:System.Windows.Forms.BorderStyle.FixedSingle>, and <xref:System.Windows.Forms.BorderStyle.None>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d40b-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4d40b-116">See Also</span></span>  
 [<span data-ttu-id="4d40b-117">Panel 컨트롤</span><span class="sxs-lookup"><span data-stu-id="4d40b-117">Panel Control</span></span>](../../../../docs/framework/winforms/controls/panel-control-windows-forms.md)  
 [<span data-ttu-id="4d40b-118">Panel 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="4d40b-118">Panel Control Overview</span></span>](../../../../docs/framework/winforms/controls/panel-control-overview-windows-forms.md)  
 [<span data-ttu-id="4d40b-119">방법: 패널의 배경 설정</span><span class="sxs-lookup"><span data-stu-id="4d40b-119">How to: Set the Background of a Panel</span></span>](../../../../docs/framework/winforms/controls/how-to-set-the-background-of-a-windows-forms-panel.md)
