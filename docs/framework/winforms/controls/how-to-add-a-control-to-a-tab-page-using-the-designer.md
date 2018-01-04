---
title: "방법: 디자이너를 사용하여 탭 페이지에 컨트롤 추가"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- TabPage control
- tab controls [Windows Forms], tab order
- tab pages [Windows Forms], adding controls
ms.assetid: 7ee734e1-e31e-4ed0-bbc0-a7e8a1f20fef
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5be65fc562d5b4d80a57ab068d97d66ccb17b6e0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-a-control-to-a-tab-page-using-the-designer"></a><span data-ttu-id="06319-102">방법: 디자이너를 사용하여 탭 페이지에 컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="06319-102">How to: Add a Control to a Tab Page Using the Designer</span></span>
<span data-ttu-id="06319-103">Windows Forms를 사용 하는 <xref:System.Windows.Forms.TabControl> 조직화 방식으로 다른 컨트롤을 표시 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="06319-103">The use of the Windows Forms <xref:System.Windows.Forms.TabControl> is to display other controls in an organized fashion.</span></span> <span data-ttu-id="06319-104">탭 페이지의 주요 부분에 그림을 표시 하려면 다음이 지침을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06319-104">You can use these instructions to display a picture on the main part of a tab page.</span></span> <span data-ttu-id="06319-105">탭 페이지의 레이블이 부분에 아이콘을 추가 하는 방법에 대 한 정보를 참조 하십시오. [하는 방법: Windows Forms TabControl의 모양 변경](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="06319-105">For information about adding an icon to the label part of a tab page, see [How to: Change the Appearance of the Windows Forms TabControl](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md).</span></span>  
  
 <span data-ttu-id="06319-106">다음 절차를 수행 하려면는 **Windows 응용 프로그램** 포함 된 폼을 사용 하 여 프로젝트는 <xref:System.Windows.Forms.TabControl> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="06319-106">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.TabControl> control.</span></span> <span data-ttu-id="06319-107">이러한 프로젝트 설정에 대 한 정보를 참조 하십시오. [하는 방법: Windows 응용 프로그램 프로젝트 만들기](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa) 및 [하는 방법: Windows Forms에 컨트롤 추가](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="06319-107">For information about setting up such a project, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa) and [How to: Add Controls to Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="06319-108">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06319-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="06319-109">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="06319-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="06319-110">자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="06319-110">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-add-a-control-using-the-designer"></a><span data-ttu-id="06319-111">디자이너를 사용 하 여 컨트롤을 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="06319-111">To add a control using the designer</span></span>  
  
1.  <span data-ttu-id="06319-112">맨 위에 표시 되도록 적절 한 탭 페이지를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="06319-112">Click the appropriate tab page so that it appears on top.</span></span>  
  
2.  <span data-ttu-id="06319-113">탭 페이지에 컨트롤을 그립니다.</span><span class="sxs-lookup"><span data-stu-id="06319-113">Draw the control on the tab page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06319-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="06319-114">See Also</span></span>  
 [<span data-ttu-id="06319-115">TabControl 컨트롤</span><span class="sxs-lookup"><span data-stu-id="06319-115">TabControl Control</span></span>](../../../../docs/framework/winforms/controls/tabcontrol-control-windows-forms.md)  
 [<span data-ttu-id="06319-116">TabControl 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="06319-116">TabControl Control Overview</span></span>](../../../../docs/framework/winforms/controls/tabcontrol-control-overview-windows-forms.md)  
 [<span data-ttu-id="06319-117">방법: Windows Forms TabControl의 모양 변경</span><span class="sxs-lookup"><span data-stu-id="06319-117">How to: Change the Appearance of the Windows Forms TabControl</span></span>](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)  
 [<span data-ttu-id="06319-118">방법: 탭 페이지 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="06319-118">How to: Disable Tab Pages</span></span>](../../../../docs/framework/winforms/controls/how-to-disable-tab-pages.md)  
 [<span data-ttu-id="06319-119">방법: Windows Forms TabControl을 사용하여 탭 추가 및 제거</span><span class="sxs-lookup"><span data-stu-id="06319-119">How to: Add and Remove Tabs with the Windows Forms TabControl</span></span>](../../../../docs/framework/winforms/controls/how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)
