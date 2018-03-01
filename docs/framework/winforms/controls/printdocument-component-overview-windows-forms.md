---
title: "PrintDocument 구성 요소 개요(Windows Forms)"
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
- PrintDocument
helpviewer_keywords:
- PrintDocument component [Windows Forms], about PrintDocument component
- printing [Windows Forms], PrintDocument component
ms.assetid: b59b4b60-dce5-42ca-8421-3a54a2f7bab0
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 414a7972550558b40403b7f4cbfd9a49194666be
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="printdocument-component-overview-windows-forms"></a><span data-ttu-id="e60f1-102">PrintDocument 구성 요소 개요(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="e60f1-102">PrintDocument Component Overview (Windows Forms)</span></span>
<span data-ttu-id="e60f1-103">Windows Forms [PrintDocument](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md) 구성 요소는 인쇄 대상 및 Windows 기반 응용 프로그램 내에서 문서를 인쇄하는 기능을 설명하는 속성을 설정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e60f1-103">The Windows Forms [PrintDocument](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md) component is used to set the properties that describe what to print and the ability to print the document within Windows-based applications.</span></span> <span data-ttu-id="e60f1-104">모든 문서 인쇄 측면의 제어에 포함되도록 [PrintDialog](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md) 구성 요소와 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e60f1-104">It can be used in conjunction with the [PrintDialog](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md) component to be in control of all aspects of document printing.</span></span>  
  
## <a name="working-with-the-printdocument-component"></a><span data-ttu-id="e60f1-105">PrintDocument 구성 요소 작업</span><span class="sxs-lookup"><span data-stu-id="e60f1-105">Working with the PrintDocument Component</span></span>  
 <span data-ttu-id="e60f1-106">두 가지와 관련 된 주요 시나리오는 <xref:System.Drawing.Printing.PrintDocument> 요소 됩니다:</span><span class="sxs-lookup"><span data-stu-id="e60f1-106">Two of the main scenarios that involve the <xref:System.Drawing.Printing.PrintDocument> component are:</span></span>  
  
-   <span data-ttu-id="e60f1-107">개별 텍스트 파일 인쇄 등의 간단한 인쇄 작업.</span><span class="sxs-lookup"><span data-stu-id="e60f1-107">Simple print jobs, such as printing an individual text file.</span></span> <span data-ttu-id="e60f1-108">이러한 경우에 추가 된 <xref:System.Drawing.Printing.PrintDocument> 을 Windows Form에 구성 요소 다음에 파일을 인쇄 하는 프로그래밍 논리를 추가 <xref:System.Drawing.Printing.PrintDocument.PrintPage> 이벤트 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="e60f1-108">In such a case you would add the <xref:System.Drawing.Printing.PrintDocument> component to a Windows Form, then add programming logic that prints a file in the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event handler.</span></span> <span data-ttu-id="e60f1-109">프로그래밍 논리 끝나야는 <xref:System.Drawing.Printing.PrintDocument.Print%2A> 메서드는 문서를 인쇄 합니다.</span><span class="sxs-lookup"><span data-stu-id="e60f1-109">The programming logic should culminate with the <xref:System.Drawing.Printing.PrintDocument.Print%2A> method to print the document.</span></span> <span data-ttu-id="e60f1-110">이 메서드는 전송는 <xref:System.Drawing.Graphics> 에 포함 된 개체는 <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> 의 속성은 <xref:System.Drawing.Printing.PrintPageEventArgs> 프린터로 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="e60f1-110">This method sends a <xref:System.Drawing.Graphics> object, contained in the <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> property of the <xref:System.Drawing.Printing.PrintPageEventArgs> class, to the printer.</span></span> <span data-ttu-id="e60f1-111">사용 하 여 텍스트 문서를 인쇄 하는 방법을 보여 주는 예제는 <xref:System.Drawing.Printing.PrintDocument> 구성 요소 참조 [하는 방법: Windows Forms에서 다중 페이지 텍스트 파일을 인쇄](../../../../docs/framework/winforms/advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e60f1-111">For an example that shows how to print a text document using the <xref:System.Drawing.Printing.PrintDocument> component, see [How to: Print a Multi-Page Text File in Windows Forms](../../../../docs/framework/winforms/advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md).</span></span>  
  
-   <span data-ttu-id="e60f1-112">작성한 인쇄 논리를 다시 사용하려는 상황과 같은 좀 더 복잡한 인쇄 작업.</span><span class="sxs-lookup"><span data-stu-id="e60f1-112">More complex print jobs, such as a situation where you will want to reuse printing logic you have written.</span></span> <span data-ttu-id="e60f1-113">이 경우 새 구성 요소에서 파생는 <xref:System.Drawing.Printing.PrintDocument> 구성 요소와 재정의 (참조 [재정의](~/docs/visual-basic/language-reference/modifiers/overrides.md) Visual basic의 경우 또는 [재정의](~/docs/csharp/language-reference/keywords/override.md) C#)는 <xref:System.Drawing.Printing.PrintDocument.PrintPage> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="e60f1-113">In such a case you would derive a new component from the <xref:System.Drawing.Printing.PrintDocument> component and override (see [Overrides](~/docs/visual-basic/language-reference/modifiers/overrides.md) for Visual Basic or [override](~/docs/csharp/language-reference/keywords/override.md) for C#) the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event.</span></span>  
  
 <span data-ttu-id="e60f1-114">폼에 추가 될 때의 <xref:System.Drawing.Printing.PrintDocument> 구성 요소는 Windows Forms 디자이너 아래쪽에서 트레이에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e60f1-114">When it is added to a form, the <xref:System.Drawing.Printing.PrintDocument> component appears in the tray at the bottom of the Windows Forms Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e60f1-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e60f1-115">See Also</span></span>  
 <xref:System.Drawing.Graphics>  
 <xref:System.Drawing.Printing.PrintDocument>  
 [<span data-ttu-id="e60f1-116">Windows Forms 인쇄 지원</span><span class="sxs-lookup"><span data-stu-id="e60f1-116">Windows Forms Print Support</span></span>](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)  
 [<span data-ttu-id="e60f1-117">PrintDocument 구성 요소</span><span class="sxs-lookup"><span data-stu-id="e60f1-117">PrintDocument Component</span></span>](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md)
