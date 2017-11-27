---
title: "Windows Forms 인쇄 지원"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms, printing
- printing [Windows Forms]
- forms [Windows Forms], printing (using designer)
- printing [Windows Forms], Windows Forms, support
- printing [Windows Forms], print support
ms.assetid: a4a2960c-eb70-48e2-b641-cfb222704e46
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 029d5ed424061807cf04446cbb10424ae20afba2
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="windows-forms-print-support"></a><span data-ttu-id="77706-102">Windows Forms 인쇄 지원</span><span class="sxs-lookup"><span data-stu-id="77706-102">Windows Forms Print Support</span></span>
<span data-ttu-id="77706-103">Windows Forms의 인쇄 이루어져 주로 사용 하는 [PrintDocument 구성 요소](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md) 인쇄할 수 있도록 구성 요소 및 [PrintPreviewDialog 컨트롤](../../../../docs/framework/winforms/controls/printpreviewdialog-control-windows-forms.md) 컨트롤 [PrintDialog 구성 요소](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md) 및 [PageSetupDialog 구성 요소](../../../../docs/framework/winforms/controls/pagesetupdialog-component-windows-forms.md) 구성 요소를 Windows 운영 체제에 익숙한 사용자에 게 친숙 한 그래픽 인터페이스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="77706-103">Printing in Windows Forms consists primarily of using the [PrintDocument Component](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md) component to enable the user to print, and the [PrintPreviewDialog Control](../../../../docs/framework/winforms/controls/printpreviewdialog-control-windows-forms.md) control, [PrintDialog Component](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md) and [PageSetupDialog Component](../../../../docs/framework/winforms/controls/pagesetupdialog-component-windows-forms.md) components to provide a familiar graphical interface to users accustomed to the Windows operating system.</span></span>  
  
 <span data-ttu-id="77706-104">새 인스턴스를 만들고 일반적으로 <xref:System.Drawing.Printing.PrintDocument> 구성 요소를 사용 하 여 인쇄 대상을 설명 하는 속성을 설정는 <xref:System.Drawing.Printing.PrinterSettings> 및 <xref:System.Drawing.Printing.PageSettings> 클래스 및 호출은 <xref:System.Drawing.Printing.PrintDocument.Print%2A> 메서드를 실제로 문서를 인쇄 합니다.</span><span class="sxs-lookup"><span data-stu-id="77706-104">Typically, you create a new instance of the <xref:System.Drawing.Printing.PrintDocument> component, set the properties that describe what to print using the <xref:System.Drawing.Printing.PrinterSettings> and <xref:System.Drawing.Printing.PageSettings> classes, and call the <xref:System.Drawing.Printing.PrintDocument.Print%2A> method to actually print the document.</span></span>  
  
 <span data-ttu-id="77706-105">Windows 기반 응용 프로그램에서 인쇄 하는 동안는 <xref:System.Drawing.Printing.PrintDocument> 구성 요소 사용자에 게 인쇄 발생 하는 팩트 하 고 인쇄 작업을 취소할 수 있는 중단 인쇄 대화 상자 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="77706-105">During the course of printing from a Windows-based application, the <xref:System.Drawing.Printing.PrintDocument> component will show an abort print dialog box to alert users to the fact that printing is occurring and to allow the print job to be canceled.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="77706-106">단원 내용</span><span class="sxs-lookup"><span data-stu-id="77706-106">In This Section</span></span>  
 [<span data-ttu-id="77706-107">방법: 표준 Windows Forms 인쇄 작업 만들기</span><span class="sxs-lookup"><span data-stu-id="77706-107">How to: Create Standard Windows Forms Print Jobs</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-standard-windows-forms-print-jobs.md)  
 <span data-ttu-id="77706-108">사용 하는 방법에 설명 된 <xref:System.Drawing.Printing.PrintDocument> Windows Form에서 인쇄 하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="77706-108">Explains how to use the <xref:System.Drawing.Printing.PrintDocument> component to print from a Windows Form.</span></span>  
  
 [<span data-ttu-id="77706-109">방법: 런타임에 PrintDialog에서 사용자 입력 캡처</span><span class="sxs-lookup"><span data-stu-id="77706-109">How to: Capture User Input from a PrintDialog at Run Time</span></span>](../../../../docs/framework/winforms/advanced/how-to-capture-user-input-from-a-printdialog-at-run-time.md)  
 <span data-ttu-id="77706-110">프로그래밍 방식으로 사용 하 여 선택한 인쇄 옵션을 수정 하는 방법에 설명 된 <xref:System.Windows.Forms.PrintDialog> 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="77706-110">Explains how to modify selected print options programmatically using the <xref:System.Windows.Forms.PrintDialog> component.</span></span>  
  
 [<span data-ttu-id="77706-111">방법: Windows Forms에서 사용자의 컴퓨터에 연결된 프린터 선택</span><span class="sxs-lookup"><span data-stu-id="77706-111">How to: Choose the Printers Attached to a User's Computer in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-choose-the-printers-attached-to-user-computer-in-windows-forms.md)  
 <span data-ttu-id="77706-112">프린터를 사용 하 여 인쇄할 변경에 대해 설명 된 <xref:System.Windows.Forms.PrintDialog> 런타임 시 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="77706-112">Describes changing the printer to print to using the <xref:System.Windows.Forms.PrintDialog> component at run time.</span></span>  
  
 [<span data-ttu-id="77706-113">방법: Windows Forms의 그래픽 인쇄</span><span class="sxs-lookup"><span data-stu-id="77706-113">How to: Print Graphics in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-print-graphics-in-windows-forms.md)  
 <span data-ttu-id="77706-114">프린터로 보내는 그래픽을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="77706-114">Describes sending graphics to the printer.</span></span>  
  
 [<span data-ttu-id="77706-115">방법: Windows Forms에서 다중 페이지 텍스트 파일 인쇄</span><span class="sxs-lookup"><span data-stu-id="77706-115">How to: Print a Multi-Page Text File in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md)  
 <span data-ttu-id="77706-116">프린터로 보내는 텍스트를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="77706-116">Describes sending text to the printer.</span></span>  
  
 [<span data-ttu-id="77706-117">방법: Windows Forms 인쇄 작업 완료</span><span class="sxs-lookup"><span data-stu-id="77706-117">How to: Complete Windows Forms Print Jobs</span></span>](../../../../docs/framework/winforms/advanced/how-to-complete-windows-forms-print-jobs.md)  
 <span data-ttu-id="77706-118">인쇄 작업을 완료 하는 사용자가 경고 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="77706-118">Explains how to alert users to the completion of a print job.</span></span>  
  
 [<span data-ttu-id="77706-119">방법: Windows Form 인쇄</span><span class="sxs-lookup"><span data-stu-id="77706-119">How to: Print a Windows Form</span></span>](../../../../docs/framework/winforms/advanced/how-to-print-a-windows-form.md)  
 <span data-ttu-id="77706-120">현재 폼의 복사본을 인쇄 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="77706-120">Shows how to print a copy of the current form.</span></span>  
  
 [<span data-ttu-id="77706-121">방법: Windows Forms에서 인쇄 미리 보기를 사용하여 인쇄</span><span class="sxs-lookup"><span data-stu-id="77706-121">How to: Print in Windows Forms Using Print Preview</span></span>](../../../../docs/framework/winforms/advanced/how-to-print-in-windows-forms-using-print-preview.md)  
 <span data-ttu-id="77706-122">사용 하는 방법을 보여 줍니다.는 <xref:System.Windows.Forms.PrintPreviewDialog> 문서 인쇄를 위한 합니다.</span><span class="sxs-lookup"><span data-stu-id="77706-122">Shows how to use a <xref:System.Windows.Forms.PrintPreviewDialog> for printing a document.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="77706-123">관련 단원</span><span class="sxs-lookup"><span data-stu-id="77706-123">Related Sections</span></span>  
 [<span data-ttu-id="77706-124">PrintDocument 구성 요소</span><span class="sxs-lookup"><span data-stu-id="77706-124">PrintDocument Component</span></span>](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md)  
 <span data-ttu-id="77706-125">사용법을 설명는 <xref:System.Drawing.Printing.PrintDocument> 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="77706-125">Explains usage of the <xref:System.Drawing.Printing.PrintDocument> component.</span></span>  
  
 [<span data-ttu-id="77706-126">PrintDialog 구성 요소</span><span class="sxs-lookup"><span data-stu-id="77706-126">PrintDialog Component</span></span>](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md)  
 <span data-ttu-id="77706-127">사용법을 설명는 <xref:System.Windows.Forms.PrintDialog> 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="77706-127">Explains usage of the <xref:System.Windows.Forms.PrintDialog> component.</span></span>  
  
 [<span data-ttu-id="77706-128">PrintPreviewDialog 컨트롤</span><span class="sxs-lookup"><span data-stu-id="77706-128">PrintPreviewDialog Control</span></span>](../../../../docs/framework/winforms/controls/printpreviewdialog-control-windows-forms.md)  
 <span data-ttu-id="77706-129">사용법을 설명는 <xref:System.Windows.Forms.PrintPreviewDialog> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="77706-129">Explains usage of the <xref:System.Windows.Forms.PrintPreviewDialog> control.</span></span>  
  
 [<span data-ttu-id="77706-130">PageSetupDialog 구성 요소</span><span class="sxs-lookup"><span data-stu-id="77706-130">PageSetupDialog Component</span></span>](../../../../docs/framework/winforms/controls/pagesetupdialog-component-windows-forms.md)  
 <span data-ttu-id="77706-131">사용법을 설명는 <xref:System.Windows.Forms.PageSetupDialog> 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="77706-131">Explains usage of the <xref:System.Windows.Forms.PageSetupDialog> component.</span></span>  
  
 <xref:System.Drawing.Printing>  
 <span data-ttu-id="77706-132">클래스를 설명의 <xref:System.Drawing.Printing> 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="77706-132">Describes the classes in the <xref:System.Drawing.Printing> namespace.</span></span>
