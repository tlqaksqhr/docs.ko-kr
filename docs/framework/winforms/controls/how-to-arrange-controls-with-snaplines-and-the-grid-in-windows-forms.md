---
title: "방법: Windows Forms에서 맞춤선과 모눈을 사용하여 컨트롤 정렬"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: GridSize
helpviewer_keywords:
- snap to grid [Windows Forms], Windows Forms Designer
- Windows Forms, grid options in designer
- controls [Windows Forms], aligning
ms.assetid: bb54bce5-880f-4a36-af68-8cf92058dc1c
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7e3754df2930503e7e7a123ffdb4d4b787338c20
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-arrange-controls-with-snaplines-and-the-grid-in-windows-forms"></a><span data-ttu-id="8a36f-102">방법: Windows Forms에서 맞춤선과 모눈을 사용하여 컨트롤 정렬</span><span class="sxs-lookup"><span data-stu-id="8a36f-102">How to: Arrange Controls with Snaplines and the Grid in Windows Forms</span></span>
<span data-ttu-id="8a36f-103">레이아웃 기능을 사용 하 여 [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)], 컨트롤이 폼에 배치 될 위치를 정확 하 게 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a36f-103">Using the layout features of [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)], you can precisely direct where controls are placed on a form.</span></span> <span data-ttu-id="8a36f-104">컨트롤을 폼에 추가 하거나 폼에서 이동한 행과 Windows Forms 디자이너 눈금의 열에 자동으로 정렬할 수 있습니다 또는 맞춤선 기능을 사용 하 여 컨트롤을 정렬할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a36f-104">Controls added to a form or moved on a form can be automatically aligned to the rows and columns of the Windows Forms Designer's grid, or you can align controls by using the snaplines feature.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8a36f-105">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a36f-105">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="8a36f-106">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8a36f-106">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="8a36f-107">자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8a36f-107">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-snap-all-controls-to-the-grid"></a><span data-ttu-id="8a36f-108">모든 컨트롤을 눈금에 맞추기</span><span class="sxs-lookup"><span data-stu-id="8a36f-108">To snap all controls to the grid</span></span>  
  
-   <span data-ttu-id="8a36f-109">선택 된 **SnapToGrid** Windows Forms 디자이너에서 레이아웃 모드 **옵션** 대화 상자.</span><span class="sxs-lookup"><span data-stu-id="8a36f-109">Select the **SnapToGrid** layout mode in the Windows Forms Designer **Options** dialog box.</span></span>  
  
     <span data-ttu-id="8a36f-110">자세한 내용은 참조 [Windows Forms 디자이너, 옵션 대화 상자, 일반](http://msdn.microsoft.com/en-us/8dd170af-72f0-4212-b04b-034ceee92834)합니다.</span><span class="sxs-lookup"><span data-stu-id="8a36f-110">For more information, see [General, Windows Forms Designer, Options Dialog Box](http://msdn.microsoft.com/en-us/8dd170af-72f0-4212-b04b-034ceee92834).</span></span> <span data-ttu-id="8a36f-111">모든 컨트롤의 모눈 점에 따라 맞춰집니다.</span><span class="sxs-lookup"><span data-stu-id="8a36f-111">All controls now align themselves along the points on the grid.</span></span>  
  
     <span data-ttu-id="8a36f-112">원위치에서 잠금으로써 눈금에 개별 컨트롤을 맞출 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a36f-112">You can snap individual controls to the grid by locking them in place.</span></span> <span data-ttu-id="8a36f-113">그러나 잠겨 있는 동안 하거나 수는 없습니다 이동 크기를 조정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a36f-113">However, while they are locked, they cannot be moved or resized.</span></span> <span data-ttu-id="8a36f-114">잠금 컨트롤에 대 한 자세한 내용은 참조 [하는 방법: Windows Forms에 컨트롤을 잠그기](../../../../docs/framework/winforms/controls/how-to-lock-controls-to-windows-forms.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8a36f-114">For more information about locking controls, see [How to: Lock Controls to Windows Forms](../../../../docs/framework/winforms/controls/how-to-lock-controls-to-windows-forms.md).</span></span>  
  
### <a name="to-align-controls-using-snaplines"></a><span data-ttu-id="8a36f-115">맞춤선을 사용 하 여 컨트롤을 맞추려면</span><span class="sxs-lookup"><span data-stu-id="8a36f-115">To align controls using snaplines</span></span>  
  
-   <span data-ttu-id="8a36f-116">선택 된 **맞춤선** Windows Forms 디자이너에서 레이아웃 모드 **옵션** 대화 상자.</span><span class="sxs-lookup"><span data-stu-id="8a36f-116">Select the **SnapLines** layout mode in the Windows Forms Designer **Options** dialog box.</span></span>  
  
     <span data-ttu-id="8a36f-117">자세한 내용은 참조 [연습: 맞춤선 Windows Forms에서 사용 하 여 컨트롤 정렬](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8a36f-117">For more information, see [Walkthrough: Arranging Controls on Windows Forms Using Snaplines](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).</span></span> <span data-ttu-id="8a36f-118">이제 폼에서 컨트롤을 정렬 하려면 맞춤선을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a36f-118">You can now use snaplines to align and arrange controls on your form.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a36f-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8a36f-119">See Also</span></span>  
 [<span data-ttu-id="8a36f-120">옵션 대화 상자, Windows Forms 디자이너, 일반</span><span class="sxs-lookup"><span data-stu-id="8a36f-120">General, Windows Forms Designer, Options Dialog Box</span></span>](http://msdn.microsoft.com/en-us/8dd170af-72f0-4212-b04b-034ceee92834)  
 [<span data-ttu-id="8a36f-121">연습: Windows Forms에서 맞춤선을 사용하여 컨트롤 정렬</span><span class="sxs-lookup"><span data-stu-id="8a36f-121">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)  
 [<span data-ttu-id="8a36f-122">Windows Forms 컨트롤</span><span class="sxs-lookup"><span data-stu-id="8a36f-122">Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/index.md)  
 [<span data-ttu-id="8a36f-123">방법: Windows Forms에 컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="8a36f-123">How to: Add Controls to Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)  
 [<span data-ttu-id="8a36f-124">Windows Forms에서 컨트롤 정렬</span><span class="sxs-lookup"><span data-stu-id="8a36f-124">Arranging Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [<span data-ttu-id="8a36f-125">개별 Windows Forms 컨트롤 레이블 지정 및 바로 가기 제공</span><span class="sxs-lookup"><span data-stu-id="8a36f-125">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)  
 [<span data-ttu-id="8a36f-126">Windows Forms에 사용할 수 있는 컨트롤</span><span class="sxs-lookup"><span data-stu-id="8a36f-126">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 [<span data-ttu-id="8a36f-127">기능별 Windows Forms 컨트롤</span><span class="sxs-lookup"><span data-stu-id="8a36f-127">Windows Forms Controls by Function</span></span>](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)
