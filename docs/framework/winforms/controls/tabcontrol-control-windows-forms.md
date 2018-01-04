---
title: "TabControl 컨트롤(Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- TabControl control [Windows Forms]
- tab controls
- tab controls [Windows Forms], creating
- multipage dialog boxes
- dialog boxes [Windows Forms], creating multipage
- property pages [Windows Forms], creating
- tab dialog boxes
ms.assetid: 915091af-93ac-4d3d-8283-738dd2d21ea7
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 705f9dbb8ea7f4d462a2b19cc0c6b845ae8f578b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="tabcontrol-control-windows-forms"></a><span data-ttu-id="08518-102">TabControl 컨트롤(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="08518-102">TabControl Control (Windows Forms)</span></span>
<span data-ttu-id="08518-103">Windows Forms `TabControl`은 파일 캐비닛의 폴더 집합에 노트북 또는 레이블의 구분선과 같은 여러 탭을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="08518-103">The Windows Forms `TabControl` displays multiple tabs, like dividers in a notebook or labels in a set of folders in a filing cabinet.</span></span> <span data-ttu-id="08518-104">탭에는 사진 및 기타 컨트롤이 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08518-104">The tabs can contain pictures and other controls.</span></span> <span data-ttu-id="08518-105">`TabControl`을 사용하여 속성 페이지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="08518-105">Use the `TabControl` to create property pages.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="08518-106">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="08518-106">In This Section</span></span>  
 [<span data-ttu-id="08518-107">TabControl 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="08518-107">TabControl Control Overview</span></span>](../../../../docs/framework/winforms/controls/tabcontrol-control-overview-windows-forms.md)  
 <span data-ttu-id="08518-108">이 컨트롤의 정의와 주요 기능 및 속성을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="08518-108">Explains what this control is and its key features and properties.</span></span>  
  
 [<span data-ttu-id="08518-109">방법: 탭 페이지에 컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="08518-109">How to: Add a Control to a Tab Page</span></span>](../../../../docs/framework/winforms/controls/how-to-add-a-control-to-a-tab-page.md)  
 <span data-ttu-id="08518-110">탭 페이지에 컨트롤을 표시하기 위한 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="08518-110">Gives directions for displaying controls on tab pages.</span></span>  
  
 [<span data-ttu-id="08518-111">방법: Windows Forms TabControl을 사용하여 탭 추가 및 제거</span><span class="sxs-lookup"><span data-stu-id="08518-111">How to: Add and Remove Tabs with the Windows Forms TabControl</span></span>](../../../../docs/framework/winforms/controls/how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)  
 <span data-ttu-id="08518-112">디자이너 또는 코드에서 탭을 추가 및 제거하기 위한 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="08518-112">Gives directions for adding and removing tabs in the designer or in code.</span></span>  
  
 [<span data-ttu-id="08518-113">방법: Windows Forms TabControl의 모양 변경</span><span class="sxs-lookup"><span data-stu-id="08518-113">How to: Change the Appearance of the Windows Forms TabControl</span></span>](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)  
 <span data-ttu-id="08518-114">개별 탭의 모양에 영향을 주는 속성을 조정하기 위한 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="08518-114">Gives directions for adjusting properties that affect the appearance of individual tabs.</span></span>  
  
 [<span data-ttu-id="08518-115">방법: 탭 페이지 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="08518-115">How to: Disable Tab Pages</span></span>](../../../../docs/framework/winforms/controls/how-to-disable-tab-pages.md)  
 <span data-ttu-id="08518-116">사용자 자격 증명에 따라 탭 페이지에 대한 액세스를 제한하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="08518-116">Explains how to restrict access to a tab page, possibly based on user credentials.</span></span>  
  
 <span data-ttu-id="08518-117">참조도 [하는 방법: 추가 및 제거는 디자이너를 사용 하 여 Windows Forms TabControl에서 탭](http://msdn.microsoft.com/library/ms233654\(v=vs.110\)), [하는 방법: 탭 페이지를 사용 하 여 디자이너 컨트롤 추가](http://msdn.microsoft.com/library/ms233668\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="08518-117">Also see [How to: Add and Remove Tabs with the Windows Forms TabControl Using the Designer](http://msdn.microsoft.com/library/ms233654\(v=vs.110\)), [How to: Add a Control to a Tab Page Using the Designer](http://msdn.microsoft.com/library/ms233668\(v=vs.110\))</span></span>  
  
## <a name="reference"></a><span data-ttu-id="08518-118">참조</span><span class="sxs-lookup"><span data-stu-id="08518-118">Reference</span></span>  
 <span data-ttu-id="08518-119"><xref:System.Windows.Forms.TabControl> 클래스</span><span class="sxs-lookup"><span data-stu-id="08518-119"><xref:System.Windows.Forms.TabControl> class</span></span>  
 <span data-ttu-id="08518-120">이 클래스를 설명하고 모든 해당 멤버의 링크를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="08518-120">Describes this class and has links to all its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="08518-121">관련 단원</span><span class="sxs-lookup"><span data-stu-id="08518-121">Related Sections</span></span>  
 [<span data-ttu-id="08518-122">Windows Forms 대화 상자</span><span class="sxs-lookup"><span data-stu-id="08518-122">Dialog Boxes in Windows Forms</span></span>](../../../../docs/framework/winforms/dialog-boxes-in-windows-forms.md)  
 <span data-ttu-id="08518-123">대체로 탭을 표시하는 대화 상자에 대한 작업 목록을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="08518-123">Provides a list of tasks for dialog boxes, which often display tabs.</span></span>  
  
 [<span data-ttu-id="08518-124">Windows Forms에 사용할 수 있는 컨트롤</span><span class="sxs-lookup"><span data-stu-id="08518-124">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 <span data-ttu-id="08518-125">사용 방법에 대한 정보 링크를 포함하는 Windows Forms 컨트롤의 전체 목록을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="08518-125">Provides a complete list of Windows Forms controls, with links to information on their use.</span></span>
