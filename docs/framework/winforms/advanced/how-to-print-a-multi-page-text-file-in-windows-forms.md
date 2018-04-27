---
title: '방법: Windows Forms에서 다중 페이지 텍스트 파일 인쇄'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- printing [Windows Forms], printing multiple pages
- text [Windows Forms], printing Windows Forms
- Windows Forms, printing text
- printing [Windows Forms], text
ms.assetid: 362427f8-03d4-4826-b49f-60ab066ad322
caps.latest.revision: 24
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: fd08d40c9b4e5f796c200966482781dfb2e700d8
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-print-a-multi-page-text-file-in-windows-forms"></a><span data-ttu-id="0e770-102">방법: Windows Forms에서 다중 페이지 텍스트 파일 인쇄</span><span class="sxs-lookup"><span data-stu-id="0e770-102">How to: Print a Multi-Page Text File in Windows Forms</span></span>
<span data-ttu-id="0e770-103">Windows 기반 응용 프로그램에서 텍스트를 인쇄하는 것은 매우 일반적입니다.</span><span class="sxs-lookup"><span data-stu-id="0e770-103">It is very common for Windows-based applications to print text.</span></span> <span data-ttu-id="0e770-104"><xref:System.Drawing.Graphics> 클래스는 화면이나 프린터와 같은 장치에 개체(그래픽 또는 텍스트)를 그리기 위한 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0e770-104">The <xref:System.Drawing.Graphics> class provides methods for drawing objects (graphics or text) to a device, such as a screen or printer.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0e770-105"><xref:System.Windows.Forms.TextRenderer>의 <xref:System.Windows.Forms.TextRenderer.DrawText%2A> 메서드는 인쇄에 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0e770-105">The <xref:System.Windows.Forms.TextRenderer.DrawText%2A> methods of <xref:System.Windows.Forms.TextRenderer> are not supported for printing.</span></span> <span data-ttu-id="0e770-106">인쇄용 텍스트를 그리려면 다음 코드 예제와 같이 항상 <xref:System.Drawing.Graphics>의 <xref:System.Drawing.Graphics.DrawString%2A> 메서드를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e770-106">You should always use the <xref:System.Drawing.Graphics.DrawString%2A> methods of <xref:System.Drawing.Graphics>, as shown in the following code example, to draw text for printing purposes.</span></span>  
  
### <a name="to-print-text"></a><span data-ttu-id="0e770-107">텍스트를 인쇄하려면</span><span class="sxs-lookup"><span data-stu-id="0e770-107">To print text</span></span>  
  
1.  <span data-ttu-id="0e770-108"><xref:System.Drawing.Printing.PrintDocument> 구성 요소와 문자열을 폼에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0e770-108">Add a <xref:System.Drawing.Printing.PrintDocument> component and a string to your form.</span></span>  
  
     [!code-csharp[System.Drawing.Printing.PrintExamples#8](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintExamples/CS/Form1.cs#8)]
     [!code-vb[System.Drawing.Printing.PrintExamples#8](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintExamples/VB/Form1.vb#8)]  
  
2.  <span data-ttu-id="0e770-109">문서를 인쇄하는 경우 <xref:System.Drawing.Printing.PrintDocument.DocumentName%2A> 속성을 인쇄할 문서로 설정하고 문서를 연 다음 이전에 추가한 문자열까지 문서 내용을 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="0e770-109">If printing a document, set the <xref:System.Drawing.Printing.PrintDocument.DocumentName%2A> property to the document you wish to print, and open and read the documents contents to the string you added previously.</span></span>  
  
     [!code-csharp[System.Drawing.Printing.PrintExamples#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintExamples/CS/Form1.cs#1)]
     [!code-vb[System.Drawing.Printing.PrintExamples#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintExamples/VB/Form1.vb#1)]  
  
3.  <span data-ttu-id="0e770-110"><xref:System.Drawing.Printing.PrintDocument.PrintPage> 이벤트 처리기에서 <xref:System.Drawing.Printing.PrintPageEventArgs> 클래스의 <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> 속성과 문서 내용을 사용하여 줄 길이와 페이지당 줄 수를 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="0e770-110">In the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event handler, use the <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> property of the <xref:System.Drawing.Printing.PrintPageEventArgs> class and the document contents to calculate line length and lines per page.</span></span> <span data-ttu-id="0e770-111">각 페이지가 그려진 후 마지막 페이지인지 확인하고 <xref:System.Drawing.Printing.PrintPageEventArgs>의 <xref:System.Drawing.Printing.PrintPageEventArgs.HasMorePages%2A> 속성을 적절하게 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0e770-111">After each page is drawn, check to see if it is the last page, and set the <xref:System.Drawing.Printing.PrintPageEventArgs.HasMorePages%2A> property of the <xref:System.Drawing.Printing.PrintPageEventArgs> accordingly.</span></span> <span data-ttu-id="0e770-112"><xref:System.Drawing.Printing.PrintPageEventArgs.HasMorePages%2A>가 `false`가 될 때까지 <xref:System.Drawing.Printing.PrintDocument.PrintPage> 이벤트가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="0e770-112">The <xref:System.Drawing.Printing.PrintDocument.PrintPage> event is raised until <xref:System.Drawing.Printing.PrintPageEventArgs.HasMorePages%2A> is `false`.</span></span> <span data-ttu-id="0e770-113">또한 <xref:System.Drawing.Printing.PrintDocument.PrintPage> 이벤트가 해당 이벤트 처리 메서드에 연결되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0e770-113">Also, make sure the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event is associated with its event-handling method.</span></span>  
  
     <span data-ttu-id="0e770-114">다음 코드 예제에서 이벤트 처리기는 "testPage.txt" 파일의 내용을 폼에 사용된 것과 동일한 글꼴로 인쇄하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e770-114">In the following code example, the event handler is used to print the contents of the "testPage.txt" file in the same font as is used on the form.</span></span>  
  
     [!code-csharp[System.Drawing.Printing.PrintExamples#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintExamples/CS/Form1.cs#2)]
     [!code-vb[System.Drawing.Printing.PrintExamples#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintExamples/VB/Form1.vb#2)]  
  
4.  <span data-ttu-id="0e770-115"><xref:System.Drawing.Printing.PrintDocument.Print%2A> 메서드를 호출하여 <xref:System.Drawing.Printing.PrintDocument.PrintPage> 이벤트를 발생시킵니다.</span><span class="sxs-lookup"><span data-stu-id="0e770-115">Call the <xref:System.Drawing.Printing.PrintDocument.Print%2A> method to raise the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event.</span></span>  
  
     [!code-csharp[System.Drawing.Printing.PrintExamples#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintExamples/CS/Form1.cs#5)]
     [!code-vb[System.Drawing.Printing.PrintExamples#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintExamples/VB/Form1.vb#5)]  
  
## <a name="example"></a><span data-ttu-id="0e770-116">예제</span><span class="sxs-lookup"><span data-stu-id="0e770-116">Example</span></span>  
 [!code-csharp[System.Drawing.Printing.PrintExamples#0](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintExamples/CS/Form1.cs#0)]
 [!code-vb[System.Drawing.Printing.PrintExamples#0](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintExamples/VB/Form1.vb#0)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="0e770-117">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="0e770-117">Compiling the Code</span></span>  
 <span data-ttu-id="0e770-118">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="0e770-118">This example requires:</span></span>  
  
-   <span data-ttu-id="0e770-119">C:\\ 드라이브의 루트에 있는, 인쇄할 텍스트를 포함하는 testPage.txt라는 텍스트 파일</span><span class="sxs-lookup"><span data-stu-id="0e770-119">A text file named testPage.txt containing the text to print, located in the root of drive C:\\.</span></span> <span data-ttu-id="0e770-120">다른 파일을 인쇄하려면 코드를 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="0e770-120">Edit the code to print a different file.</span></span>  
  
-   <span data-ttu-id="0e770-121">System, System.Windows.Forms, System.Drawing 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="0e770-121">References to the System, System.Windows.Forms, System.Drawing assemblies.</span></span>  
  
-   <span data-ttu-id="0e770-122">Visual Basic 또는 Visual C#에 대 한 명령줄에서이 예제를 빌드하는 방법에 대 한 정보를 참조 하십시오. [명령줄에서 빌드](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) 또는 [사용한 명령줄 빌드 csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0e770-122">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="0e770-123">[!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] 에서 코드를 새 프로젝트에 붙여넣어 이 예제를 빌드할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e770-123">You can also build this example in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] by pasting the code into a new project.</span></span>  <span data-ttu-id="0e770-124">[방법: Visual Studio를 사용하여 전체 Windows Forms 코드 예제 컴파일 및 실행](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\))을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0e770-124">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e770-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0e770-125">See Also</span></span>  
 <xref:System.Drawing.Graphics>  
 <xref:System.Drawing.Brush>  
 [<span data-ttu-id="0e770-126">Windows Forms 인쇄 지원</span><span class="sxs-lookup"><span data-stu-id="0e770-126">Windows Forms Print Support</span></span>](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)
