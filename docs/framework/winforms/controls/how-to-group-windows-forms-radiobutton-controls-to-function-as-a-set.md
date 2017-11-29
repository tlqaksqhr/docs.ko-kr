---
title: "방법: 기능별로 Windows Forms RadioButton 컨트롤 그룹화"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- radio buttons [Windows Forms], grouping
- controls [Windows Forms], grouping
- Windows Forms controls, grouping
- RadioButton control [Windows Forms], grouping
ms.assetid: 58f8fe34-50b7-49d8-a2be-c271be3c6b32
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 37d8571624272f62c6ce327b0ed25e082c5cf713
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-group-windows-forms-radiobutton-controls-to-function-as-a-set"></a><span data-ttu-id="fd052-102">방법: 기능별로 Windows Forms RadioButton 컨트롤 그룹화</span><span class="sxs-lookup"><span data-stu-id="fd052-102">How to: Group Windows Forms RadioButton Controls to Function as a Set</span></span>
<span data-ttu-id="fd052-103">Windows Forms <xref:System.Windows.Forms.RadioButton> 컨트롤은 사용자에 게 제공 요소가 포함 된 프로시저 또는 개체에 할당 수 하나만 있는 두 개 이상의 설정 설계 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd052-103">Windows Forms <xref:System.Windows.Forms.RadioButton> controls are designed to give users a choice among two or more settings, of which only one can be assigned to a procedure or object.</span></span> <span data-ttu-id="fd052-104">예를 들어 그룹 <xref:System.Windows.Forms.RadioButton> 컨트롤은 주문에 대 한 패키지 운송 업체의을 표시할 수는 있지만 운송 업체 중 하나에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd052-104">For example, a group of <xref:System.Windows.Forms.RadioButton> controls may display a choice of package carriers for an order, but only one of the carriers will be used.</span></span> <span data-ttu-id="fd052-105">따라서 하나의 <xref:System.Windows.Forms.RadioButton> 한 번에 선택할 수 있습니다, 기능 그룹의 일부인 경우에 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd052-105">Therefore only one <xref:System.Windows.Forms.RadioButton> at a time can be selected, even if it is a part of a functional group.</span></span>  
  
 <span data-ttu-id="fd052-106">와 같은 컨테이너 내 그려 라디오 단추 그룹화는 <xref:System.Windows.Forms.Panel> 컨트롤은 <xref:System.Windows.Forms.GroupBox> 컨트롤 또는 폼입니다.</span><span class="sxs-lookup"><span data-stu-id="fd052-106">You group radio buttons by drawing them inside a container such as a <xref:System.Windows.Forms.Panel> control, a <xref:System.Windows.Forms.GroupBox> control, or a form.</span></span> <span data-ttu-id="fd052-107">폼 될 하나의 그룹에 직접 추가 하는 모든 라디오 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="fd052-107">All radio buttons that are added directly to a form become one group.</span></span> <span data-ttu-id="fd052-108">별도 그룹을 추가 하려면 패널 이나 그룹 상자 배치 해야 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd052-108">To add separate groups, you must place them inside panels or group boxes.</span></span> <span data-ttu-id="fd052-109">패널 또는 그룹 상자에 대 한 자세한 내용은 참조 [Panel 컨트롤 개요](../../../../docs/framework/winforms/controls/panel-control-overview-windows-forms.md) 또는 [GroupBox 컨트롤 개요](../../../../docs/framework/winforms/controls/groupbox-control-overview-windows-forms.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fd052-109">For more information about panels or group boxes, see [Panel Control Overview](../../../../docs/framework/winforms/controls/panel-control-overview-windows-forms.md) or [GroupBox Control Overview](../../../../docs/framework/winforms/controls/groupbox-control-overview-windows-forms.md).</span></span>  
  
### <a name="to-group-radiobutton-controls-as-a-set-to-function-independently-of-other-sets"></a><span data-ttu-id="fd052-110">다른 집합 독립적으로 기능을 집합으로 그룹 RadioButton 컨트롤에</span><span class="sxs-lookup"><span data-stu-id="fd052-110">To group RadioButton controls as a set to function independently of other sets</span></span>  
  
1.  <span data-ttu-id="fd052-111">끌어서는 <xref:System.Windows.Forms.GroupBox> 또는 <xref:System.Windows.Forms.Panel> 에서 제어는 **Windows Forms** 탭에 **도구 상자** 폼입니다.</span><span class="sxs-lookup"><span data-stu-id="fd052-111">Drag a <xref:System.Windows.Forms.GroupBox> or <xref:System.Windows.Forms.Panel> control from the **Windows Forms** tab on the **Toolbox** onto the form.</span></span>  
  
2.  <span data-ttu-id="fd052-112">그리기 <xref:System.Windows.Forms.RadioButton> 컨트롤에 <xref:System.Windows.Forms.GroupBox> 또는 <xref:System.Windows.Forms.Panel> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd052-112">Draw <xref:System.Windows.Forms.RadioButton> controls on the <xref:System.Windows.Forms.GroupBox> or <xref:System.Windows.Forms.Panel> control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd052-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fd052-113">See Also</span></span>  
 <xref:System.Windows.Forms.RadioButton>  
 [<span data-ttu-id="fd052-114">RadioButton 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="fd052-114">RadioButton Control Overview</span></span>](../../../../docs/framework/winforms/controls/radiobutton-control-overview-windows-forms.md)  
 [<span data-ttu-id="fd052-115">Panel 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="fd052-115">Panel Control Overview</span></span>](../../../../docs/framework/winforms/controls/panel-control-overview-windows-forms.md)  
 [<span data-ttu-id="fd052-116">GroupBox 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="fd052-116">GroupBox Control Overview</span></span>](../../../../docs/framework/winforms/controls/groupbox-control-overview-windows-forms.md)  
 [<span data-ttu-id="fd052-117">CheckBox 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="fd052-117">CheckBox Control Overview</span></span>](../../../../docs/framework/winforms/controls/checkbox-control-overview-windows-forms.md)  
 [<span data-ttu-id="fd052-118">RadioButton 컨트롤</span><span class="sxs-lookup"><span data-stu-id="fd052-118">RadioButton Control</span></span>](../../../../docs/framework/winforms/controls/radiobutton-control-windows-forms.md)
