---
title: "PageSetupDialog 구성 요소(Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- printing [Windows Forms], page setup
- margins [Windows Forms], page setup options
- paper orientation
- print options [Windows Forms], PageSetupDialog component
- page properties
- printing [Windows Forms], displaying setup dialog boxes
- portrait orientation
- headers [Windows Forms], printing
- footers [Windows Forms], page setup options
- landscape orientation
- page footer
- page setup
- Page Setup dialog box
- PageSetupDialog component
- page header
- printing [Windows Forms], headers and footers
ms.assetid: 1c7ccb02-ac62-4fc8-8e4f-c67b01a86802
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1eb071b4bf3248deaa171ad473d1867d2edb46ab
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="pagesetupdialog-component-windows-forms"></a><span data-ttu-id="2910a-102">PageSetupDialog 구성 요소(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="2910a-102">PageSetupDialog Component (Windows Forms)</span></span>
<span data-ttu-id="2910a-103">Windows Forms <xref:System.Windows.Forms.PageSetupDialog> 구성 요소는 Windows 기반 응용 프로그램에서 인쇄를 위한 페이지 세부 정보를 설정 하는 데 사용 하는 미리 구성 된 대화 상자.</span><span class="sxs-lookup"><span data-stu-id="2910a-103">The Windows Forms <xref:System.Windows.Forms.PageSetupDialog> component is a pre-configured dialog box used to set page details for printing in Windows-based applications.</span></span> <span data-ttu-id="2910a-104">고유한 대화 상자를 구성 하는 대신 페이지 기본 설정을 지정 하려면 Windows 기반 응용 프로그램 간단한 솔루션으로 사용자에 대 한 내에서 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2910a-104">Use it within your Windows-based application as a simple solution for users to set page preferences in lieu of configuring your own dialog box.</span></span> <span data-ttu-id="2910a-105">테두리 및 여백, 머리글 및 바닥글 및 세로 또는 가로 방향 설정 하려면 사용자가 활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2910a-105">You can enable users to set border and margin adjustments, headers and footers, and portrait vs. landscape orientation.</span></span> <span data-ttu-id="2910a-106">표준 Windows 대화 상자를 사용하여 기본 기능이 사용자에게 익숙한 응용 프로그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2910a-106">By relying on standard Windows dialog boxes, you create applications whose basic functionality is immediately familiar to users.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2910a-107">단원 내용</span><span class="sxs-lookup"><span data-stu-id="2910a-107">In This Section</span></span>  
 [<span data-ttu-id="2910a-108">PageSetupDialog 구성 요소 개요</span><span class="sxs-lookup"><span data-stu-id="2910a-108">PageSetupDialog Component Overview</span></span>](../../../../docs/framework/winforms/controls/pagesetupdialog-component-overview-windows-forms.md)  
 <span data-ttu-id="2910a-109">일반적인 개념을 소개는 <xref:System.Windows.Forms.PageSetupDialog> 구성 요소는 사용자가 페이지 설정을 조작 하는 데 사용할 수 있는 미리 구성 된 대화 상자를 표시 하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2910a-109">Introduces the general concepts of the <xref:System.Windows.Forms.PageSetupDialog> component, which you can use to display a pre-configured dialog box that users can use to manipulate page settings.</span></span>  
  
 [<span data-ttu-id="2910a-110">방법: PageSetupDialog 구성 요소를 사용하여 페이지 속성 설정</span><span class="sxs-lookup"><span data-stu-id="2910a-110">How to: Determine Page Properties Using the PageSetupDialog Component</span></span>](../../../../docs/framework/winforms/controls/how-to-determine-page-properties-using-the-pagesetupdialog-component.md)  
 <span data-ttu-id="2910a-111">인스턴스를 사용 하 여 페이지 속성을 설정 하는 방법에 설명 된 <xref:System.Windows.Forms.PageSetupDialog> 런타임 시 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="2910a-111">Explains how to set page properties by using an instance of the <xref:System.Windows.Forms.PageSetupDialog> component at run time.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="2910a-112">참조</span><span class="sxs-lookup"><span data-stu-id="2910a-112">Reference</span></span>  
 <xref:System.Windows.Forms.PageSetupDialog>  
 <span data-ttu-id="2910a-113">클래스 및 해당 멤버에 대한 참조 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2910a-113">Provides reference information on the class and its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="2910a-114">관련 단원</span><span class="sxs-lookup"><span data-stu-id="2910a-114">Related Sections</span></span>  
 [<span data-ttu-id="2910a-115">Windows Forms에 사용할 수 있는 컨트롤</span><span class="sxs-lookup"><span data-stu-id="2910a-115">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 <span data-ttu-id="2910a-116">사용 방법에 대한 정보 링크를 포함하는 Windows Forms 컨트롤의 전체 목록을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2910a-116">Provides a complete list of Windows Forms controls, with links to information on their use.</span></span>  
  
 [<span data-ttu-id="2910a-117">대화 상자 컨트롤 및 구성 요소</span><span class="sxs-lookup"><span data-stu-id="2910a-117">Dialog-Box Controls and Components</span></span>](../../../../docs/framework/winforms/controls/dialog-box-controls-and-components-windows-forms.md)  
 <span data-ttu-id="2910a-118">사용자가 응용 프로그램이나 시스템에서 표준 조작을 수행할 수 있도록 하는 컨트롤 및 구성 요소 집합에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2910a-118">Describes a set of controls and components that allow users to perform standard interactions with the application or system.</span></span>  
  
 [<span data-ttu-id="2910a-119">Windows Forms 대화 상자의 필수 코드</span><span class="sxs-lookup"><span data-stu-id="2910a-119">Essential Code for Windows Forms Dialog Boxes</span></span>](http://go.microsoft.com/fwlink/?LinkID=102575)  
 <span data-ttu-id="2910a-120">Windows Forms 대화 상자 컨트롤 및 구성 요소와 기본 함수를 실행하는 데 필요한 코드에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2910a-120">Discusses the Windows Forms dialog box controls and components and the code necessary for executing their basic functions.</span></span> <span data-ttu-id="2910a-121">(MSDN Online Library 기술 문서)</span><span class="sxs-lookup"><span data-stu-id="2910a-121">(MSDN Online Library technical article)</span></span>
