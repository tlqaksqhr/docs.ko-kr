---
title: "방법: 디자이너를 사용하여 Windows Forms 패널의 배경 설정"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- background colors [Windows Forms], Windows Forms Panel controls
- background images [Windows Forms], Windows Forms Panel controls
- Panel control [Windows Forms], background
- colors [Windows Forms], Windows Forms Panel controls
ms.assetid: db83cf54-3c69-4b08-ac6c-25b9b5abb1b0
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 451fa6433a53255f5fe45557c2d8b03ac319de71
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-set-the-background-of-a-windows-forms-panel-using-the-designer"></a><span data-ttu-id="4361c-102">방법: 디자이너를 사용하여 Windows Forms 패널의 배경 설정</span><span class="sxs-lookup"><span data-stu-id="4361c-102">How to: Set the Background of a Windows Forms Panel Using the Designer</span></span>
<span data-ttu-id="4361c-103">Windows Forms <xref:System.Windows.Forms.Panel> 컨트롤 배경 색과 배경 이미지를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4361c-103">A Windows Forms <xref:System.Windows.Forms.Panel> control can display both a background color and a background image.</span></span> <span data-ttu-id="4361c-104"><xref:System.Windows.Forms.Control.BackColor%2A> 속성 예: 레이블 패널에 포함 된는 라디오 단추 컨트롤에 대 한 배경색을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4361c-104">The <xref:System.Windows.Forms.Control.BackColor%2A> property sets the background color for controls that are contained in the panel, such as labels and radio buttons.</span></span> <span data-ttu-id="4361c-105">경우는 <xref:System.Windows.Forms.Control.BackgroundImage%2A> 속성이 설정 되어 있지는 <xref:System.Windows.Forms.Control.BackColor%2A> 패널의 모든 선택 영역을 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="4361c-105">If the <xref:System.Windows.Forms.Control.BackgroundImage%2A> property is not set, the <xref:System.Windows.Forms.Control.BackColor%2A> selection will fill all of the panel.</span></span> <span data-ttu-id="4361c-106">경우는 <xref:System.Windows.Forms.Control.BackgroundImage%2A> 속성이 설정 되어 있으면 패널에 포함 된 컨트롤 뒤에 이미지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4361c-106">If the <xref:System.Windows.Forms.Control.BackgroundImage%2A> property is set, the image will be displayed behind the controls that are contained in the panel.</span></span>  
  
 <span data-ttu-id="4361c-107">다음 절차를 수행 하려면는 **Windows 응용 프로그램** 포함 하는 폼을 사용 하 여 프로젝트는 <xref:System.Windows.Forms.Panel> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="4361c-107">The following procedure requires a **Windows Application** project with a form that contains a <xref:System.Windows.Forms.Panel> control.</span></span> <span data-ttu-id="4361c-108">이러한 프로젝트를 설정 하는 방법에 대 한 정보를 참조 하십시오. [하는 방법: Windows 응용 프로그램 프로젝트 만들기](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) 및 [하는 방법: Windows Forms에 컨트롤 추가](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4361c-108">For information about how to set up such a project, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) and [How to: Add Controls to Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4361c-109">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4361c-109">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="4361c-110">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4361c-110">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="4361c-111">자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4361c-111">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-set-the-background-in-the-windows-forms-designer"></a><span data-ttu-id="4361c-112">Windows Forms 디자이너의 배경 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="4361c-112">To set the background in the Windows Forms Designer</span></span>  
  
1.  <span data-ttu-id="4361c-113"><xref:System.Windows.Forms.Panel> 컨트롤을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4361c-113">Select the <xref:System.Windows.Forms.Panel> control.</span></span>  
  
2.  <span data-ttu-id="4361c-114">에 **속성** 창에서 화살표 단추 옆에를 클릭은 <xref:System.Windows.Forms.Control.BackColor%2A> 속성을 3 개의 탭이 포함 된 창을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="4361c-114">In the **Properties** window, click the arrow button next to the <xref:System.Windows.Forms.Control.BackColor%2A> property to display a window with three tabs.</span></span>  
  
3.  <span data-ttu-id="4361c-115">선택 된 **사용자 지정** 탭 색의 팔레트를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="4361c-115">Select the **Custom** tab to display a palette of colors.</span></span>  
  
4.  <span data-ttu-id="4361c-116">선택 된 **웹** 또는 **시스템** 미리 정의 된 색 이름 목록을 표시 하려면 탭 한 다음 색을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4361c-116">Select the **Web** or **System** tab to display a list of predefined names for colors, and then select a color.</span></span>  
  
5.  <span data-ttu-id="4361c-117">에 **속성** 창, 화살표 옆에 단추 클릭은 <xref:System.Windows.Forms.Control.BackgroundImage%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="4361c-117">In the **Properties** window, click the arrow button next to the <xref:System.Windows.Forms.Control.BackgroundImage%2A> property.</span></span>  
  
6.  <span data-ttu-id="4361c-118">에 **열려** 대화 상자에서 파일을 표시 하려면 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4361c-118">In the **Open** dialog box, select the file that you want to display.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4361c-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4361c-119">See Also</span></span>  
 <xref:System.Windows.Forms.Control.BackColor%2A>  
 <xref:System.Windows.Forms.Control.BackgroundImage%2A>  
 [<span data-ttu-id="4361c-120">Panel 컨트롤</span><span class="sxs-lookup"><span data-stu-id="4361c-120">Panel Control</span></span>](../../../../docs/framework/winforms/controls/panel-control-windows-forms.md)  
 [<span data-ttu-id="4361c-121">Panel 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="4361c-121">Panel Control Overview</span></span>](../../../../docs/framework/winforms/controls/panel-control-overview-windows-forms.md)  
 [<span data-ttu-id="4361c-122">방법: 디자이너에서 Windows Forms 패널 컨트롤을 사용하여 컨트롤 그룹화</span><span class="sxs-lookup"><span data-stu-id="4361c-122">How to: Group Controls with the Windows Forms Panel Control Using the Designer</span></span>](../../../../docs/framework/winforms/controls/group-controls-with-wf-panel-control-using-the-designer.md)
