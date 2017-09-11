---
title: "방법: DataRepeater 컨트롤 (Visual Studio)의 바인딩된 데이터 표시 | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- DataRepeater, data-binding
- DataRepeater, displaying bound controls
ms.assetid: 56a15326-1334-4275-af4e-075cad79e6f7
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 31905a37f09db5f5192123f0118252fbe8b02eff
ms.openlocfilehash: 677c964ee9ebbad6ec712a29c8b9c8920aa7e7ec
ms.contentlocale: ko-kr
ms.lasthandoff: 05/26/2017

---
# <a name="how-to-display-bound-data-in-a-datarepeater-control-visual-studio"></a><span data-ttu-id="d8fea-102">방법: DataRepeater 컨트롤의 바인딩된 데이터 표시(Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="d8fea-102">How to: Display Bound Data in a DataRepeater Control (Visual Studio)</span></span>
<span data-ttu-id="d8fea-103">가장 일반적인 용도 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>데이터베이스 또는 다른 데이터 소스에 바인딩된 데이터를 표시 하는 컨트롤입니다.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="d8fea-103">The most common use of the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control is to display bound data from a database or other data source.</span></span>  
  
 <span data-ttu-id="d8fea-104">정적 레이블 또는 각 항목에 대해 반복 되는 이미지와 같은 다른 컨트롤을 추가 하려는, 바인딩된 컨트롤 외에 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>제어 합니다.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="d8fea-104">In addition to bound controls, you may want to add other controls, such as a static label or an image that is repeated on each item in the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span> <span data-ttu-id="d8fea-105">자세한 내용은 참조 [하는 방법: DataRepeater 컨트롤의 바인딩되지 않은 컨트롤 표시](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d8fea-105">For more information, see [How to: Display Unbound Controls in a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md).</span></span>  
  
 <span data-ttu-id="d8fea-106">바인딩할 수도 있습니다 데이터 소스에 실행할 때 설정 하 여는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A>속성을 `True` 데이터 소스를 할당 하는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DataSource%2A>속성.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DataSource%2A> </xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A></span><span class="sxs-lookup"><span data-stu-id="d8fea-106">You can also bind to a data source at run time by setting the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A> property to `True` and assigning a data source to the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DataSource%2A> property.</span></span> <span data-ttu-id="d8fea-107">이 경우 데이터 소스와 모든 상호 작용을 관리 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8fea-107">In this case, you will need to manage all interaction with the data source.</span></span> <span data-ttu-id="d8fea-108">자세한 내용은 참조 [DataRepeater 컨트롤의 가상 모드](../../../visual-basic/developing-apps/windows-forms/virtual-mode-in-the-datarepeater-control-visual-studio.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d8fea-108">For more information, see [Virtual Mode in the DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/virtual-mode-in-the-datarepeater-control-visual-studio.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-data-bound-datarepeater"></a><span data-ttu-id="d8fea-109">데이터 바인딩된 DataRepeater를 만들려면</span><span class="sxs-lookup"><span data-stu-id="d8fea-109">To create a data-bound DataRepeater</span></span>  
  
1.  <span data-ttu-id="d8fea-110">끌기는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>에서 제어는 **Visual Basic PowerPacks** 탭에 **도구 상자** 폼 이나 컨테이너 컨트롤로.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="d8fea-110">Drag a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control from the **Visual Basic PowerPacks** tab in the **Toolbox** to a form or container control.</span></span>  
  
2.  <span data-ttu-id="d8fea-111">크기 조정 및 위치 핸들 크기를 끌어서 컨트롤을 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8fea-111">Drag the sizing and position handles to size and position the control.</span></span>  
  
     <span data-ttu-id="d8fea-112">컨트롤에는 두 개의 사각형 영역을 참고 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8fea-112">Note that the control has two rectangular regions.</span></span> <span data-ttu-id="d8fea-113">위 영역은 *항목 템플릿을*; 서식 파일에 추가 된 컨트롤의 각 항목에 반복 됩니다는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>런타임 시 컨트롤.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="d8fea-113">The upper region is the *item template*; controls added to the template will be repeated in each item in the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control at run time.</span></span> <span data-ttu-id="d8fea-114">하위 영역은 *뷰포트*, 항목이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8fea-114">The lower region is the *viewport*, where the items will be displayed.</span></span>  
  
     <span data-ttu-id="d8fea-115">또한 크기와 컨트롤 또는 항목 템플릿을 변경 하 여 위치를 조정할 수는 **크기** 및 **위치** 속성 창에서 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="d8fea-115">You can also size and position the control or the item template by changing the **Size** and **Position** properties in the Properties window.</span></span>  
  
3.  <span data-ttu-id="d8fea-116">**데이터** 메뉴에서 **데이터 소스 표시**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d8fea-116">On the **Data** menu, click **Show Data Sources**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d8fea-117">하는 경우는 **데이터 원본** 창이 비어 있으면 데이터 소스를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8fea-117">If the **Data Sources** window is empty, add a data source to it.</span></span> <span data-ttu-id="d8fea-118">자세한 내용은 참조 [새 데이터 소스를 추가할](https://docs.microsoft.com/visualstudio/data-tools/add-new-data-sources)합니다.</span><span class="sxs-lookup"><span data-stu-id="d8fea-118">For more information, see [Add new data sources](https://docs.microsoft.com/visualstudio/data-tools/add-new-data-sources).</span></span>  
  
4.  <span data-ttu-id="d8fea-119">에 **데이터 원본** 창에서 바인딩할 데이터를 포함 하는 테이블에 대 한 최상위 노드를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8fea-119">In the **Data Sources** window, select the top-level node for the table that contains the data that you want to bind.</span></span>  
  
5.  <span data-ttu-id="d8fea-120">변경 테이블의 삭제 유형을 `Details` 클릭 하 여 `Details` 테이블 노드의 드롭다운 목록에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8fea-120">Change the drop type of the table to `Details` by clicking `Details` in the drop-down list on the table node.</span></span>  
  
6.  <span data-ttu-id="d8fea-121">테이블 노드를 선택 하 고의 항목 템플릿 영역으로 끌어 옵니다는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>제어 합니다.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="d8fea-121">Select the table node and drag it onto the item template region of the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
     <span data-ttu-id="d8fea-122">각 필드에 대해 표시 되는 컨트롤의 어떤 형식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8fea-122">You can specify which types of controls are displayed for each field.</span></span> <span data-ttu-id="d8fea-123">자세한 내용은 참조 [데이터 소스 창에서 끌어 올 때 만들 컨트롤 설정](https://docs.microsoft.com/visualstudio/data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window)합니다.</span><span class="sxs-lookup"><span data-stu-id="d8fea-123">For more information, see [Set the control to be created when dragging from the Data Sources window](https://docs.microsoft.com/visualstudio/data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8fea-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d8fea-124">See Also</span></span>  
 <span data-ttu-id="d8fea-125"><xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="d8fea-125"><xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span></span>   
<span data-ttu-id="d8fea-126"> [DataRepeater 컨트롤 소개](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md) </span><span class="sxs-lookup"><span data-stu-id="d8fea-126"> [Introduction to the DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md) </span></span>  
<span data-ttu-id="d8fea-127"> [방법: 바인딩되지 않은 DataRepeater 컨트롤의 컨트롤 표시](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md) </span><span class="sxs-lookup"><span data-stu-id="d8fea-127"> [How to: Display Unbound Controls in a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md) </span></span>  
<span data-ttu-id="d8fea-128"> [방법: 두 DataRepeater 컨트롤 (Visual Studio)를 사용 하 여 마스터/세부 폼 만들기](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md) </span><span class="sxs-lookup"><span data-stu-id="d8fea-128"> [How to: Create a Master/Detail Form by Using Two DataRepeater Controls (Visual Studio)](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md) </span></span>  
<span data-ttu-id="d8fea-129"> [방법: DataRepeater 컨트롤의 모양 변경](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md) </span><span class="sxs-lookup"><span data-stu-id="d8fea-129"> [How to: Change the Appearance of a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md) </span></span>  
<span data-ttu-id="d8fea-130"> [DataRepeater 컨트롤 문제 해결](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)</span><span class="sxs-lookup"><span data-stu-id="d8fea-130"> [Troubleshooting the DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)</span></span>
