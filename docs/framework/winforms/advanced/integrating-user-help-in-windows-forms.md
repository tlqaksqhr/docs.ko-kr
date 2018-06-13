---
title: Windows Forms에 사용자 도움말 통합
ms.date: 03/30/2017
helpviewer_keywords:
- Help [Windows Forms], Windows Forms (using designer)
- Windows Forms, Help (using designer)
- HTML Help [Windows Forms], Windows Forms (using designer)
- Help [Windows Forms], Windows applications (using designer)
- forms. Help (using designer)
- Windows applications [Windows Forms], Help (using designer)
ms.assetid: a8563d25-8a75-4bc7-a024-f1870591b50f
ms.openlocfilehash: b16ba14eea68083cd7bdfc91c88375406137f450
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33527225"
---
# <a name="integrating-user-help-in-windows-forms"></a><span data-ttu-id="73686-102">Windows Forms에 사용자 도움말 통합</span><span class="sxs-lookup"><span data-stu-id="73686-102">Integrating User Help in Windows Forms</span></span>
<span data-ttu-id="73686-103">필수적 이지만 되지만 흔히 간과 되 끝점이 Windows 기반 응용 프로그램을 구축 하는 도움말 시스템을 것이 사용자가 혼동 하는 중에 도움을 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="73686-103">An essential, but often overlooked, aspect of building Windows-based applications is the Help system, as this is where users turn for assistance in times of confusion.</span></span> <span data-ttu-id="73686-104">Windows Forms에는 두 가지 유형의 도움말 지원, 각각에서 제공 되는 [HelpProvider 구성 요소](../../../../docs/framework/winforms/controls/helpprovider-component-windows-forms.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="73686-104">Windows Forms support two different types of Help, each provided by the [HelpProvider Component](../../../../docs/framework/winforms/controls/helpprovider-component-windows-forms.md).</span></span> <span data-ttu-id="73686-105">첫 번째 사용자를 HTML 이나 HTML 도움말 1의 도움말 파일을 가리키는 포함 됩니다. *x* 또는 큰 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="73686-105">The first involves pointing the user to a Help file of either HTML or HTML Help 1.*x* or greater format.</span></span> <span data-ttu-id="73686-106">두 번째 표시할 수 간략 한 "설명 된 설명"-개별 컨트롤; Help를 입력 합니다. 이 대화 상자에서 특히 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="73686-106">The second can display brief "What's This"-type Help on individual controls; this is especially useful on dialog boxes.</span></span> <span data-ttu-id="73686-107">두 가지 유형의 도움말 고 동일한 폼에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73686-107">Both types of Help can be used on the same form.</span></span>  
  
 <span data-ttu-id="73686-108">또한는 [ToolTip 구성 요소](../../../../docs/framework/winforms/controls/tooltip-component-windows-forms.md) 는 Windows Forms에서 컨트롤에 대 한 개별 도움말을 제공 하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73686-108">Additionally, the [ToolTip Component](../../../../docs/framework/winforms/controls/tooltip-component-windows-forms.md) can be used to provide individual Help for controls on Windows Forms.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="73686-109">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="73686-109">In This Section</span></span>  
 [<span data-ttu-id="73686-110">방법: Windows 응용 프로그램에서 도움말 제공</span><span class="sxs-lookup"><span data-stu-id="73686-110">How to: Provide Help in a Windows Application</span></span>](../../../../docs/framework/winforms/advanced/how-to-provide-help-in-a-windows-application.md)  
 <span data-ttu-id="73686-111">사용 하는 방법에 설명 된 `HelpProvider` 도움말 시스템에서 파일에 컨트롤을 연결 하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="73686-111">Explains how to use the `HelpProvider` component to link controls to files in a Help system.</span></span>  
  
 [<span data-ttu-id="73686-112">방법: 팝업 도움말 표시</span><span class="sxs-lookup"><span data-stu-id="73686-112">How to: Display Pop-up Help</span></span>](../../../../docs/framework/winforms/advanced/how-to-display-pop-up-help.md)  
 <span data-ttu-id="73686-113">사용 하는 방법에 설명 된 `HelpProvider` Windows Forms에서 팝업 도움말을 표시 하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="73686-113">Explains how to use the `HelpProvider` component to show pop-up Help on Windows Forms.</span></span>  
  
 [<span data-ttu-id="73686-114">ToolTip을 사용한 컨트롤 도움말</span><span class="sxs-lookup"><span data-stu-id="73686-114">Control Help Using ToolTips</span></span>](../../../../docs/framework/winforms/advanced/control-help-using-tooltips.md)  
 <span data-ttu-id="73686-115">사용 하 여 설명의 `ToolTip` 구성 요소 컨트롤 관련 도움말을 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73686-115">Describes using the `ToolTip` component to show control-specific Help.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="73686-116">관련 단원</span><span class="sxs-lookup"><span data-stu-id="73686-116">Related Sections</span></span>  
 [<span data-ttu-id="73686-117">HelpProvider 구성 요소</span><span class="sxs-lookup"><span data-stu-id="73686-117">HelpProvider Component</span></span>](../../../../docs/framework/winforms/controls/helpprovider-component-windows-forms.md)  
 <span data-ttu-id="73686-118">기본 사항을 설명는 `HelpProvider` 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="73686-118">Explains the basics of the `HelpProvider` component.</span></span>  
  
 [<span data-ttu-id="73686-119">ToolTip 구성 요소</span><span class="sxs-lookup"><span data-stu-id="73686-119">ToolTip Component</span></span>](../../../../docs/framework/winforms/controls/tooltip-component-windows-forms.md)  
 <span data-ttu-id="73686-120">기본 사항을 설명는 `ToolTip` 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="73686-120">Explains the basics of the `ToolTip` component.</span></span>  
  
 [<span data-ttu-id="73686-121">Windows Forms 개요</span><span class="sxs-lookup"><span data-stu-id="73686-121">Windows Forms Overview</span></span>](../../../../docs/framework/winforms/windows-forms-overview.md)  
 <span data-ttu-id="73686-122">Windows Forms의 기본 사항을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="73686-122">Explains the basics of Windows Forms.</span></span>  
  
 [<span data-ttu-id="73686-123">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="73686-123">Windows Forms</span></span>](../../../../docs/framework/winforms/index.md)  
 <span data-ttu-id="73686-124">Windows Forms의 개요를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="73686-124">Provides an overview of Windows Forms.</span></span>
