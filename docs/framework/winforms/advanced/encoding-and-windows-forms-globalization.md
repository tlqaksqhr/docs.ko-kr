---
title: "인코딩 및 Windows Forms 전역화"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ListView control [Windows Forms], lack of Unicode support
- DateTimePicker control [Windows Forms], lack of Unicode support
- TrackBar control [Windows Forms], lack of Unicode support
- ImageList component [Windows Forms], lack of Unicode support
- Unicode [Windows Forms]
- ToolBar control [Windows Forms], lack of Unicode support
- international applications [Windows Forms], character display
- StatusBar control [Windows Forms], lack of Unicode support
- MonthCalendar control [Windows Forms], lack of Unicode support
- international characters
- TabControl control [Windows Forms], lack of Unicode support
- Windows Forms, encoding
- TreeView control [Windows Forms], lack of Unicode support
- ProgressBar control [Windows Forms], Unicode-enabled forms
- localization [Windows Forms], character sets
- globalization [Windows Forms], character sets
ms.assetid: 22e8965d-a712-42b3-8167-3ee346bd70f9
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f25f4f7206b68e961f3c09a488af643ad5d0a4fd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="encoding-and-windows-forms-globalization"></a><span data-ttu-id="3752a-102">인코딩 및 Windows Forms 전역화</span><span class="sxs-lookup"><span data-stu-id="3752a-102">Encoding and Windows Forms Globalization</span></span>
<span data-ttu-id="3752a-103">Windows Forms 응용 프로그램은 완전히 유니코드를 사용할 수 있으므로 플랫폼, 프로그램 또는 언어에 관계없이 각 문자가 고유한 숫자로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3752a-103">Windows Forms applications are entirely Unicode-enabled, meaning that each character is represented by a unique number, no matter what the platform, program, or language.</span></span> <span data-ttu-id="3752a-104">유니코드에 대 한 자세한 내용은 참조는 [유니코드 컨소시엄 웹 사이트](http://www.unicode.org)합니다.</span><span class="sxs-lookup"><span data-stu-id="3752a-104">For more information about Unicode, see the [Unicode consortium Web site](http://www.unicode.org).</span></span>  
  
## <a name="benefits-of-unicode"></a><span data-ttu-id="3752a-105">유니코드의 이점</span><span class="sxs-lookup"><span data-stu-id="3752a-105">Benefits of Unicode</span></span>  
 <span data-ttu-id="3752a-106">유니코드 사용 폼의 이점에는 힌디어와 같은 유니코드 전용 스크립트로 작업할 수 있는 기능이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="3752a-106">The benefits of Unicode-enabled forms include the ability to work with scripts that are Unicode-only, such as Hindi.</span></span> <span data-ttu-id="3752a-107">또한 단일 폼에서 여러 언어를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3752a-107">In addition, you can use multiple languages on a single form.</span></span> <span data-ttu-id="3752a-108">유니코드에서는 모든 문자가 2바이트 길이이므로 더블바이트 문자를 나타내기 위한 특별한 작업이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3752a-108">In Unicode, all characters are two bytes long, so no special effort is needed to represent double-byte characters.</span></span> <span data-ttu-id="3752a-109">모든 플랫폼에서 작동하는 단일 코드 집합을 작성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3752a-109">You can also write a single set of code that will work on all platforms.</span></span> <span data-ttu-id="3752a-110">이는 Windows NT, [!INCLUDE[win98](../../../../includes/win98-md.md)] 등의 플랫폼마다 각기 다른 코드를 작성해야 했던 이전 버전의 [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)]에서 변경된 내용입니다.</span><span class="sxs-lookup"><span data-stu-id="3752a-110">This is a change from previous versions of [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)], in which you had to write different code for different platforms, such as Windows NT and [!INCLUDE[win98](../../../../includes/win98-md.md)].</span></span>  
  
 <span data-ttu-id="3752a-111">그러나 특정 컨트롤은 [!INCLUDE[win98](../../../../includes/win98-md.md)] 및 Windows Millennium Edition에서 유니코드를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3752a-111">However, certain controls do not support Unicode in [!INCLUDE[win98](../../../../includes/win98-md.md)] and Windows Millennium Edition.</span></span> <span data-ttu-id="3752a-112">모두 공용 컨트롤에서 상속되는 이러한 컨트롤은 Windows 코드 페이지에서 [!INCLUDE[vcpransi](../../../../includes/vcpransi-md.md)]로 데이터를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="3752a-112">These controls, all of which inherit from the common control, will process data with the Windows code pages, as [!INCLUDE[vcpransi](../../../../includes/vcpransi-md.md)].</span></span> <span data-ttu-id="3752a-113">해당 컨트롤은 <xref:System.Windows.Forms.TabControl>, <xref:System.Windows.Forms.ListView>, <xref:System.Windows.Forms.TreeView>, <xref:System.Windows.Forms.DateTimePicker>, <xref:System.Windows.Forms.MonthCalendar>, <xref:System.Windows.Forms.TrackBar>, <xref:System.Windows.Forms.ProgressBar>, <xref:System.Windows.Forms.ImageList>, <xref:System.Windows.Forms.ToolBar> 및 <xref:System.Windows.Forms.StatusBar>입니다.</span><span class="sxs-lookup"><span data-stu-id="3752a-113">These controls are: <xref:System.Windows.Forms.TabControl>, <xref:System.Windows.Forms.ListView>, <xref:System.Windows.Forms.TreeView>, <xref:System.Windows.Forms.DateTimePicker>, <xref:System.Windows.Forms.MonthCalendar>, <xref:System.Windows.Forms.TrackBar>, <xref:System.Windows.Forms.ProgressBar>, <xref:System.Windows.Forms.ImageList>, <xref:System.Windows.Forms.ToolBar>, and <xref:System.Windows.Forms.StatusBar>.</span></span> <span data-ttu-id="3752a-114">따라서 나열된 플랫폼의 이 컨트롤에는 유니코드 데이터를 표시할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3752a-114">As a result, you cannot display Unicode data in these controls on the listed platforms.</span></span> <span data-ttu-id="3752a-115">예를 들어 영어 [!INCLUDE[win98](../../../../includes/win98-md.md)] 운영 체제에서는 일본어 문자를 표시할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3752a-115">For example, you cannot display Japanese characters on an English [!INCLUDE[win98](../../../../includes/win98-md.md)] operating system.</span></span>  
  
 <span data-ttu-id="3752a-116"><xref:System.Windows.Forms.ToolBar> 및 <xref:System.Windows.Forms.StatusBar> 컨트롤에 대한 유니코드 인식 대체 항목으로 이러한 이전 컨트롤을 대체하는 <xref:System.Windows.Forms.ToolStrip> 및 <xref:System.Windows.Forms.StatusStrip> 컨트롤을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3752a-116">For Unicode-aware alternatives to the <xref:System.Windows.Forms.ToolBar> and <xref:System.Windows.Forms.StatusBar> controls, use the <xref:System.Windows.Forms.ToolStrip> and <xref:System.Windows.Forms.StatusStrip> controls, which replace these older controls.</span></span> <span data-ttu-id="3752a-117">응용 프로그램에서 시각적 요소 간에 비슷한 모양과 느낌을 유지 관리하려면 <xref:System.Windows.Forms.MainMenu> 대신 메뉴 렌더링에 <xref:System.Windows.Forms.MenuStrip> 컨트롤을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3752a-117">To maintain a similar look and feel between visual elements in your application, use the <xref:System.Windows.Forms.MenuStrip> control for rendering menus instead of <xref:System.Windows.Forms.MainMenu>.</span></span> <span data-ttu-id="3752a-118"><xref:System.Windows.Forms.ToolStrip> 및 <xref:System.Windows.Forms.StatusStrip>과 마찬가지로, <xref:System.Windows.Forms.MenuStrip>도 유니코드 문자를 처리하고 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3752a-118">Like <xref:System.Windows.Forms.ToolStrip> and <xref:System.Windows.Forms.StatusStrip>, <xref:System.Windows.Forms.MenuStrip> can also process and display Unicode characters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3752a-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3752a-119">See Also</span></span>  
 [<span data-ttu-id="3752a-120">Windows Forms 전역화</span><span class="sxs-lookup"><span data-stu-id="3752a-120">Globalizing Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/globalizing-windows-forms.md)
