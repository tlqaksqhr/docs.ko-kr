---
title: '방법: DataRepeater 컨트롤의 레이아웃 변경(Visual Studio)'
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataRepeater, changing layout style
- DataRepeater, changing orientation
ms.assetid: 33aa8fd5-ac63-4bd0-ba13-8c2ab17e7824
ms.openlocfilehash: fa780ee40171143c17b5bdbda4a97179ed5f2151
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33590844"
---
# <a name="how-to-change-the-layout-of-a-datarepeater-control-visual-studio"></a><span data-ttu-id="00b9a-102">방법: DataRepeater 컨트롤의 레이아웃 변경(Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="00b9a-102">How to: Change the Layout of a DataRepeater Control (Visual Studio)</span></span>
<span data-ttu-id="00b9a-103"><xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 컨트롤 (가로 스크롤 항목) 가로 또는 세로 방향 (세로 스크롤 항목)에 표시할 수 방향입니다.</span><span class="sxs-lookup"><span data-stu-id="00b9a-103">The <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control can be displayed in either a vertical (items scroll vertically) or horizontal (items scroll horizontally) orientation.</span></span> <span data-ttu-id="00b9a-104">디자인 타임 또는 런타임 시 방향을 변경 하 여 변경할 수 있습니다는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="00b9a-104">You can change the orientation at design time or at run time by changing the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> property.</span></span> <span data-ttu-id="00b9a-105">변경 하는 경우는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> 런타임 시 속성을 할 수 있습니다 크기를 조정 하려면는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> 고 자식 컨트롤의 위치를 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="00b9a-105">If you change the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> property at run time, you may also want to resize the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> and reposition the child controls.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="00b9a-106">에 컨트롤의 위치를 변경 하는 경우는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> 런타임 시 호출 해야 합니다는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.BeginResetItemTemplate%2A> 및 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.EndResetItemTemplate%2A> 메서드의 컨트롤의 위치를 변경 하는 코드 블록의 시작과 끝에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00b9a-106">If you reposition controls on the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> at run time, you will need to call the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.BeginResetItemTemplate%2A> and <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.EndResetItemTemplate%2A> methods at the beginning and end of the code block that repositions the controls.</span></span>  
  
### <a name="to-change-the-layout-at-design-time"></a><span data-ttu-id="00b9a-107">디자인 타임에 레이아웃을 변경 하려면</span><span class="sxs-lookup"><span data-stu-id="00b9a-107">To change the layout at design time</span></span>  
  
1.  <span data-ttu-id="00b9a-108">Windows Forms 디자이너에서 선택 된 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="00b9a-108">In the Windows Forms Designer, select the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="00b9a-109">외부 테두리를 선택 해야 합니다는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 컨트롤 위쪽에 없는 컨트롤의 아래쪽 영역에서을 클릭 하 여 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> 영역입니다.</span><span class="sxs-lookup"><span data-stu-id="00b9a-109">You must select the outer border of the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control by clicking in the lower region of the control, not in the upper <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> region.</span></span>  
  
2.  <span data-ttu-id="00b9a-110">속성 창에서 설정 된 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> 속성을 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles.Vertical> 또는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles.Horizontal>합니다.</span><span class="sxs-lookup"><span data-stu-id="00b9a-110">In the Properties window, set the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> property to either <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles.Vertical> or <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles.Horizontal>.</span></span>  
  
### <a name="to-change-the-layout-at-run-time"></a><span data-ttu-id="00b9a-111">런타임 시 레이아웃을 변경 하려면</span><span class="sxs-lookup"><span data-stu-id="00b9a-111">To change the layout at run time</span></span>  
  
1.  <span data-ttu-id="00b9a-112">다음 코드는 단추 또는 메뉴를 추가 `Click` 이벤트 처리기.</span><span class="sxs-lookup"><span data-stu-id="00b9a-112">Add the following code to a button or menu `Click` event handler:</span></span>  
  
     [!code-csharp[VbPowerPacksDataRepeaterLayout#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-change-the-layout-of-a-datarepeater-control-visual-studio_1.cs)]
     [!code-vb[VbPowerPacksDataRepeaterLayout#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-change-the-layout-of-a-datarepeater-control-visual-studio_1.vb)]  
  
2.  <span data-ttu-id="00b9a-113">대부분의 경우에서 크기를 조정 하려면 "예" 섹션에 표시 된 것과 비슷한 코드를 추가 하려면 됩니다는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> 새 방향에 맞게 컨트롤을 다시 정렬 합니다.</span><span class="sxs-lookup"><span data-stu-id="00b9a-113">In most cases, you will want to add code similar to that shown in the Example section to resize the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> and rearrange controls to fit the new orientation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="00b9a-114">예제</span><span class="sxs-lookup"><span data-stu-id="00b9a-114">Example</span></span>  
 <span data-ttu-id="00b9a-115">에 응답 하는 방법을 보여 주는 다음 예제는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyleChanged> 이벤트 처리기에서 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="00b9a-115">The following example shows how to respond to the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyleChanged> event in an event handler.</span></span> <span data-ttu-id="00b9a-116">이 예제를 실행 하려면는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 라는 컨트롤 `DataRepeater1` 폼에 해당 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> 두 개의 <xref:System.Windows.Forms.TextBox> 라는 컨트롤 `TextBox1` 및 `TextBox2`합니다.</span><span class="sxs-lookup"><span data-stu-id="00b9a-116">This example requires that you have a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control named `DataRepeater1` on a form and that its <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> contain two <xref:System.Windows.Forms.TextBox> controls named `TextBox1` and `TextBox2`.</span></span>  
  
 [!code-csharp[VbPowerPacksDataRepeaterLayout#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-change-the-layout-of-a-datarepeater-control-visual-studio_2.cs)]
 [!code-vb[VbPowerPacksDataRepeaterLayout#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-change-the-layout-of-a-datarepeater-control-visual-studio_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="00b9a-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="00b9a-117">See Also</span></span>  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A>  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.BeginResetItemTemplate%2A>  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.EndResetItemTemplate%2A>  
 [<span data-ttu-id="00b9a-118">DataRepeater 컨트롤 소개</span><span class="sxs-lookup"><span data-stu-id="00b9a-118">Introduction to the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="00b9a-119">DataRepeater 컨트롤 문제 해결</span><span class="sxs-lookup"><span data-stu-id="00b9a-119">Troubleshooting the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="00b9a-120">방법: DataRepeater 컨트롤의 모양 변경</span><span class="sxs-lookup"><span data-stu-id="00b9a-120">How to: Change the Appearance of a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)
