---
title: "StatusBar 컨트롤 개요(Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: StatusBar
helpviewer_keywords:
- StatusBar control [Windows Forms], about StatusBar control
- status bars
ms.assetid: b7b9852c-633d-4416-bb2e-94852b989c6c
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: df8e6b8484cf3b35c684445445ddc41adc358698
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="statusbar-control-overview-windows-forms"></a><span data-ttu-id="1f80d-102">StatusBar 컨트롤 개요(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="1f80d-102">StatusBar Control Overview (Windows Forms)</span></span>
> [!IMPORTANT]
>  <span data-ttu-id="1f80d-103"><xref:System.Windows.Forms.StatusStrip> 및 <xref:System.Windows.Forms.ToolStripStatusLabel> 컨트롤 교체 및 기능을 추가 <xref:System.Windows.Forms.StatusBar> 및 <xref:System.Windows.Forms.StatusBarPanel> 제어; 그러나는 <xref:System.Windows.Forms.StatusBar> 및 <xref:System.Windows.Forms.StatusBarPanel> 버전과 호환성 및 이후 사용에 대 한 컨트롤이 유지 되는 경우 있습니다 이 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f80d-103">The <xref:System.Windows.Forms.StatusStrip> and <xref:System.Windows.Forms.ToolStripStatusLabel> controls replace and add functionality to the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls; however, the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls are retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="1f80d-104">Windows Forms [StatusBar 컨트롤](../../../../docs/framework/winforms/controls/statusbar-control-windows-forms.md) 폼에서 일반적으로 응용 프로그램이 다양 한 종류의 상태 정보를 표시할 수는 창의 맨 아래에 표시 되는 영역으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f80d-104">The Windows Forms [StatusBar Control](../../../../docs/framework/winforms/controls/statusbar-control-windows-forms.md) is used on forms as an area, usually displayed at the bottom of a window, in which an application can display various kinds of status information.</span></span> <span data-ttu-id="1f80d-105"><xref:System.Windows.Forms.StatusBar>컨트롤에 텍스트 또는 아이콘을 나타내는 상태 또는 일련의 프로세스; 진행 중임 애니메이션 아이콘을 표시 하는 상태 표시줄 패널에 있을 수 있습니다. 예를 들어 [!INCLUDE[ofprword](../../../../includes/ofprword-md.md)] 나타내는 문서를 저장 하는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="1f80d-105"><xref:System.Windows.Forms.StatusBar> controls can have status bar panels on them that display text or icons to indicate state, or a series of icons in an animation that indicate a process is working; for example, [!INCLUDE[ofprword](../../../../includes/ofprword-md.md)] indicating that the document is being saved.</span></span>  
  
## <a name="using-the-statusbar-control"></a><span data-ttu-id="1f80d-106">StatusBar 컨트롤을 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="1f80d-106">Using the StatusBar Control</span></span>  
 <span data-ttu-id="1f80d-107">Internet Explorer에서 상태 표시줄을 사용 하 여 하이퍼링크; 위로 마우스를 가져가면 페이지의 URL이 표시를 [!INCLUDE[ofprword](../../../../includes/ofprword-md.md)] 페이지 위치, 섹션 위치 및 겹쳐쓰기 및 변경 내용 추적; 등 편집 모드에 대 한 정보 제공 및 [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] 도킹 가능한 조작 하는 방법을 알려 주는 등의 상황에 맞는 정보를 제공 하는 상태 표시줄을 사용 하 여 창 또는 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f80d-107">Internet Explorer uses a status bar to indicate the URL of a page when the mouse rolls over the hyperlink; [!INCLUDE[ofprword](../../../../includes/ofprword-md.md)] gives you information on page location, section location, and editing modes such as overtype and revision tracking; and [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] uses the status bar to give context-sensitive information, such as telling you how to manipulate dockable windows as either docked or floating.</span></span>  
  
 <span data-ttu-id="1f80d-108">설정 하 여 상태 표시줄에 단일 메시지를 표시할 수는 <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> 속성을 `false` (기본값) 설정의 <xref:System.Windows.Forms.StatusBar.Text%2A> 상태 표시줄에 표시할 텍스트 상태 표시줄의 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="1f80d-108">You can display a single message on the status bar by setting the <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> property to `false` (the default) and setting the <xref:System.Windows.Forms.StatusBar.Text%2A> property of the status bar to the text you want to appear in the status bar.</span></span> <span data-ttu-id="1f80d-109">상태 표시줄 패널을 설정 하 여 둘 이상의 유형의 정보를 표시할 여러 개로 나눌 수는 <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> 속성을 `true` 를 사용 하 고는 <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection.Add%2A> 방식의 <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection>합니다.</span><span class="sxs-lookup"><span data-stu-id="1f80d-109">You can divide the status bar into panels to display more than one type of information by setting the <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> property to `true` and using the <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection.Add%2A> method of <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f80d-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1f80d-110">See Also</span></span>  
 <xref:System.Windows.Forms.StatusBar>  
 <xref:System.Windows.Forms.ToolStripStatusLabel>  
 [<span data-ttu-id="1f80d-111">방법: Windows Forms StatusBar 컨트롤에서 클릭한 패널 확인</span><span class="sxs-lookup"><span data-stu-id="1f80d-111">How to: Determine Which Panel in the Windows Forms StatusBar Control Was Clicked</span></span>](../../../../docs/framework/winforms/controls/determine-which-panel-wf-statusbar-control-was-clicked.md)
