---
title: "StatusBar 컨트롤(Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- StatusBar control [Windows Forms]
- status bars [Windows Forms], creating
ms.assetid: 6f543e27-cf78-4b7f-b4d0-6a8030155d48
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 775d1a350075811dc02ae33efd1a6ae05328c4ff
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="statusbar-control-windows-forms"></a><span data-ttu-id="9d97c-102">StatusBar 컨트롤(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="9d97c-102">StatusBar Control (Windows Forms)</span></span>
> [!NOTE]
>  <span data-ttu-id="9d97c-103"><xref:System.Windows.Forms.ToolStripStatusLabel> 컨트롤은 <xref:System.Windows.Forms.StatusBar> 컨트롤을 대체하고 여기에 다른 기능을 추가하여 새로 도입된 컨트롤이지만 이전 버전과의 호환성 및 이후 사용 가능성을 고려하여 <xref:System.Windows.Forms.StatusBar> 컨트롤을 계속 유지하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d97c-103">The <xref:System.Windows.Forms.ToolStripStatusLabel> control replaces and adds functionality to the <xref:System.Windows.Forms.StatusBar> control; however, the <xref:System.Windows.Forms.StatusBar> control is retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="9d97c-104">Windows Forms <xref:System.Windows.Forms.StatusBar> 컨트롤은 폼에서 응용 프로그램이 다양한 종류의 상태 정보를 표시할 수 있는, 대개 창 아래쪽에 표시되는 영역으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d97c-104">The Windows Forms <xref:System.Windows.Forms.StatusBar> control is used on forms as an area, usually displayed at the bottom of a window, in which an application can display various kinds of status information.</span></span> <span data-ttu-id="9d97c-105"><xref:System.Windows.Forms.StatusBar>컨트롤은 아이콘을 나타내는 상태 또는 일련의 프로세스; 진행 중임 애니메이션 아이콘을 표시 하는 상태 표시줄 패널에 있을 수 있습니다. 예를 들어 있음을 나타내는 Microsoft Word 문서는 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d97c-105"><xref:System.Windows.Forms.StatusBar> controls can have status-bar panels on them that display icons to indicate state, or a series of icons in an animation that indicate a process is working; for example, Microsoft Word indicating that the document is being saved.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9d97c-106">단원 내용</span><span class="sxs-lookup"><span data-stu-id="9d97c-106">In This Section</span></span>  
 [<span data-ttu-id="9d97c-107">StatusBar 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="9d97c-107">StatusBar Control Overview</span></span>](../../../../docs/framework/winforms/controls/statusbar-control-overview-windows-forms.md)  
 <span data-ttu-id="9d97c-108">일반적인 개념을 소개는 <xref:System.Windows.Forms.StatusBar> 컨트롤에 포커스가 있는 컨트롤에 대 한 관련 정보를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d97c-108">Introduces the general concepts of the <xref:System.Windows.Forms.StatusBar> control, which enables users to see relevant information for the control that has focus.</span></span>  
  
 [<span data-ttu-id="9d97c-109">방법: StatusBar 컨트롤에 패널 추가</span><span class="sxs-lookup"><span data-stu-id="9d97c-109">How to: Add Panels to a StatusBar Control</span></span>](../../../../docs/framework/winforms/controls/how-to-add-panels-to-a-statusbar-control.md)  
 <span data-ttu-id="9d97c-110">프로그래밍 가능한 패널을 추가 하는 방법에 설명 된 <xref:System.Windows.Forms.StatusBar> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d97c-110">Explains how to add programmable panels to the <xref:System.Windows.Forms.StatusBar> control.</span></span>  
  
 [<span data-ttu-id="9d97c-111">방법: Windows Forms StatusBar 컨트롤에서 클릭한 패널 확인</span><span class="sxs-lookup"><span data-stu-id="9d97c-111">How to: Determine Which Panel in the Windows Forms StatusBar Control Was Clicked</span></span>](../../../../docs/framework/winforms/controls/determine-which-panel-wf-statusbar-control-was-clicked.md)  
 <span data-ttu-id="9d97c-112">처리 하는 방법에 설명 <xref:System.Windows.Forms.Control.Click> 에서 발생 하는 이벤트는 <xref:System.Windows.Forms.StatusBar> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d97c-112">Explains how to handle <xref:System.Windows.Forms.Control.Click> events raised from the <xref:System.Windows.Forms.StatusBar> control.</span></span>  
  
 [<span data-ttu-id="9d97c-113">방법: 상태 표시줄 패널의 크기 설정</span><span class="sxs-lookup"><span data-stu-id="9d97c-113">How to: Set the Size of Status-Bar Panels</span></span>](../../../../docs/framework/winforms/controls/how-to-set-the-size-of-status-bar-panels.md)  
 <span data-ttu-id="9d97c-114">너비를 제어 하 고 런타임에 상태 표시줄 패널의 동작을 조정 하는 속성에 자세히 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d97c-114">Gives details on the properties that control the width and resize behavior of status-bar panels at run time.</span></span>  
  
 [<span data-ttu-id="9d97c-115">연습: 런타임에 상태 표시줄 정보 업데이트</span><span class="sxs-lookup"><span data-stu-id="9d97c-115">Walkthrough: Updating Status Bar Information at Run Time</span></span>](../../../../docs/framework/winforms/controls/walkthrough-updating-status-bar-information-at-run-time.md)  
 <span data-ttu-id="9d97c-116">상태 표시줄 패널 내에서 데이터를 프로그래밍 방식으로 제어 하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d97c-116">Explains how to programmatically control the data within status-bar panels.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="9d97c-117">참조</span><span class="sxs-lookup"><span data-stu-id="9d97c-117">Reference</span></span>  
 <xref:System.Windows.Forms.StatusBar>  
 <span data-ttu-id="9d97c-118">클래스 및 해당 멤버에 대한 참조 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9d97c-118">Provides reference information on the class and its members.</span></span>  
  
 <xref:System.Windows.Forms.ToolStripStatusLabel>  
 <span data-ttu-id="9d97c-119">대체 하 고 여기에 새로운 기능이 추가 된 <xref:System.Windows.Forms.StatusBar> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d97c-119">Replaces and adds functionality to the <xref:System.Windows.Forms.StatusBar> control.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="9d97c-120">관련 단원</span><span class="sxs-lookup"><span data-stu-id="9d97c-120">Related Sections</span></span>  
 [<span data-ttu-id="9d97c-121">Windows Forms에 사용할 수 있는 컨트롤</span><span class="sxs-lookup"><span data-stu-id="9d97c-121">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 <span data-ttu-id="9d97c-122">사용 방법에 대한 정보 링크를 포함하는 Windows Forms 컨트롤의 전체 목록을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9d97c-122">Provides a complete list of Windows Forms controls, with links to information on their use.</span></span>
