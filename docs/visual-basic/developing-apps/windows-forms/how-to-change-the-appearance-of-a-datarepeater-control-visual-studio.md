---
title: "방법: DataRepeater 컨트롤의 모양 변경(Visual Studio)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataRepeater, customizing
- DataRepeater, changing run time appearance
ms.assetid: 2af6dfce-760b-489e-b863-8da967f315c3
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 585ff4c942185f3199fe6e9e47a4ebd9f1f0a478
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-change-the-appearance-of-a-datarepeater-control-visual-studio"></a><span data-ttu-id="d8675-102">방법: DataRepeater 컨트롤의 모양 변경(Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="d8675-102">How to: Change the Appearance of a DataRepeater Control (Visual Studio)</span></span>
<span data-ttu-id="d8675-103">모양을 변경할 수 있습니다는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 속성을 설정 하 여 디자인 타임 또는 런타임에 처리 하 여 컨트롤의 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="d8675-103">You can change the appearance of a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control at design time by setting properties or at run time by handling the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> event.</span></span>  
  
 <span data-ttu-id="d8675-104">컨트롤의 항목 템플릿 섹션을 선택한 경우 디자인 타임에 설정 된 속성 각각에 대해 반복 됩니다 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> 런타임 시.</span><span class="sxs-lookup"><span data-stu-id="d8675-104">Properties that you set at design time when the item template section of the control is selected will be repeated for each <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> at run time.</span></span> <span data-ttu-id="d8675-105">모양 관련 속성의는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 런타임 시 컨테이너의 일부 경우에만 남아 처리 되지 않는 컨트롤 자체는 표시 됩니다 (경우에 예를 들어는 <xref:System.Windows.Forms.Control.Padding%2A> 속성은 큰 값으로).</span><span class="sxs-lookup"><span data-stu-id="d8675-105">Appearance-related properties of the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control itself will be visible at run time only if a part of the container is left uncovered (for example, if the <xref:System.Windows.Forms.Control.Padding%2A> property is set to a large value).</span></span>  
  
 <span data-ttu-id="d8675-106">런타임 시 모양 관련 속성 수 수 조건에 따라 설정할 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8675-106">At run time, appearance-related properties can be set based on conditions.</span></span> <span data-ttu-id="d8675-107">예를 들어 예약 응용 프로그램에서 사용자에 게 경고할 항목 지연 되는 항목의 배경색을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8675-107">For example, in a scheduling application, you might change the background color of an item to warn users when an item is past due.</span></span> <span data-ttu-id="d8675-108">에 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> 이벤트 처리기와 같은 조건문에서 속성을 설정 하는 경우 `If…Then`도 사용 해야는 `Else` 절 조건에 맞지 않을 때 모양을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8675-108">In the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> event handler, if you set a property in a conditional statement such as `If…Then`, you must also use an `Else` clause to specify the appearance when the condition is not met.</span></span>  
  
### <a name="to-change-the-appearance-at-design-time"></a><span data-ttu-id="d8675-109">디자인 타임에 모양을 변경 하려면</span><span class="sxs-lookup"><span data-stu-id="d8675-109">To change the appearance at design time</span></span>  
  
1.  <span data-ttu-id="d8675-110">Windows Forms 디자이너에서의 항목 템플릿 (위쪽) 영역을 선택는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8675-110">In the Windows Forms Designer, select the item template (upper) region of the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
2.  <span data-ttu-id="d8675-111">속성 창에서 속성을 선택 하 고 값을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8675-111">In the Properties window, select a property and change the value.</span></span> <span data-ttu-id="d8675-112">모양에 영향을 주는 공용 속성 포함 <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.BackgroundImage%2A>, <xref:System.Windows.Forms.Panel.BorderStyle%2A>, 및 <xref:System.Windows.Forms.Control.ForeColor%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="d8675-112">Common properties that affect appearance include <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.BackgroundImage%2A>, <xref:System.Windows.Forms.Panel.BorderStyle%2A>, and <xref:System.Windows.Forms.Control.ForeColor%2A>.</span></span>  
  
### <a name="to-change-the-appearance-at-run-time"></a><span data-ttu-id="d8675-113">런타임 시 모양을 변경 하려면</span><span class="sxs-lookup"><span data-stu-id="d8675-113">To change the appearance at run time</span></span>  
  
1.  <span data-ttu-id="d8675-114">코드 편집기의 이벤트 드롭다운 목록에서 **DrawItem**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d8675-114">In the Code Editor, in the Event drop-down list, click **DrawItem**.</span></span>  
  
2.  <span data-ttu-id="d8675-115">에 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> 이벤트 처리기 속성을 설정 하는 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8675-115">In the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> event handler, add code to set the properties:</span></span>  
  
     [!code-csharp[VbPowerPacksDataRepeaterAppearance#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio_1.cs)]
     [!code-vb[VbPowerPacksDataRepeaterAppearance#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="d8675-116">예제</span><span class="sxs-lookup"><span data-stu-id="d8675-116">Example</span></span>  
 <span data-ttu-id="d8675-117">에 대 한 몇 가지 일반적인 사용자 지정의 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 다른 색 및 조건에 따라 필드의 색 변경 행을 표시 하는 컨트롤 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8675-117">Some common customizations for the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control include displaying the rows in alternating colors and changing the color of a field based on a condition.</span></span> <span data-ttu-id="d8675-118">다음 예제에서는 이러한 사용자 지정을 수행 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d8675-118">The following example shows how to perform these customizations.</span></span> <span data-ttu-id="d8675-119">이 예에서는 있다고 가정는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Northwind 데이터베이스의 Products 테이블에 바인딩되는 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="d8675-119">This example assumes that you have a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control that is bound to the Products table in the Northwind database.</span></span>  
  
 [!code-vb[VbPowerPacksDataRepeaterAlternateBackColor#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio_2.vb)]
 [!code-csharp[VbPowerPacksDataRepeaterAlternateBackColor#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio_2.cs)]  
  
 <span data-ttu-id="d8675-120">참고 모두 이러한 사용자 지정에 대 한 조건의 양쪽 모두에 대 한 속성을 설정 하는 코드를 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8675-120">Note that for both of these customizations, you must provide code to set the properties for both sides of the condition.</span></span> <span data-ttu-id="d8675-121">지정 하지 않는 경우는 `Else` 조건, 실행 시 예기치 않은 결과가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8675-121">If you do not specify the `Else` condition, you will see unexpected results at run time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8675-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d8675-122">See Also</span></span>  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem>  
 [<span data-ttu-id="d8675-123">DataRepeater 컨트롤 소개</span><span class="sxs-lookup"><span data-stu-id="d8675-123">Introduction to the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="d8675-124">DataRepeater 컨트롤 문제 해결</span><span class="sxs-lookup"><span data-stu-id="d8675-124">Troubleshooting the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="d8675-125">방법: DataRepeater 컨트롤의 바인딩된 데이터 표시</span><span class="sxs-lookup"><span data-stu-id="d8675-125">How to: Display Bound Data in a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="d8675-126">방법: DataRepeater 컨트롤의 바인딩되지 않은 컨트롤 표시</span><span class="sxs-lookup"><span data-stu-id="d8675-126">How to: Display Unbound Controls in a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="d8675-127">방법: DataRepeater 컨트롤의 항목 머리글 표시</span><span class="sxs-lookup"><span data-stu-id="d8675-127">How to: Display Item Headers in a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-display-item-headers-in-a-datarepeater-control-visual-studio.md)
