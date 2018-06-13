---
title: '방법: DataRepeater 컨트롤의 데이터 검색(Visual Studio)'
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataRepeater, implementing search
- DataRepeater, searching data
ms.assetid: a8ab5d17-b94f-43c4-8dd7-d0450226d73f
ms.openlocfilehash: 689990ee125c85c3151a4e965b619fde068d220e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33588056"
---
# <a name="how-to-search-data-in-a-datarepeater-control-visual-studio"></a><span data-ttu-id="db6b5-102">방법: DataRepeater 컨트롤의 데이터 검색(Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="db6b5-102">How to: Search Data in a DataRepeater Control (Visual Studio)</span></span>
<span data-ttu-id="db6b5-103">사용 하는 경우는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 특정 레코드에 대 한 사용자 들은 검색 하려는 경우 많은 레코드를 포함 하는 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="db6b5-103">When you are using a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control that contains many records, you may want to let users search for a specific record.</span></span> <span data-ttu-id="db6b5-104">컨트롤 자체에 데이터를 검색 하는 대신 기본 쿼리를 통해 검색을 구현할 수 있습니다 <xref:System.Windows.Forms.BindingSource>합니다.</span><span class="sxs-lookup"><span data-stu-id="db6b5-104">Rather than searching the data in the control itself, you can implement a search by querying the underlying <xref:System.Windows.Forms.BindingSource>.</span></span> <span data-ttu-id="db6b5-105">항목이 발견 되는 경우 사용할 수 있습니다는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.CurrentItemIndex%2A> 속성을 항목을 선택 하 고을 뷰로 스크롤합니다.</span><span class="sxs-lookup"><span data-stu-id="db6b5-105">If the item is found, you can then use the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.CurrentItemIndex%2A> property to select the item and scroll it into view.</span></span>  
  
### <a name="to-implement-search"></a><span data-ttu-id="db6b5-106">검색을 구현 하려면</span><span class="sxs-lookup"><span data-stu-id="db6b5-106">To implement search</span></span>  
  
1.  <span data-ttu-id="db6b5-107"><xref:System.Windows.Forms.TextBox> 도구 상자 **에서** 컨트롤이 포함된 폼으로 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 컨트롤을 끌어 옵니다.</span><span class="sxs-lookup"><span data-stu-id="db6b5-107">Drag a <xref:System.Windows.Forms.TextBox> control from the **Toolbox** onto the form that contains the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
2.  <span data-ttu-id="db6b5-108">속성 창에서 **Name** 속성을 **SearchTextBox**로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="db6b5-108">In the Properties window, change the **Name** property to **SearchTextBox**.</span></span>  
  
3.  <span data-ttu-id="db6b5-109"><xref:System.Windows.Forms.Button> 도구 상자 **에서** 컨트롤이 포함된 폼으로 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 컨트롤을 끌어 옵니다.</span><span class="sxs-lookup"><span data-stu-id="db6b5-109">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** onto the form that contains the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
4.  <span data-ttu-id="db6b5-110">속성 창에서 **Name** 속성을 **SearchButton**으로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="db6b5-110">In the Properties window, change the **Name** property to **SearchButton**.</span></span> <span data-ttu-id="db6b5-111">**Text** 속성을 **Search**로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="db6b5-111">Change the **Text** property to **Search**.</span></span>  
  
5.  <span data-ttu-id="db6b5-112"><xref:System.Windows.Forms.Button> 컨트롤을 두 번 클릭하여 코드 편집기를 열고 `SearchButton_Click` 이벤트 처리기에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="db6b5-112">Double-click the <xref:System.Windows.Forms.Button> control to open the Code Editor, and add the following code to the `SearchButton_Click` event handler.</span></span>  
  
     [!code-vb[VbPowerPacksDataRepeaterSearch#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-search-data-in-a-datarepeater-control-visual-studio_1.vb)]
     [!code-csharp[VbPowerPacksDataRepeaterSearch#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-search-data-in-a-datarepeater-control-visual-studio_1.cs)]  
  
     <span data-ttu-id="db6b5-113">대체 *ProductsBindingSource* 의 이름으로는 <xref:System.Windows.Forms.BindingSource> 에 대 한 프로그램 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>, 대체 *ProductID* 검색할 필드의 이름으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="db6b5-113">Replace *ProductsBindingSource* with the name of the <xref:System.Windows.Forms.BindingSource> for your <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>, and replace *ProductID* with the name of the field that you want to search.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db6b5-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="db6b5-114">See Also</span></span>  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
 [<span data-ttu-id="db6b5-115">DataRepeater 컨트롤 소개</span><span class="sxs-lookup"><span data-stu-id="db6b5-115">Introduction to the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="db6b5-116">DataRepeater 컨트롤 문제 해결</span><span class="sxs-lookup"><span data-stu-id="db6b5-116">Troubleshooting the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="db6b5-117">방법: DataRepeater 컨트롤의 모양 변경</span><span class="sxs-lookup"><span data-stu-id="db6b5-117">How to: Change the Appearance of a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)
