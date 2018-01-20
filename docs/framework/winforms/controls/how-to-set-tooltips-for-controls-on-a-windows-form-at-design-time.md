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
ms.openlocfilehash: 28a83a623329a7bf0162bb9feb0dc21bb73611cf
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time"></a><span data-ttu-id="cca52-102">방법: 디자인 타임에 Windows Form의 컨트롤에 도구 설명 설정</span><span class="sxs-lookup"><span data-stu-id="cca52-102">How to: Set ToolTips for Controls on a Windows Form at Design Time</span></span>
<span data-ttu-id="cca52-103">설정할 수 있습니다는 <xref:System.Windows.Forms.ToolTip> 코드에서 또는 Windows Forms 디자이너에서 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="cca52-103">You can set a <xref:System.Windows.Forms.ToolTip> string in code or in the Windows Forms Designer.</span></span> <span data-ttu-id="cca52-104">에 대 한 자세한 내용은 <xref:System.Windows.Forms.ToolTip> 구성 요소 참조 [ToolTip 구성 요소 개요](../../../../docs/framework/winforms/controls/tooltip-component-overview-windows-forms.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="cca52-104">For more information about the <xref:System.Windows.Forms.ToolTip> component, see [ToolTip Component Overview](../../../../docs/framework/winforms/controls/tooltip-component-overview-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cca52-105">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cca52-105">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="cca52-106">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cca52-106">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="cca52-107">자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cca52-107">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-set-a-tooltip-programmatically"></a><span data-ttu-id="cca52-108">프로그래밍 방식으로 도구 설명을 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="cca52-108">To set a ToolTip programmatically</span></span>  
  
1.  <span data-ttu-id="cca52-109">도구 설명을 표시 하는 컨트롤을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="cca52-109">Add the control that will display the ToolTip.</span></span>  
  
2.  <span data-ttu-id="cca52-110">사용 하 여는 <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> 의 메서드는 <xref:System.Windows.Forms.ToolTip> 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="cca52-110">Use the <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> method of the <xref:System.Windows.Forms.ToolTip> component.</span></span>  
  
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
  
### <a name="to-set-a-tooltip-in-the-designer"></a><span data-ttu-id="cca52-111">디자이너에서 도구 설명을 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="cca52-111">To set a ToolTip in the designer</span></span>  
  
1.  <span data-ttu-id="cca52-112">폼에 <xref:System.Windows.Forms.ToolTip> 구성 요소를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="cca52-112">Add a <xref:System.Windows.Forms.ToolTip> component to the form.</span></span>  
  
2.  <span data-ttu-id="cca52-113">도구 설명 표시 되거나 폼에 추가 하는 컨트롤을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cca52-113">Select the control that will display the ToolTip, or add it to the form.</span></span>  
  
3.  <span data-ttu-id="cca52-114">에 **속성** 창의 설정는 **ToolTip1의 도구 설명** 텍스트의 적절 한 문자열로 값입니다.</span><span class="sxs-lookup"><span data-stu-id="cca52-114">In the **Properties** window, set the **ToolTip on ToolTip1** value to an appropriate string of text.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cca52-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cca52-115">See Also</span></span>  
 [<span data-ttu-id="cca52-116">ToolTip 구성 요소 개요</span><span class="sxs-lookup"><span data-stu-id="cca52-116">ToolTip Component Overview</span></span>](../../../../docs/framework/winforms/controls/tooltip-component-overview-windows-forms.md)  
 [<span data-ttu-id="cca52-117">방법: Windows Forms ToolTip 구성 요소의 지연 변경</span><span class="sxs-lookup"><span data-stu-id="cca52-117">How to: Change the Delay of the Windows Forms ToolTip Component</span></span>](../../../../docs/framework/winforms/controls/how-to-change-the-delay-of-the-windows-forms-tooltip-component.md)  
 [<span data-ttu-id="cca52-118">ToolTip 구성 요소</span><span class="sxs-lookup"><span data-stu-id="cca52-118">ToolTip Component</span></span>](../../../../docs/framework/winforms/controls/tooltip-component-windows-forms.md)
