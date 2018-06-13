---
title: '방법: DataRepeater 컨트롤의 바인딩되지 않은 컨트롤 표시(Visual Studio)'
ms.date: 07/20/2015
helpviewer_keywords:
- DataRepeater, adding unbound controls
- DataRepeater
- displaying unbound data
ms.assetid: f234fa40-5a13-4209-930e-7c5f81e86e66
ms.openlocfilehash: 698e518a4ed10ed6cf14ccafc6833b1acf8752db
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33588108"
---
# <a name="how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio"></a><span data-ttu-id="761ee-102">방법: DataRepeater 컨트롤의 바인딩되지 않은 컨트롤 표시(Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="761ee-102">How to: Display Unbound Controls in a DataRepeater Control (Visual Studio)</span></span>
<span data-ttu-id="761ee-103">바인딩된 컨트롤 이외에 다른 컨트롤을 추가 하려는 한 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>, 정적 레이블 또는 각 항목에 대해 반복 되는 이미지와 같은 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="761ee-103">In addition to bound controls, you may want to add other controls to a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>, such as a static label or an image that is repeated on each item in the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="761ee-104">한 개 이상의 바인딩된 컨트롤에도 있어야는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 또는 아무것도 실행 시 표시 되지 것입니다.</span><span class="sxs-lookup"><span data-stu-id="761ee-104">You must also have at least one bound control on the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> or nothing will be displayed at run time.</span></span>  
  
### <a name="to-add-unbound-controls-to-a-datarepeater"></a><span data-ttu-id="761ee-105">DataRepeater에 바인딩되지 않은 컨트롤을 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="761ee-105">To add unbound controls to a DataRepeater</span></span>  
  
1.  <span data-ttu-id="761ee-106">끌어서는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 에서 제어는 **Visual Basic PowerPacks** 탭에 **도구 상자** 폼 이나 컨테이너 컨트롤로 합니다.</span><span class="sxs-lookup"><span data-stu-id="761ee-106">Drag a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control from the **Visual Basic PowerPacks** tab in the **Toolbox** to a form or container control.</span></span>  
  
2.  <span data-ttu-id="761ee-107">크기를 위치 및 크기 조정 핸들을 끌어서 컨트롤을 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="761ee-107">Drag the sizing and position handles to size and position the control.</span></span>  
  
     <span data-ttu-id="761ee-108">크기 조정 하 고 변경 하 여 컨트롤을 배치할 수도 있습니다는 **크기** 및 **위치** 속성 창에서 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="761ee-108">You can also size and position the control by changing the **Size** and **Position** properties in the Properties window.</span></span>  
  
3.  <span data-ttu-id="761ee-109">데이터 바인딩된 컨트롤을 하나 이상 추가 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="761ee-109">Add at least one data-bound control to the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span> <span data-ttu-id="761ee-110">자세한 내용은 참조 [하는 방법: DataRepeater 컨트롤의 바인딩된 데이터 표시](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="761ee-110">For more information, see [How to: Display Bound Data in a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md).</span></span>  
  
4.  <span data-ttu-id="761ee-111">컨트롤을 끌어는 **도구 상자** 의 항목 템플릿 영역으로는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="761ee-111">Drag a control from the **Toolbox** onto the item template region of the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
     <span data-ttu-id="761ee-112">컨트롤에는 두 개의 사각형 영역을 참고 합니다.</span><span class="sxs-lookup"><span data-stu-id="761ee-112">Note that the control has two rectangular regions.</span></span> <span data-ttu-id="761ee-113">내부 영역은입니다는 *항목 템플릿을*; 서식 파일에 추가 된 컨트롤의 각 항목에 반복 됩니다는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 런타임 시 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="761ee-113">The inner region is the *item template*; controls added to the template will be repeated in each item in the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control at run time.</span></span> <span data-ttu-id="761ee-114">외부 영역은는 *뷰포트*, 여기서 항목이 표시;이 영역에 추가 된 실행 시 표시 되지 것입니다.</span><span class="sxs-lookup"><span data-stu-id="761ee-114">The outer region is the *viewport*, where the items will be displayed; controls that are added to this region will not be displayed at run time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="761ee-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="761ee-115">See Also</span></span>  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
 [<span data-ttu-id="761ee-116">DataRepeater 컨트롤 소개</span><span class="sxs-lookup"><span data-stu-id="761ee-116">Introduction to the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="761ee-117">DataRepeater 컨트롤 문제 해결</span><span class="sxs-lookup"><span data-stu-id="761ee-117">Troubleshooting the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="761ee-118">방법: DataRepeater 컨트롤의 바인딩된 데이터 표시</span><span class="sxs-lookup"><span data-stu-id="761ee-118">How to: Display Bound Data in a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="761ee-119">방법: 두 DataRepeater 컨트롤 (Visual Studio)를 사용 하 여 마스터/세부 폼 만들기</span><span class="sxs-lookup"><span data-stu-id="761ee-119">How to: Create a Master/Detail Form by Using Two DataRepeater Controls (Visual Studio)</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md)  
 [<span data-ttu-id="761ee-120">방법: DataRepeater 컨트롤의 모양 변경</span><span class="sxs-lookup"><span data-stu-id="761ee-120">How to: Change the Appearance of a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)
