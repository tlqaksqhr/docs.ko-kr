---
title: '방법: 두 DataRepeater 컨트롤 (Visual Studio)를 사용 하 여 마스터-세부 폼 만들기'
ms.date: 07/20/2015
helpviewer_keywords:
- DataRepeater, master/detail tables
ms.assetid: eec43ae3-05d8-45a1-8d41-3803c6359dbe
ms.openlocfilehash: 84639a5d49a3fa4a8c6845793c39fc8a67c31e02
ms.sourcegitcommit: 70c76a12449439bac0f7a359866be5a0311ce960
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/25/2018
ms.locfileid: "39245541"
---
# <a name="how-to-create-a-masterdetail-form-by-using-two-datarepeater-controls-visual-studio"></a><span data-ttu-id="7a9f0-102">방법: 두 DataRepeater 컨트롤을 사용하여 마스터/세부 폼 만들기(Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="7a9f0-102">How to: Create a Master/Detail Form by Using Two DataRepeater Controls (Visual Studio)</span></span>
<span data-ttu-id="7a9f0-103">두 개 이상 사용 하 여 관련된 데이터를 표시할 수 있습니다 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 마스터/세부 폼 만들기를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a9f0-103">You can display related data by using two or more <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controls to create a master/detail form.</span></span> <span data-ttu-id="7a9f0-104">하나에서 고객의 목록을 표시 하려는 하는 예를 들어 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>, 사용자가 고객을 선택 하면 두 번째의 해당 고객의 주문 목록을 표시 하 고 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>입니다.</span><span class="sxs-lookup"><span data-stu-id="7a9f0-104">For example, you might want to display a list of customers in one <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>, and when the user selects a customer, display a list of that customer's orders in a second <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.</span></span>  
  
 <span data-ttu-id="7a9f0-105">동일한 마스터 테이블 노드를 공유 하는 세부 항목을 끌어 관련된 데이터를 표시할 수 있습니다 합니다 **데이터 원본** 창만 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="7a9f0-105">You can display related data by dragging detail items that share the same master table node from the **Data Sources** window onto a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span> <span data-ttu-id="7a9f0-106">예를 들어 Customers 테이블과 관련된 Orders 테이블에는 데이터 원본에 있는 경우 두 테이블 모두으로 표시에서 트리 뷰의 최상위 노드를 **데이터 원본** 창입니다.</span><span class="sxs-lookup"><span data-stu-id="7a9f0-106">For example, if you have a data source that has a Customers table and a related Orders table, you see both tables as top-level nodes in the tree view in the **Data Sources** window.</span></span> <span data-ttu-id="7a9f0-107">열을 볼 수 있도록 고객 노드를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a9f0-107">Expand the Customers node so that you can see the columns.</span></span> <span data-ttu-id="7a9f0-108">Orders 테이블을 나타내는 확장 가능한 노드 목록에서 마지막 열 인지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a9f0-108">Notice that the last column in the list is an expandable node that represents the Orders table.</span></span> <span data-ttu-id="7a9f0-109">이 노드는 고객에 대 한 관련된 주문을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7a9f0-109">This node represents the related orders for a customer.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-display-related-data-in-two-datarepeater-controls"></a><span data-ttu-id="7a9f0-110">두 개의 DataRepeater 컨트롤에 관련 된 데이터를 표시 하려면</span><span class="sxs-lookup"><span data-stu-id="7a9f0-110">To display related data in two DataRepeater controls</span></span>  
  
1.  <span data-ttu-id="7a9f0-111">두 개 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 에서 제어 합니다 **Visual Basic PowerPacks** 탭에 **도구 상자** 폼 이나 컨테이너 컨트롤에 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a9f0-111">Drag two <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controls from the **Visual Basic PowerPacks** tab in the **Toolbox** to a form or container control.</span></span>  
  
2.  <span data-ttu-id="7a9f0-112">컨트롤의 크기를 side-by-side-배치할를 크기 조정 및 위치 핸들을 끕니다.</span><span class="sxs-lookup"><span data-stu-id="7a9f0-112">Drag the sizing and position handles to size the controls and position them side-by-side.</span></span>  
  
3.  <span data-ttu-id="7a9f0-113">**데이터** 메뉴에서 **데이터 소스 표시**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7a9f0-113">On the **Data** menu, click **Show Data Sources**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7a9f0-114">경우는 **데이터 원본** 창이 비어 있는 경우 데이터 소스를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a9f0-114">If the **Data Sources** window is empty, add a data source to it.</span></span> <span data-ttu-id="7a9f0-115">자세한 내용은 [새 데이터 소스 추가](/visualstudio/data-tools/add-new-data-sources)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7a9f0-115">For more information, see [Add new data sources](/visualstudio/data-tools/add-new-data-sources).</span></span>  
  
4.  <span data-ttu-id="7a9f0-116">에 **데이터 원본** 창 마스터 테이블에 대 한 최상위 노드를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a9f0-116">In the **Data Sources** window, select the top-level node for the master table.</span></span>  
  
5.  <span data-ttu-id="7a9f0-117">클릭 하 여 세부 정보로 마스터 테이블의 놓기 형식을 변경할 **세부 정보** 테이블 노드의 드롭다운 목록에서.</span><span class="sxs-lookup"><span data-stu-id="7a9f0-117">Change the drop type of the master table to Details by clicking **Details** in the drop-down list on the table node.</span></span>  
  
6.  <span data-ttu-id="7a9f0-118">첫 번째 항목 템플릿 영역 마스터 테이블 노드를 끌어 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a9f0-118">Drag the master table node onto the item template region of the first <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
7.  <span data-ttu-id="7a9f0-119">마스터 테이블 노드를 확장 하 고 관련된 테이블에 대 한 상세 노드를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a9f0-119">Expand the master table node and select the detail node for the related table.</span></span>  
  
8.  <span data-ttu-id="7a9f0-120">클릭 하 여 세부 정보로 세부 정보 테이블의 놓기 형식을 변경할 **세부 정보** 테이블 노드의 드롭다운 목록에서.</span><span class="sxs-lookup"><span data-stu-id="7a9f0-120">Change the drop type of the detail table to Details by clicking **Details** in the drop-down list on the table node.</span></span>  
  
9. <span data-ttu-id="7a9f0-121">이 테이블 노드를 선택 하 고 두 번째 항목 템플릿 영역으로 끌어 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a9f0-121">Select this table node and drag it onto the item template region of the second <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a9f0-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7a9f0-122">See Also</span></span>  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
 [<span data-ttu-id="7a9f0-123">DataRepeater 컨트롤 소개</span><span class="sxs-lookup"><span data-stu-id="7a9f0-123">Introduction to the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="7a9f0-124">방법: DataRepeater 컨트롤의 바인딩된 데이터 표시</span><span class="sxs-lookup"><span data-stu-id="7a9f0-124">How to: Display Bound Data in a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="7a9f0-125">방법: Windows Forms 응용 프로그램에서 관련 데이터 표시</span><span class="sxs-lookup"><span data-stu-id="7a9f0-125">How to: Display Related Data in a Windows Forms Application</span></span>](/visualstudio/data-tools/bind-windows-forms-controls-to-data-in-visual-studio)  
 [<span data-ttu-id="7a9f0-126">방법: DataRepeater 컨트롤의 모양 변경</span><span class="sxs-lookup"><span data-stu-id="7a9f0-126">How to: Change the Appearance of a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="7a9f0-127">DataRepeater 컨트롤 문제 해결</span><span class="sxs-lookup"><span data-stu-id="7a9f0-127">Troubleshooting the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
