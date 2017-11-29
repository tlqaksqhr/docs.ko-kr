---
title: "방법: PrintDialog 구성 요소 표시"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Print dialog box [Windows Forms], displaying
- PrintDialog component [Windows Forms], displaying
- printing [Windows Forms], displaying print dialog box
ms.assetid: 745a8db7-0526-4b21-b09d-18e13ed32014
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7e1162a4e926d5be35f8f7bb7cdeb92264f293aa
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-display-the-printdialog-component"></a><span data-ttu-id="d2298-102">방법: PrintDialog 구성 요소 표시</span><span class="sxs-lookup"><span data-stu-id="d2298-102">How to: Display the PrintDialog Component</span></span>
<span data-ttu-id="d2298-103"><xref:System.Windows.Forms.PrintDialog> 구성 요소는 표준 Windows 인쇄 대화 상자 많은 사용자 익숙할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d2298-103">The <xref:System.Windows.Forms.PrintDialog> component is the standard Windows print dialog box that many of your users will be familiar with.</span></span> <span data-ttu-id="d2298-104">사용자가 즉시 만족 하기 때문에 있다면 좋을 것 사용할 수는 <xref:System.Windows.Forms.PrintDialog> 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="d2298-104">Because your users will be immediately comfortable with it, it would be beneficial for you to use the <xref:System.Windows.Forms.PrintDialog> component.</span></span>  
  
### <a name="to-display-the-printdialog-component"></a><span data-ttu-id="d2298-105">PrintDialog 구성 요소를 표시하려면</span><span class="sxs-lookup"><span data-stu-id="d2298-105">To display the PrintDialog component</span></span>  
  
-   <span data-ttu-id="d2298-106">호출 된 <xref:System.Windows.Forms.Form.ShowDialog%2A> 응용 프로그램의 코드에서 메서드를 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2298-106">Call the <xref:System.Windows.Forms.Form.ShowDialog%2A> method from within the code of your application.</span></span>  
  
     <span data-ttu-id="d2298-107">구성 요소가 표시되면 사용자가 이 구성 요소와 상호 작용하여 인쇄 작업의 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d2298-107">Once the component is shown, users will interact with it, setting the properties of the print job.</span></span> <span data-ttu-id="d2298-108">이러한 파일에 저장 되는 <!--zz <xref:System.Drawing.Printing.PrinterSetting>--> `PrinterSetting` 클래스 (및 <xref:System.Drawing.Printing.PageSettings> 클래스를 사용자가 액세스 하는 경우는 [PageSetupDialog 구성 요소](../../../../docs/framework/winforms/controls/pagesetupdialog-component-windows-forms.md) 통해는 <xref:System.Windows.Forms.PrintDialog> 구성 요소) 인쇄 작업에 연결 된 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2298-108">These are saved in the <!--zz <xref:System.Drawing.Printing.PrinterSetting>--> `PrinterSetting` class (and the <xref:System.Drawing.Printing.PageSettings> class, if the user accesses the [PageSetupDialog Component](../../../../docs/framework/winforms/controls/pagesetupdialog-component-windows-forms.md) through the <xref:System.Windows.Forms.PrintDialog> component) associated with that print job.</span></span> <span data-ttu-id="d2298-109">그런 다음 설정한 속성을 호출하여 인쇄 작업의 세부 사항을 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2298-109">You can then make calls to the properties they set to determine the specifics of the print job.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2298-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d2298-110">See Also</span></span>  
 [<span data-ttu-id="d2298-111">방법: 표준 Windows Forms 인쇄 작업 만들기</span><span class="sxs-lookup"><span data-stu-id="d2298-111">How to: Create Standard Windows Forms Print Jobs</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-standard-windows-forms-print-jobs.md)  
 [<span data-ttu-id="d2298-112">방법: 런타임에 PrintDialog에서 사용자 입력 캡처</span><span class="sxs-lookup"><span data-stu-id="d2298-112">How to: Capture User Input from a PrintDialog at Run Time</span></span>](../../../../docs/framework/winforms/advanced/how-to-capture-user-input-from-a-printdialog-at-run-time.md)  
 [<span data-ttu-id="d2298-113">PrintPreviewDialog 컨트롤</span><span class="sxs-lookup"><span data-stu-id="d2298-113">PrintPreviewDialog Control</span></span>](../../../../docs/framework/winforms/controls/printpreviewdialog-control-windows-forms.md)  
 [<span data-ttu-id="d2298-114">PrintDialog 구성 요소</span><span class="sxs-lookup"><span data-stu-id="d2298-114">PrintDialog Component</span></span>](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md)  
 [<span data-ttu-id="d2298-115">Windows Forms 인쇄 지원</span><span class="sxs-lookup"><span data-stu-id="d2298-115">Windows Forms Print Support</span></span>](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)  
 [<span data-ttu-id="d2298-116">Windows Forms 컨트롤</span><span class="sxs-lookup"><span data-stu-id="d2298-116">Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/index.md)
