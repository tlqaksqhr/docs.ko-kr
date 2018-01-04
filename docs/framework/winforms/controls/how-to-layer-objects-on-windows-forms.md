---
title: "방법: Windows Forms에서 개체 계층화"
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
- Windows Forms controls, layering
- controls [Windows Forms], layering
- z order
- controls [Windows Forms], positioning
- z-order
ms.assetid: 1acc4281-2976-4715-86f4-bda68134baaf
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f042816b912a0de643dd1d0f66ddba6d5eff7df2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-layer-objects-on-windows-forms"></a><span data-ttu-id="ccf45-102">방법: Windows Forms에서 개체 계층화</span><span class="sxs-lookup"><span data-stu-id="ccf45-102">How to: Layer Objects on Windows Forms</span></span>
<span data-ttu-id="ccf45-103">복잡 한 사용자 인터페이스를 만들거나 여러 문서 MDI (인터페이스) 폼을 사용할 때 컨트롤과 보다 복잡 한 UI (사용자 인터페이스) 자식 폼 계층화 하려는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="ccf45-103">When you create a complex user interface, or work with a multiple document interface (MDI) form, you will often want to layer both controls and child forms to create more complex user interfaces (UI).</span></span> <span data-ttu-id="ccf45-104">이동 하 고 컨트롤 및 windows 그룹의 컨텍스트 내에서 한 추적을 z 순서를 조작 합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf45-104">To move and keep track of controls and windows within the context of a group, you manipulate their z-order.</span></span> <span data-ttu-id="ccf45-105">*Z 순서* 폼의 z 축 (깊이)와 함께 폼에 컨트롤의 시각적 계층은 합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf45-105">*Z-order* is the visual layering of controls on a form along the form's z-axis (depth).</span></span> <span data-ttu-id="ccf45-106">Z 순서 맨 아래에 있는 창에는 다른 모든 창과 겹칩니다.</span><span class="sxs-lookup"><span data-stu-id="ccf45-106">The window at the top of the z-order overlaps all other windows.</span></span> <span data-ttu-id="ccf45-107">다른 모든 창과 z 순서 맨 아래에 있는 창을 위에 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf45-107">All other windows overlap the window at the bottom of the z-order.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ccf45-108">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ccf45-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="ccf45-109">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf45-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="ccf45-110">자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ccf45-110">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-layer-controls-at-design-time"></a><span data-ttu-id="ccf45-111">디자인 타임에 레이어 컨트롤에</span><span class="sxs-lookup"><span data-stu-id="ccf45-111">To layer controls at design time</span></span>  
  
1.  <span data-ttu-id="ccf45-112">레이어를 하는 컨트롤을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf45-112">Select a control that you want to layer.</span></span>  
  
2.  <span data-ttu-id="ccf45-113">에 **형식** 메뉴에서 **순서**, 클릭 하 고 **앞으로 가져오기** 또는 **맨 뒤로 보내기**합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf45-113">On the **Format** menu, point to **Order**, and then click **Bring To Front** or **Send To Back**.</span></span>  
  
### <a name="to-layer-controls-programmatically"></a><span data-ttu-id="ccf45-114">컨트롤을 프로그래밍 방식으로 계층화</span><span class="sxs-lookup"><span data-stu-id="ccf45-114">To layer controls programmatically</span></span>  
  
-   <span data-ttu-id="ccf45-115">사용 하 여 <xref:System.Windows.Forms.Control.BringToFront%2A> 및 <xref:System.Windows.Forms.Control.SendToBack%2A> 컨트롤의 z 순서를 조작 하는 메서드.</span><span class="sxs-lookup"><span data-stu-id="ccf45-115">Use the <xref:System.Windows.Forms.Control.BringToFront%2A> and <xref:System.Windows.Forms.Control.SendToBack%2A> methods to manipulate the z-order of the controls.</span></span>  
  
     <span data-ttu-id="ccf45-116">예를 들어 경우는 <xref:System.Windows.Forms.TextBox> 컨트롤 `txtFirstName`은 아래 다른 제어 및 중지할 위쪽에, 다음 코드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf45-116">For example, if a <xref:System.Windows.Forms.TextBox> control, `txtFirstName`, is underneath another control and you want to have it on top, use the following code:</span></span>  
  
    ```vb  
    txtFirstName.BringToFront()  
    ```  
  
    ```csharp  
    txtFirstName.BringToFront();  
    ```  
  
    ```cpp  
    txtFirstName->BringToFront();  
    ```  
  
> [!NOTE]
>  <span data-ttu-id="ccf45-117">Windows Forms에서는 *컨트롤 포함*합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf45-117">Windows Forms supports *control containment*.</span></span> <span data-ttu-id="ccf45-118">컨트롤 포함에서는 다양 한의 번호를 비롯 한 포함 하는 컨트롤 내에서 컨트롤 배치 <xref:System.Windows.Forms.RadioButton> 컨트롤 내는 <xref:System.Windows.Forms.GroupBox> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf45-118">Control containment involves placing a number of controls within a containing control, such as a number of <xref:System.Windows.Forms.RadioButton> controls within a <xref:System.Windows.Forms.GroupBox> control.</span></span> <span data-ttu-id="ccf45-119">그런 다음 포함 하는 컨트롤 내에서 컨트롤 계층 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ccf45-119">You can then layer the controls within the containing control.</span></span> <span data-ttu-id="ccf45-120">그룹 상자를 이동 그 안에 포함 되기 때문에 컨트롤을도 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf45-120">Moving the group box moves the controls as well, because they are contained inside it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccf45-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ccf45-121">See Also</span></span>  
 [<span data-ttu-id="ccf45-122">Windows Forms 컨트롤</span><span class="sxs-lookup"><span data-stu-id="ccf45-122">Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/index.md)  
 [<span data-ttu-id="ccf45-123">Windows Forms에서 컨트롤 정렬</span><span class="sxs-lookup"><span data-stu-id="ccf45-123">Arranging Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [<span data-ttu-id="ccf45-124">개별 Windows Forms 컨트롤 레이블 지정 및 바로 가기 제공</span><span class="sxs-lookup"><span data-stu-id="ccf45-124">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)  
 [<span data-ttu-id="ccf45-125">Windows Forms에 사용할 수 있는 컨트롤</span><span class="sxs-lookup"><span data-stu-id="ccf45-125">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 [<span data-ttu-id="ccf45-126">기능별 Windows Forms 컨트롤</span><span class="sxs-lookup"><span data-stu-id="ccf45-126">Windows Forms Controls by Function</span></span>](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)
