---
title: "방법: 디자이너를 사용하여 Windows Forms ListView 컨트롤에서 Tile 보기 사용"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- tile view feature
- ListView control [Windows Forms], tile view
- tiling [Windows Forms], Windows Forms, controls
ms.assetid: 12f0816a-52b8-41ee-a6d9-ded3a8a5817a
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 36b20f4ee5bed6f81c42225f35083d51fb2a6308
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-enable-tile-view-in-a-windows-forms-listview-control-using-the-designer"></a><span data-ttu-id="da4e9-102">방법: 디자이너를 사용하여 Windows Forms ListView 컨트롤에서 Tile 보기 사용</span><span class="sxs-lookup"><span data-stu-id="da4e9-102">How to: Enable Tile View in a Windows Forms ListView Control Using the Designer</span></span>
<span data-ttu-id="da4e9-103">바둑판식 뷰 기능은 <xref:System.Windows.Forms.ListView> 제어를 통해 그래픽 정보와 텍스트 정보 간의 시각적 균형을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da4e9-103">The tile view feature of the <xref:System.Windows.Forms.ListView> control enables you to provide a visual balance between graphical and textual information.</span></span> <span data-ttu-id="da4e9-104">바둑판식 뷰에서 항목에 대해 표시되는 텍스트 정보는 세부 정보 뷰에 대해 정의된 열 정보와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="da4e9-104">The textual information displayed for an item in tile view is the same as the column information defined for details view.</span></span> <span data-ttu-id="da4e9-105">다음 함수를 함께 그룹화 또는 삽입 타일 보기에 기능을 표시할는 <xref:System.Windows.Forms.ListView> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="da4e9-105">Tile view functions in combination with either the grouping or insertion mark features in the <xref:System.Windows.Forms.ListView> control.</span></span>  
  
 <span data-ttu-id="da4e9-106">바둑판식 뷰는 다음 그림에 나와 있는 것 처럼 32 x 32 아이콘과 여러 줄의 텍스트를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="da4e9-106">The tile view uses a 32 x 32 icon and several lines of text, as shown in the following image.</span></span>  
  
 <span data-ttu-id="da4e9-107">![ListView 컨트롤의 tile 보기](../../../../docs/framework/winforms/controls/media/listviewtile.gif "ListViewTile")</span><span class="sxs-lookup"><span data-stu-id="da4e9-107">![Tile View in a ListView Control](../../../../docs/framework/winforms/controls/media/listviewtile.gif "ListViewTile")</span></span>  
  
 <span data-ttu-id="da4e9-108">Tile 보기 속성 및 메서드 사용 전체적으로 크기와 tile 보기 창 내에서 모든 항목의 모양을 제어 하려면 각 항목에 대해 표시할 열 필드를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da4e9-108">Tile view properties and methods enable you to specify which column fields to display for each item, and to collectively control the size and appearance of all items within a tile view window.</span></span> <span data-ttu-id="da4e9-109">명확성을 위해 첫 번째 텍스트 줄을 타일에는 항상 해당 항목의 이름입니다. 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="da4e9-109">For clarity, the first line of text in a tile is always the item's name; it cannot be changed.</span></span>  
  
 <span data-ttu-id="da4e9-110">다음 절차를 수행 하려면는 **Windows 응용 프로그램** 포함 된 폼을 사용 하 여 프로젝트는 <xref:System.Windows.Forms.ListView> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="da4e9-110">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.ListView> control.</span></span> <span data-ttu-id="da4e9-111">이러한 프로젝트 설정에 대 한 정보를 참조 하십시오. [하는 방법: Windows 응용 프로그램 프로젝트 만들기](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa) 및 [하는 방법: Windows Forms에 컨트롤 추가](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="da4e9-111">For information about setting up such a project, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa) and [How to: Add Controls to Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="da4e9-112">바둑판식 뷰는 응용 프로그램이 <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> 메서드를 호출할 때 [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)]에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da4e9-112">The tile view is available only on [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] when your application calls the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="da4e9-113">이전 운영 체제에서는 바둑판식 뷰와 관련된 코드가 아무 효과도 없으며, <xref:System.Windows.Forms.ListView> 컨트롤이 큰 아이콘 보기에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="da4e9-113">On earlier operating systems, any code related to the tile view has no effect, and the <xref:System.Windows.Forms.ListView> control displays in the large icon view.</span></span> <span data-ttu-id="da4e9-114">자세한 내용은 <xref:System.Windows.Forms.ListView.View%2A?displayProperty=nameWithType>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="da4e9-114">For more information, see <xref:System.Windows.Forms.ListView.View%2A?displayProperty=nameWithType>.</span></span>  
>   
>  <span data-ttu-id="da4e9-115">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da4e9-115">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="da4e9-116">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="da4e9-116">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="da4e9-117">자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="da4e9-117">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-set-tile-view-in-the-designer"></a><span data-ttu-id="da4e9-118">디자이너에서 tile 보기를 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="da4e9-118">To set tile view in the designer</span></span>  
  
1.  <span data-ttu-id="da4e9-119">선택 된 <xref:System.Windows.Forms.ListView> 폼의 컨트롤로 합니다.</span><span class="sxs-lookup"><span data-stu-id="da4e9-119">Select the <xref:System.Windows.Forms.ListView> control on your form.</span></span>  
  
2.  <span data-ttu-id="da4e9-120">에 **속성** 창에서는 <xref:System.Windows.Forms.ListView.View%2A> 속성 선택 **타일**합니다.</span><span class="sxs-lookup"><span data-stu-id="da4e9-120">In the **Properties** window, select the <xref:System.Windows.Forms.ListView.View%2A> property and choose **Tile**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da4e9-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="da4e9-121">See Also</span></span>  
 <xref:System.Windows.Forms.ListView.TileSize%2A>  
 [<span data-ttu-id="da4e9-122">Windows XP 기능 및 Windows Forms 컨트롤</span><span class="sxs-lookup"><span data-stu-id="da4e9-122">Windows XP Features and Windows Forms Controls</span></span>](http://msdn.microsoft.com/en-us/bc7fab94-fce9-4bf1-a8ad-a5837c91c3c0)  
 [<span data-ttu-id="da4e9-123">ListView 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="da4e9-123">ListView Control Overview</span></span>](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)
