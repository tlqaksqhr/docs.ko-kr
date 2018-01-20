---
title: "방법: 디자이너를 사용하여 Windows Forms TabControl에서 탭 추가 및 제거"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- tabs [Windows Forms], removing from pages
- TabPage control
- TabPage control [Windows Forms], adding and removing tabs
- tabs [Windows Forms], adding to pages
- tab pages
ms.assetid: 480633db-413a-45d2-9c8f-0427cc13adbe
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8e603e420be2c5be6174fab3876008fdf73c8459
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol-using-the-designer"></a><span data-ttu-id="b02b9-102">방법: 디자이너를 사용하여 Windows Forms TabControl에서 탭 추가 및 제거</span><span class="sxs-lookup"><span data-stu-id="b02b9-102">How to: Add and Remove Tabs with the Windows Forms TabControl Using the Designer</span></span>
<span data-ttu-id="b02b9-103">배치 하는 경우는 <xref:System.Windows.Forms.TabControl> 컨트롤이 폼에 기본적으로 두 개의 탭 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="b02b9-103">When you place a <xref:System.Windows.Forms.TabControl> control on your form, it contains two tabs by default.</span></span> <span data-ttu-id="b02b9-104">추가 하거나 디자이너를 사용 하 여 탭을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b02b9-104">You can add or remove tabs using the designer.</span></span>  
  
 <span data-ttu-id="b02b9-105">다음 절차를 수행 하려면는 **Windows 응용 프로그램** 포함 된 폼을 사용 하 여 프로젝트는 <xref:System.Windows.Forms.TabControl> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="b02b9-105">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.TabControl> control.</span></span> <span data-ttu-id="b02b9-106">이러한 프로젝트 설정에 대 한 정보를 참조 하십시오. [하는 방법: Windows 응용 프로그램 프로젝트 만들기](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) 및 [하는 방법: Windows Forms에 컨트롤 추가](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b02b9-106">For information about setting up such a project, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) and [How to: Add Controls to Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b02b9-107">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b02b9-107">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="b02b9-108">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b02b9-108">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="b02b9-109">자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b02b9-109">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-add-or-remove-a-tab-using-the-designer"></a><span data-ttu-id="b02b9-110">추가 하거나 디자이너를 사용 하 여 탭을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="b02b9-110">To add or remove a tab using the designer</span></span>  
  
-   <span data-ttu-id="b02b9-111">컨트롤의 스마트 태그에서 클릭 **탭 추가** 또는 **탭 제거**</span><span class="sxs-lookup"><span data-stu-id="b02b9-111">On the control's smart tag, click **Add Tab** or **Remove Tab**</span></span>  
  
     <span data-ttu-id="b02b9-112">또는</span><span class="sxs-lookup"><span data-stu-id="b02b9-112">-or-</span></span>  
  
     <span data-ttu-id="b02b9-113">에 **속성** 창 클릭는 **줄임표** 단추 (![VisualStudioEllipsesButton 스크린 샷](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) 옆에 <xref:System.Windows.Forms.TabControl.TabPages%2A> 속성을 열고는 **TabPage 컬렉션 편집기**합니다.</span><span class="sxs-lookup"><span data-stu-id="b02b9-113">In the **Properties** window, click the **Ellipsis** button (![VisualStudioEllipsesButton screenshot](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) next to the <xref:System.Windows.Forms.TabControl.TabPages%2A> property to open the **TabPage Collection Editor**.</span></span> <span data-ttu-id="b02b9-114">클릭는 **추가** 또는 **제거** 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="b02b9-114">Click the **Add** or **Remove** button.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b02b9-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b02b9-115">See Also</span></span>  
 [<span data-ttu-id="b02b9-116">TabControl 컨트롤</span><span class="sxs-lookup"><span data-stu-id="b02b9-116">TabControl Control</span></span>](../../../../docs/framework/winforms/controls/tabcontrol-control-windows-forms.md)  
 [<span data-ttu-id="b02b9-117">TabControl 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="b02b9-117">TabControl Control Overview</span></span>](../../../../docs/framework/winforms/controls/tabcontrol-control-overview-windows-forms.md)  
 [<span data-ttu-id="b02b9-118">방법: 탭 페이지에 컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="b02b9-118">How to: Add a Control to a Tab Page</span></span>](../../../../docs/framework/winforms/controls/how-to-add-a-control-to-a-tab-page.md)  
 [<span data-ttu-id="b02b9-119">방법: 탭 페이지 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="b02b9-119">How to: Disable Tab Pages</span></span>](../../../../docs/framework/winforms/controls/how-to-disable-tab-pages.md)  
 [<span data-ttu-id="b02b9-120">방법: Windows Forms TabControl의 모양 변경</span><span class="sxs-lookup"><span data-stu-id="b02b9-120">How to: Change the Appearance of the Windows Forms TabControl</span></span>](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
