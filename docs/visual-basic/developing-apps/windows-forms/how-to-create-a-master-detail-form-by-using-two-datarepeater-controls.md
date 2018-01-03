---
title: "방법: 두 DataRepeater 컨트롤 (Visual Studio)를 사용 하 여 마스터-세부 폼 만들기"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords: DataRepeater, master/detail tables
ms.assetid: eec43ae3-05d8-45a1-8d41-3803c6359dbe
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f17cb86c3ea0ea056291a51becd7ecf9f73d0a73
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-create-a-masterdetail-form-by-using-two-datarepeater-controls-visual-studio"></a><span data-ttu-id="2e16c-102">방법: 두 DataRepeater 컨트롤을 사용하여 마스터/세부 폼 만들기(Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="2e16c-102">How to: Create a Master/Detail Form by Using Two DataRepeater Controls (Visual Studio)</span></span>
<span data-ttu-id="2e16c-103">두 개 이상의 사용 하 여 관련된 데이터를 표시할 수 있습니다 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 마스터/세부 폼을 만들 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="2e16c-103">You can display related data by using two or more <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controls to create a master/detail form.</span></span> <span data-ttu-id="2e16c-104">예를 들어 하나에 고객의 목록을 표시 하려면 수 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>, 사용자가 고객을 선택 하는 경우 두 번째에 해당 고객의 주문 목록을 표시 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>합니다.</span><span class="sxs-lookup"><span data-stu-id="2e16c-104">For example, you might want to display a list of customers in one <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>, and when the user selects a customer, display a list of that customer's orders in a second <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.</span></span>  
  
 <span data-ttu-id="2e16c-105">동일한 마스터 테이블 노드를 공유 하는 세부 항목을 끌어 관련된 데이터를 표시할 수 있습니다는 **데이터 원본** 창으로는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e16c-105">You can display related data by dragging detail items that share the same master table node from the **Data Sources** window onto a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span> <span data-ttu-id="2e16c-106">예를 들어 Customers 테이블과 관련된 Orders 테이블에 있는 데이터 소스를 설정한 경우 두 테이블 모두 노드로 표시 최상위 트리 뷰에 **데이터 소스** 창.</span><span class="sxs-lookup"><span data-stu-id="2e16c-106">For example, if you have a data source that has a Customers table and a related Orders table, you see both tables as top-level nodes in the tree view in the **Data Sources** window.</span></span> <span data-ttu-id="2e16c-107">열을 볼 수 있도록 Customers 노드를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e16c-107">Expand the Customers node so that you can see the columns.</span></span> <span data-ttu-id="2e16c-108">Orders 테이블을 나타내는 확장 가능한 노드 목록에서 마지막 열 임을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e16c-108">Notice that the last column in the list is an expandable node that represents the Orders table.</span></span> <span data-ttu-id="2e16c-109">이 노드는 고객에 대 한 관련된 주문을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2e16c-109">This node represents the related orders for a customer.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-display-related-data-in-two-datarepeater-controls"></a><span data-ttu-id="2e16c-110">두 DataRepeater 컨트롤에 관련된 데이터 표시</span><span class="sxs-lookup"><span data-stu-id="2e16c-110">To display related data in two DataRepeater controls</span></span>  
  
1.  <span data-ttu-id="2e16c-111">두 개 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 에서 제어는 **Visual Basic PowerPacks** 탭에 **도구 상자** 폼 이나 컨테이너 컨트롤로 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e16c-111">Drag two <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controls from the **Visual Basic PowerPacks** tab in the **Toolbox** to a form or container control.</span></span>  
  
2.  <span data-ttu-id="2e16c-112">컨트롤의 크기와 위치를 함께 위치 및 크기 조정 핸들을 끌어 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e16c-112">Drag the sizing and position handles to size the controls and position them side-by-side.</span></span>  
  
3.  <span data-ttu-id="2e16c-113">**데이터** 메뉴에서 **데이터 소스 표시**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2e16c-113">On the **Data** menu, click **Show Data Sources**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2e16c-114">경우는 **데이터 소스** 창이 비어 있는 경우 데이터 소스를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e16c-114">If the **Data Sources** window is empty, add a data source to it.</span></span> <span data-ttu-id="2e16c-115">자세한 내용은 [새 데이터 소스 추가](/visualstudio/data-tools/add-new-data-sources)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2e16c-115">For more information, see [Add new data sources](/visualstudio/data-tools/add-new-data-sources).</span></span>  
  
4.  <span data-ttu-id="2e16c-116">에 **데이터 소스** 창 마스터 테이블에 대 한 최상위 노드를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e16c-116">In the **Data Sources** window, select the top-level node for the master table.</span></span>  
  
5.  <span data-ttu-id="2e16c-117">클릭 하 여 세부 정보를 마스터 테이블의 놓기 형식을 변경할 **세부 정보** 테이블 노드의 드롭다운 목록에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e16c-117">Change the drop type of the master table to Details by clicking **Details** in the drop-down list on the table node.</span></span>  
  
6.  <span data-ttu-id="2e16c-118">첫 번째 항목 템플릿 영역 마스터 테이블 노드를 끌어 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e16c-118">Drag the master table node onto the item template region of the first <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
7.  <span data-ttu-id="2e16c-119">마스터 테이블 노드를 확장 하 고 관련된 테이블에 대 한 상세 노드를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e16c-119">Expand the master table node and select the detail node for the related table.</span></span>  
  
8.  <span data-ttu-id="2e16c-120">클릭 하 여 세부 정보를 테이블의 놓기 형식을 변경 **세부 정보** 테이블 노드의 드롭다운 목록에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e16c-120">Change the drop type of the detail table to Details by clicking **Details** in the drop-down list on the table node.</span></span>  
  
9. <span data-ttu-id="2e16c-121">이 테이블 노드를 선택 하 고 두 번째 항목 템플릿 영역으로 끌어 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e16c-121">Select this table node and drag it onto the item template region of the second <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e16c-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2e16c-122">See Also</span></span>  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
 [<span data-ttu-id="2e16c-123">DataRepeater 컨트롤 소개</span><span class="sxs-lookup"><span data-stu-id="2e16c-123">Introduction to the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="2e16c-124">방법: DataRepeater 컨트롤의 바인딩된 데이터 표시</span><span class="sxs-lookup"><span data-stu-id="2e16c-124">How to: Display Bound Data in a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="2e16c-125">방법: Windows Forms 응용 프로그램에서 관련 데이터 표시</span><span class="sxs-lookup"><span data-stu-id="2e16c-125">How to: Display Related Data in a Windows Forms Application</span></span>](/visualstudio/data-tools/bind-windows-forms-controls-to-data-in-visual-studio)  
 [<span data-ttu-id="2e16c-126">방법: DataRepeater 컨트롤의 모양 변경</span><span class="sxs-lookup"><span data-stu-id="2e16c-126">How to: Change the Appearance of a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="2e16c-127">DataRepeater 컨트롤 문제 해결</span><span class="sxs-lookup"><span data-stu-id="2e16c-127">Troubleshooting the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
