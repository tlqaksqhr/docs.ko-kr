---
title: "NotifyIcon 구성 요소 개요(Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- NotifyIcon
helpviewer_keywords:
- NotifyIcon component [Windows Forms], about NotifyIcon component
- system tray icons [Windows Forms], about system tray icons
- system tray icons [Windows Forms], using in Windows Forms
ms.assetid: 5b9189fa-d4ae-41a6-9b97-eb1f44bb1a69
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 8c909537bd4c52a546faeb83c6e9291c4de76d76
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="notifyicon-component-overview-windows-forms"></a><span data-ttu-id="ba388-102">NotifyIcon 구성 요소 개요(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="ba388-102">NotifyIcon Component Overview (Windows Forms)</span></span>
<span data-ttu-id="ba388-103">Windows Forms <xref:System.Windows.Forms.NotifyIcon> 구성 요소는 일반적으로 백그라운드에서 실행되고 대체로 사용자 인터페이스를 표시하지 않는 프로세스에 대한 아이콘을 표시하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba388-103">The Windows Forms <xref:System.Windows.Forms.NotifyIcon> component is typically used to display icons for processes that run in the background and do not show a user interface much of the time.</span></span> <span data-ttu-id="ba388-104">예를 들어 작업 표시줄의 상태 알림 영역에서 아이콘을 클릭하여 액세스할 수 있는 바이러스 방지 프로그램이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba388-104">An example would be a virus protection program that can be accessed by clicking an icon in the status notification area of the taskbar.</span></span>  
  
## <a name="key-properties-of-notifyicons"></a><span data-ttu-id="ba388-105">NotifyIcons의 키 속성</span><span class="sxs-lookup"><span data-stu-id="ba388-105">Key Properties of NotifyIcons</span></span>  
 <span data-ttu-id="ba388-106">각 <xref:System.Windows.Forms.NotifyIcon> 구성 요소는 상태 영역에 단일 아이콘을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="ba388-106">Each <xref:System.Windows.Forms.NotifyIcon> component displays a single icon in the status area.</span></span> <span data-ttu-id="ba388-107">3개의 백그라운드 프로세스가 있고 각 프로세스에 대한 아이콘을 표시하려는 경우 <xref:System.Windows.Forms.NotifyIcon> 구성 요소 3개를 폼에 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba388-107">If you have three background processes and wish to display an icon for each, you must add three <xref:System.Windows.Forms.NotifyIcon> components to the form.</span></span> <span data-ttu-id="ba388-108"><xref:System.Windows.Forms.NotifyIcon> 구성 요소의 키 속성은 <xref:System.Windows.Forms.NotifyIcon.Icon%2A> 및 <xref:System.Windows.Forms.NotifyIcon.Visible%2A>입니다.</span><span class="sxs-lookup"><span data-stu-id="ba388-108">The key properties of the <xref:System.Windows.Forms.NotifyIcon> component are <xref:System.Windows.Forms.NotifyIcon.Icon%2A> and <xref:System.Windows.Forms.NotifyIcon.Visible%2A>.</span></span> <span data-ttu-id="ba388-109"><xref:System.Windows.Forms.NotifyIcon.Icon%2A> 속성은 상태 영역에 표시되는 아이콘을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ba388-109">The <xref:System.Windows.Forms.NotifyIcon.Icon%2A> property sets the icon that appears in the status area.</span></span> <span data-ttu-id="ba388-110">아이콘이 표시되려면 <xref:System.Windows.Forms.NotifyIcon.Visible%2A> 속성을 `true`로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba388-110">In order for the icon to appear, the <xref:System.Windows.Forms.NotifyIcon.Visible%2A> property must be set to `true`.</span></span>  
  
 <span data-ttu-id="ba388-111">[!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)]를 사용 중인 경우 <xref:System.Windows.Forms.NotifyIcon> 컨트롤에 사용할 수 있는 표준 이미지의 대규모 라이브러리에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba388-111">If you are using [!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)], you have access to a large library of standard images that you can use with the <xref:System.Windows.Forms.NotifyIcon> control.</span></span>  
  
## <a name="notifyicons-options"></a><span data-ttu-id="ba388-112">NotifyIcons 옵션</span><span class="sxs-lookup"><span data-stu-id="ba388-112">NotifyIcons Options</span></span>  
 <span data-ttu-id="ba388-113">풍선 설명, 바로 가기 메뉴 및 도구 설명을 <xref:System.Windows.Forms.NotifyIcon>에 연결하여 사용자를 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba388-113">You can associate balloon tips, shortcut menus, and ToolTips with a <xref:System.Windows.Forms.NotifyIcon> to assist the user.</span></span>  
  
 <span data-ttu-id="ba388-114">풍선 설명을 표시할 시간 범위를 지정하고 <xref:System.Windows.Forms.NotifyIcon.ShowBalloonTip%2A> 메서드를 호출하여 <xref:System.Windows.Forms.NotifyIcon>에 대한 풍선 설명을 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba388-114">You can display balloon tips for a <xref:System.Windows.Forms.NotifyIcon> by calling the <xref:System.Windows.Forms.NotifyIcon.ShowBalloonTip%2A> method specifying the time span you wish the balloon tip to display.</span></span> <span data-ttu-id="ba388-115"><xref:System.Windows.Forms.NotifyIcon.BalloonTipText%2A>, <xref:System.Windows.Forms.NotifyIcon.BalloonTipIcon%2A> 및 <xref:System.Windows.Forms.NotifyIcon.BalloonTipTitle%2A>을 각각 사용하여 풍선 설명의 텍스트, 아이콘 및 제목을 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba388-115">You can also specify the text, icon and title of the balloon tip with the <xref:System.Windows.Forms.NotifyIcon.BalloonTipText%2A>, <xref:System.Windows.Forms.NotifyIcon.BalloonTipIcon%2A> and <xref:System.Windows.Forms.NotifyIcon.BalloonTipTitle%2A>, respectively.</span></span> <span data-ttu-id="ba388-116"><xref:System.Windows.Forms.NotifyIcon> 구성 요소에 연결된 도구 설명 및 바로 가기 메뉴가 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba388-116"><xref:System.Windows.Forms.NotifyIcon> components can also have associated ToolTips and shortcut menus.</span></span> <span data-ttu-id="ba388-117">자세한 내용은 참조 [ToolTip 구성 요소 개요](../../../../docs/framework/winforms/controls/tooltip-component-overview-windows-forms.md) 및 [ContextMenu 구성 요소 개요](../../../../docs/framework/winforms/controls/contextmenu-component-overview-windows-forms.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ba388-117">For more information, see [ToolTip Component Overview](../../../../docs/framework/winforms/controls/tooltip-component-overview-windows-forms.md) and [ContextMenu Component Overview](../../../../docs/framework/winforms/controls/contextmenu-component-overview-windows-forms.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba388-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ba388-118">See Also</span></span>  
 <xref:System.Windows.Forms.NotifyIcon>  
 [<span data-ttu-id="ba388-119">NotifyIcon 구성 요소</span><span class="sxs-lookup"><span data-stu-id="ba388-119">NotifyIcon Component</span></span>](../../../../docs/framework/winforms/controls/notifyicon-component-windows-forms.md)
