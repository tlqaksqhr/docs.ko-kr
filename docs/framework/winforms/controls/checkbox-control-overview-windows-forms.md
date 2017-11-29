---
title: "CheckBox 컨트롤 개요(Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CheckBox
helpviewer_keywords:
- CheckBox control [Windows Forms], about CheckBox control
- data binding [Windows Forms], checkbox controls
- check boxes [Windows Forms], about check boxes
ms.assetid: 085a4e0b-9046-473f-b141-d0edddfb2ebb
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a154a3f639102e3f3e2acd62626379e12bbd1344
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="checkbox-control-overview-windows-forms"></a><span data-ttu-id="1032d-102">CheckBox 컨트롤 개요(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="1032d-102">CheckBox Control Overview (Windows Forms)</span></span>
<span data-ttu-id="1032d-103">Windows Forms <xref:System.Windows.Forms.CheckBox> 컨트롤은 특정 조건이 설정 또는 해제되었는지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1032d-103">The Windows Forms <xref:System.Windows.Forms.CheckBox> control indicates whether a particular condition is on or off.</span></span> <span data-ttu-id="1032d-104">일반적으로 예/아니요 또는 True/False 선택을 사용자에게 제공하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1032d-104">It is commonly used to present a Yes/No or True/False selection to the user.</span></span> <span data-ttu-id="1032d-105">확인란 컨트롤을 그룹으로 사용하여 사용자가 하나 이상 선택할 수 있는 여러 선택 항목을 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1032d-105">You can use check box controls in groups to display multiple choices from which the user can select one or more.</span></span>  
  
 <span data-ttu-id="1032d-106">확인란 컨트롤 사용자가 수행한 선택 영역을 나타내는 데 사용 되는 각 한다는 점에서 라디오 단추 컨트롤이 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="1032d-106">The check box control is similar to the radio button control in that each is used to indicate a selection that is made by the user.</span></span> <span data-ttu-id="1032d-107">한 번에 하나의 라디오 단추 그룹에서 선택할 수 있습니다는 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="1032d-107">They differ in that only one radio button in a group can be selected at a time.</span></span> <span data-ttu-id="1032d-108">확인란 컨트롤 임의 개수의 확인란을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1032d-108">With the check box control, however, any number of check boxes may be selected.</span></span>  
  
 <span data-ttu-id="1032d-109">확인란 단순 데이터 바인딩을 사용 하 여 데이터베이스의 요소에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1032d-109">A check box may be connected to elements in a database using simple data binding.</span></span> <span data-ttu-id="1032d-110">사용 하 여 여러 확인란을 그룹화 할 수 있습니다는 <xref:System.Windows.Forms.GroupBox> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="1032d-110">Multiple check boxes may be grouped using the <xref:System.Windows.Forms.GroupBox> control.</span></span> <span data-ttu-id="1032d-111">이 그룹화 된 컨트롤 수 함께 이동할 수의 폼 디자이너에서 때문에 시각적 모양에 대 한 및 사용자 인터페이스 디자인에 대 한 유용한.</span><span class="sxs-lookup"><span data-stu-id="1032d-111">This is useful for visual appearance and also for user interface design, since grouped controls can be moved around together on the form designer.</span></span> <span data-ttu-id="1032d-112">자세한 내용은 참조 [Windows Forms 데이터 바인딩](../../../../docs/framework/winforms/windows-forms-data-binding.md) 및 [GroupBox 컨트롤](../../../../docs/framework/winforms/controls/groupbox-control-windows-forms.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1032d-112">For more information, see [Windows Forms Data Binding](../../../../docs/framework/winforms/windows-forms-data-binding.md) and [GroupBox Control](../../../../docs/framework/winforms/controls/groupbox-control-windows-forms.md).</span></span>  
  
 <span data-ttu-id="1032d-113"><xref:System.Windows.Forms.CheckBox> 컨트롤에는 두 가지 중요 한 속성을 <xref:System.Windows.Forms.CheckBox.Checked%2A> 및 <xref:System.Windows.Forms.CheckBox.CheckState%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="1032d-113">The <xref:System.Windows.Forms.CheckBox> control has two important properties, <xref:System.Windows.Forms.CheckBox.Checked%2A> and <xref:System.Windows.Forms.CheckBox.CheckState%2A>.</span></span> <span data-ttu-id="1032d-114"><xref:System.Windows.Forms.CheckBox.Checked%2A> 속성 중 하나를 반환 합니다. `true` 또는 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="1032d-114">The <xref:System.Windows.Forms.CheckBox.Checked%2A> property returns either `true` or `false`.</span></span> <span data-ttu-id="1032d-115"><xref:System.Windows.Forms.CheckBox.CheckState%2A> 속성 중 하나를 반환 합니다. <xref:System.Windows.Forms.CheckState.Checked> 또는 <xref:System.Windows.Forms.CheckState.Unchecked>; 하거나, 있는 경우는 <xref:System.Windows.Forms.CheckBox.ThreeState%2A> 속성이 `true`, <xref:System.Windows.Forms.CheckBox.CheckState%2A> 반환할 수 있습니다 <xref:System.Windows.Forms.CheckState.Indeterminate>합니다.</span><span class="sxs-lookup"><span data-stu-id="1032d-115">The <xref:System.Windows.Forms.CheckBox.CheckState%2A> property returns either <xref:System.Windows.Forms.CheckState.Checked> or <xref:System.Windows.Forms.CheckState.Unchecked>; or, if the <xref:System.Windows.Forms.CheckBox.ThreeState%2A> property is set to `true`, <xref:System.Windows.Forms.CheckBox.CheckState%2A> may also return <xref:System.Windows.Forms.CheckState.Indeterminate>.</span></span> <span data-ttu-id="1032d-116">비활성화 된 상태에서를 나타내는 옵션을 사용할 수 없으면 흐릿하게는 상자가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1032d-116">In the indeterminate state, the box is displayed with a dimmed appearance to indicate the option is unavailable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1032d-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1032d-117">See Also</span></span>  
 <xref:System.Windows.Forms.CheckBox>  
 [<span data-ttu-id="1032d-118">방법: Windows Forms CheckBox 컨트롤을 사용하여 옵션 설정</span><span class="sxs-lookup"><span data-stu-id="1032d-118">How to: Set Options with Windows Forms CheckBox Controls</span></span>](../../../../docs/framework/winforms/controls/how-to-set-options-with-windows-forms-checkbox-controls.md)  
 [<span data-ttu-id="1032d-119">방법: Windows Forms CheckBox 클릭에 응답</span><span class="sxs-lookup"><span data-stu-id="1032d-119">How to: Respond to Windows Forms CheckBox Clicks</span></span>](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-checkbox-clicks.md)  
 [<span data-ttu-id="1032d-120">CheckBox 컨트롤</span><span class="sxs-lookup"><span data-stu-id="1032d-120">CheckBox Control</span></span>](../../../../docs/framework/winforms/controls/checkbox-control-windows-forms.md)
