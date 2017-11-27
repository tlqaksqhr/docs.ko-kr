---
title: "방법: 디자이너를 사용하여 Windows Forms ListView 컨트롤에 열 추가"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ListView control [Windows Forms], adding column headers
- columns [Windows Forms], adding to ListView controls
ms.assetid: 5b1a8b4d-587e-479a-95c1-f9b90884f13a
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7223fc47c885b7e659b9bab00c276759410d2567
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-add-columns-to-the-windows-forms-listview-control-using-the-designer"></a><span data-ttu-id="e256e-102">방법: 디자이너를 사용하여 Windows Forms ListView 컨트롤에 열 추가</span><span class="sxs-lookup"><span data-stu-id="e256e-102">How to: Add Columns to the Windows Forms ListView Control Using the Designer</span></span>
<span data-ttu-id="e256e-103">Windows Forms <xref:System.Windows.Forms.ListView> 컨트롤 각 목록에 대 한 여러 열을 표시할 수 있습니다에 때 항목는 **세부 정보** 보기.</span><span class="sxs-lookup"><span data-stu-id="e256e-103">The Windows Forms <xref:System.Windows.Forms.ListView> control can display multiple columns for each list item when in the **Details** view.</span></span> <span data-ttu-id="e256e-104">여러 유형의 각 목록 항목에 대 한 정보를 표시 하는 열을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e256e-104">You can use the columns to display several types of information about each list item.</span></span> <span data-ttu-id="e256e-105">예를 들어 파일 이름, 파일 형식, 크기 및 파일을 마지막으로 수정한 날짜 파일의 목록을 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e256e-105">For example, a list of files could display the file name, file type, size, and date the file was last modified.</span></span> <span data-ttu-id="e256e-106">작성 된 후 열을 채우는 방법에 대 한 정보를 참조 하십시오. [하는 방법: Windows Forms ListView 컨트롤에서 열에 하위 항목 표시](../../../../docs/framework/winforms/controls/how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e256e-106">For information on populating the columns once they are created, see [How to: Display Subitems in Columns with the Windows Forms ListView Control](../../../../docs/framework/winforms/controls/how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md).</span></span>  
  
 <span data-ttu-id="e256e-107">다음 절차를 수행 하려면는 **Windows 응용 프로그램** 포함 된 폼을 사용 하 여 프로젝트는 <xref:System.Windows.Forms.ListView> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="e256e-107">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.ListView> control.</span></span> <span data-ttu-id="e256e-108">이러한 프로젝트 설정에 대 한 정보를 참조 하십시오. [하는 방법: Windows 응용 프로그램 프로젝트 만들기](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa) 및 [하는 방법: Windows Forms에 컨트롤 추가](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e256e-108">For information about setting up such a project, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa) and [How to: Add Controls to Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e256e-109">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e256e-109">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="e256e-110">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e256e-110">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="e256e-111">자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e256e-111">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-add-columns-in-the-designer"></a><span data-ttu-id="e256e-112">디자이너에서 열을 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="e256e-112">To add columns in the designer</span></span>  
  
1.  <span data-ttu-id="e256e-113">에 **속성** 창의 컨트롤의 설정 <xref:System.Windows.Forms.ListView.View%2A> 속성을 <xref:System.Windows.Forms.View.Details>합니다.</span><span class="sxs-lookup"><span data-stu-id="e256e-113">In the **Properties** window, set the control's <xref:System.Windows.Forms.ListView.View%2A> property to <xref:System.Windows.Forms.View.Details>.</span></span>  
  
2.  <span data-ttu-id="e256e-114">에 **속성** 창 클릭는 **줄임표** 단추 (![VisualStudioEllipsesButton 스크린 샷](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) 옆에 <xref:System.Windows.Forms.ListView.Columns%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="e256e-114">In the **Properties** window, click the **Ellipsis** button (![VisualStudioEllipsesButton screenshot](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) next to the <xref:System.Windows.Forms.ListView.Columns%2A> property.</span></span>  
  
     <span data-ttu-id="e256e-115">**ColumnHeader 컬렉션 편집기** 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="e256e-115">The **ColumnHeader Collection Editor** appears.</span></span>  
  
3.  <span data-ttu-id="e256e-116">사용 하 여는 **추가** 단추 새 열을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="e256e-116">Use the **Add** button to add new columns.</span></span> <span data-ttu-id="e256e-117">다음 열 머리글을 선택 하 고 해당 텍스트 (열 캡션), 텍스트 맞춤 및 두께 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e256e-117">You can then select the column header and set its text (the caption of the column), text alignment, and width.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e256e-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e256e-118">See Also</span></span>  
 [<span data-ttu-id="e256e-119">ListView 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="e256e-119">ListView Control Overview</span></span>](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)  
 [<span data-ttu-id="e256e-120">방법: Windows Forms ListView 컨트롤을 사용하여 항목 추가 및 제거</span><span class="sxs-lookup"><span data-stu-id="e256e-120">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)  
 [<span data-ttu-id="e256e-121">방법: Windows Forms ListView 컨트롤을 사용하여 열에 하위 항목 표시</span><span class="sxs-lookup"><span data-stu-id="e256e-121">How to: Display Subitems in Columns with the Windows Forms ListView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)  
 [<span data-ttu-id="e256e-122">방법: Windows Forms ListView 컨트롤의 아이콘 표시</span><span class="sxs-lookup"><span data-stu-id="e256e-122">How to: Display Icons for the Windows Forms ListView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-display-icons-for-the-windows-forms-listview-control.md)  
 [<span data-ttu-id="e256e-123">방법: TreeView 또는 ListView 컨트롤에 사용자 지정 정보 추가(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="e256e-123">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)
