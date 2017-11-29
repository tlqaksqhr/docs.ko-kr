---
title: "Windows Forms 응용 프로그램의 도움말 시스템"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Help [Windows Forms], adding to Windows applications
- Windows applications [Windows Forms], providing Help systems
- What's This? Help
- Help [Windows Forms], Windows Forms
- HelpProvider component [Windows Forms], providing Help in Windows applications
ms.assetid: 2a96a278-432c-41fc-9e3c-5bfedf5e1267
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 45d3385d008f823050f213252fdc2e1851cf422b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="help-systems-in-windows-forms-applications"></a><span data-ttu-id="9148b-102">Windows Forms 응용 프로그램의 도움말 시스템</span><span class="sxs-lookup"><span data-stu-id="9148b-102">Help Systems in Windows Forms Applications</span></span>
<span data-ttu-id="9148b-103">하나는 가장 중요 한 행위의, 응용 프로그램 개발자는 사용자를 위해 수 때 유용한 도움말 시스템입니다.</span><span class="sxs-lookup"><span data-stu-id="9148b-103">One of the most important courtesies you, as a developer of applications, can furnish your users with is a competent Help system.</span></span> <span data-ttu-id="9148b-104">이것이 응용 또는 혼동 될 때 설정 됩니다 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9148b-104">This is where they will turn when they become confused or disoriented.</span></span> <span data-ttu-id="9148b-105">Windows 기반 응용 프로그램의 도움말 시스템을 제공 하는 사용 하 여 쉽게 설정할 수는 [HelpProvider 구성 요소](../../../../docs/framework/winforms/controls/helpprovider-component-windows-forms.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9148b-105">Providing a Help system in a Windows-based application is easily done by using the [HelpProvider Component](../../../../docs/framework/winforms/controls/helpprovider-component-windows-forms.md).</span></span>  
  
## <a name="different-types-of-help"></a><span data-ttu-id="9148b-106">다양 한 유형의 도움말</span><span class="sxs-lookup"><span data-stu-id="9148b-106">Different Types of Help</span></span>  
 <span data-ttu-id="9148b-107">Windows Forms <xref:System.Windows.Forms.HelpProvider> 구성 요소는 HTML 도움말 1.x 도움말 파일(HTML Help Workshop으로 생성된 .chm 파일 또는 .htm 파일)을 Windows 기반 응용 프로그램에 연결하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9148b-107">The Windows Forms <xref:System.Windows.Forms.HelpProvider> component is used to associate an HTML Help 1.x Help file (either a .chm file, produced with the HTML Help Workshop, or an .htm file) with your Windows-based application.</span></span> <span data-ttu-id="9148b-108"><xref:System.Windows.Forms.HelpProvider> 특정 컨트롤 또는 Windows Forms에서 컨트롤에 대 한 상황에 맞는 도움말을 제공 하 구성 요소를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9148b-108">The <xref:System.Windows.Forms.HelpProvider> component can be used to provide context-sensitive Help for controls on Windows Forms or specific controls.</span></span> <span data-ttu-id="9148b-109">또한는 <xref:System.Windows.Forms.HelpProvider> 구성 요소는 도움말 파일 목차, 인덱스 또는 검색 기능 테이블의 기본 페이지 등의 특정 영역을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9148b-109">Additionally, the <xref:System.Windows.Forms.HelpProvider> component can open a Help file to specific areas, such as the main page of a table of contents, an index, or a search function.</span></span> <span data-ttu-id="9148b-110">에 대 한 일반 정보에 대 한는 <xref:System.Windows.Forms.HelpProvider> 구성 요소 참조 [HelpProvider 구성 요소 개요](../../../../docs/framework/winforms/controls/helpprovider-component-overview-windows-forms.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9148b-110">For general information about the <xref:System.Windows.Forms.HelpProvider> component, see [HelpProvider Component Overview](../../../../docs/framework/winforms/controls/helpprovider-component-overview-windows-forms.md).</span></span> <span data-ttu-id="9148b-111">사용 하는 방법에 대 한 내용은 <xref:System.Windows.Forms.HelpProvider> Windows Forms에서 팝업 도움말을 표시 하는 구성 요소 참조 [하는 방법: 팝업 도움말 표시](../../../../docs/framework/winforms/advanced/how-to-display-pop-up-help.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9148b-111">For information on how to use the <xref:System.Windows.Forms.HelpProvider> component to show pop-up Help on Windows Forms, see [How to: Display Pop-up Help](../../../../docs/framework/winforms/advanced/how-to-display-pop-up-help.md).</span></span> <span data-ttu-id="9148b-112">사용 하 여에 대 한 내용은 <xref:System.Windows.Forms.ToolTip> 컨트롤 관련 도움말을 표시 하는 구성 요소 참조 [제어 도움말 사용 하 여 도구 설명을](../../../../docs/framework/winforms/advanced/control-help-using-tooltips.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9148b-112">For information on using the <xref:System.Windows.Forms.ToolTip> component to show control-specific Help, see [Control Help Using ToolTips](../../../../docs/framework/winforms/advanced/control-help-using-tooltips.md).</span></span>  
  
 <span data-ttu-id="9148b-113">HTML Help Workshop으로 HTML 도움말 1.x 파일을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9148b-113">You can generate HTML Help 1.x files with the HTML Help Workshop.</span></span> <span data-ttu-id="9148b-114">HTML 도움말에 대 한 자세한 내용은 "HTML Help Workshop" 또는 MSDN에 있는 다른 "HTML Help" 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9148b-114">For more information on HTML Help, see the "HTML Help Workshop" or the other "HTML Help" topics in MSDN.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9148b-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9148b-115">See Also</span></span>  
 [<span data-ttu-id="9148b-116">Windows Forms에 사용자 도움말 통합</span><span class="sxs-lookup"><span data-stu-id="9148b-116">Integrating User Help in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/integrating-user-help-in-windows-forms.md)  
 [<span data-ttu-id="9148b-117">HelpProvider 구성 요소</span><span class="sxs-lookup"><span data-stu-id="9148b-117">HelpProvider Component</span></span>](../../../../docs/framework/winforms/controls/helpprovider-component-windows-forms.md)  
 [<span data-ttu-id="9148b-118">ToolTip 구성 요소</span><span class="sxs-lookup"><span data-stu-id="9148b-118">ToolTip Component</span></span>](../../../../docs/framework/winforms/controls/tooltip-component-windows-forms.md)  
 [<span data-ttu-id="9148b-119">Windows Forms 개요</span><span class="sxs-lookup"><span data-stu-id="9148b-119">Windows Forms Overview</span></span>](../../../../docs/framework/winforms/windows-forms-overview.md)  
 [<span data-ttu-id="9148b-120">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9148b-120">Windows Forms</span></span>](../../../../docs/framework/winforms/index.md)
