---
title: "방법: Windows Forms DataGridView 컨트롤에서 사용자가 여러 셀을 클립보드에 복사할 수 있도록 설정"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cells [Windows Forms], copying to Clipboard
- DataGridView control [Windows Forms], copying multiple cells
- data grids [Windows Forms], copying multiple cells
- Clipboard [Windows Forms], copying multiple cells
ms.assetid: fd0403b2-d0e3-4ae0-839c-0f737e1eb4a9
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b312dca036b327ee86527607db8b73d4545500d0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-enable-users-to-copy-multiple-cells-to-the-clipboard-from-the-windows-forms-datagridview-control"></a><span data-ttu-id="0ef15-102">방법: Windows Forms DataGridView 컨트롤에서 사용자가 여러 셀을 클립보드에 복사할 수 있도록 설정</span><span class="sxs-lookup"><span data-stu-id="0ef15-102">How to: Enable Users to Copy Multiple Cells to the Clipboard from the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="0ef15-103">셀 복사를 사용하면 <xref:System.Windows.Forms.DataGridView> 컨트롤의 데이터가 <xref:System.Windows.Forms.Clipboard>를 통해 다른 응용 프로그램에 쉽게 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ef15-103">When you enable cell copying, you make the data in your <xref:System.Windows.Forms.DataGridView> control easily accessible to other applications through the <xref:System.Windows.Forms.Clipboard>.</span></span> <span data-ttu-id="0ef15-104">선택된 셀의 값은 문자열로 변환되고 메모장 및 Excel 같은 응용 프로그램에 붙여넣도록 탭으로 구분된 텍스트 값으로 클립보드에 추가되거나 Word 같은 응용 프로그램에 붙여넣도록 HTML 형식 테이블로 클립보드에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ef15-104">The values of the selected cells are converted to strings and added to the Clipboard as tab-delimited text values for pasting into applications like Notepad and Excel, and as an HTML-formatted table for pasting into applications like Word.</span></span>  
  
 <span data-ttu-id="0ef15-105">셀 값만 복사하거나 클립보드 데이터에 행 및 열 머리글 텍스트를 포함하거나 사용자가 전체 행이나 열을 선택할 때만 머리글을 포함하도록 셀 복사를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ef15-105">You can configure cell copying to copy cell values only, to include row and column header text in the Clipboard data, or to include header text only when users select entire rows or columns.</span></span>  
  
 <span data-ttu-id="0ef15-106">선택 모드에 따라 사용자는 연결이 끊어진 셀 그룹 여러 개를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ef15-106">Depending on the selection mode, users can select multiple disconnected groups of cells.</span></span> <span data-ttu-id="0ef15-107">사용자가 셀을 클립보드에 복사할 때 셀이 선택되지 않은 행과 열은 복사되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0ef15-107">When a user copies cells to the Clipboard, rows and columns with no selected cells are not copied.</span></span> <span data-ttu-id="0ef15-108">모든 다른 행 또는 열은 클립보드에 복사된 데이터 테이블의 행과 열이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ef15-108">All other rows or columns become rows and columns in the table of data copied to the Clipboard.</span></span> <span data-ttu-id="0ef15-109">이들 행이나 열에서 선택되지 않은 셀은 빈 자리 표시자로 클립보드에 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ef15-109">Unselected cells in these rows or columns are copied as blank placeholders to the Clipboard.</span></span>  
  
### <a name="to-enable-cell-copying"></a><span data-ttu-id="0ef15-110">셀 복사를 사용하도록 설정하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="0ef15-110">To enable cell copying</span></span>  
  
-   <span data-ttu-id="0ef15-111"><xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A?displayProperty=nameWithType> 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0ef15-111">Set the <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A?displayProperty=nameWithType> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewClipboardDemo#15](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewClipboardDemo/CS/datagridviewclipboarddemo.cs#15)]
     [!code-vb[System.Windows.Forms.DataGridViewClipboardDemo#15](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewClipboardDemo/VB/datagridviewclipboarddemo.vb#15)]  
  
## <a name="example"></a><span data-ttu-id="0ef15-112">예</span><span class="sxs-lookup"><span data-stu-id="0ef15-112">Example</span></span>  
 <span data-ttu-id="0ef15-113">다음 전체 코드 예제에서는 셀을 클립보드에 복사하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0ef15-113">The following complete code example demonstrates how cells are copied to the Clipboard.</span></span> <span data-ttu-id="0ef15-114">이 예제는 <xref:System.Windows.Forms.DataGridView.GetClipboardContent%2A?displayProperty=nameWithType> 메서드를 사용하여 선택된 셀을 클립보드에 복사하는 단추를 포함하고 클립보드 내용을 텍스트 상자에 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="0ef15-114">This example includes a button that copies the selected cells to the Clipboard using the <xref:System.Windows.Forms.DataGridView.GetClipboardContent%2A?displayProperty=nameWithType> method and displays the Clipboard contents in a text box.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataGridViewClipboardDemo#00](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewClipboardDemo/CS/datagridviewclipboarddemo.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewClipboardDemo#00](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewClipboardDemo/VB/datagridviewclipboarddemo.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="0ef15-115">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="0ef15-115">Compiling the Code</span></span>  
 <span data-ttu-id="0ef15-116">이 코드에는 다음이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="0ef15-116">This code requires:</span></span>  
  
-   <span data-ttu-id="0ef15-117">N:System 및 N:System.Windows.Forms 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="0ef15-117">References to the N:System and N:System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="0ef15-118">[!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] 또는 [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)]의 명령줄에서 이 예제를 빌드하는 방법에 대한 자세한 내용은 [명령줄에서 빌드](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) 또는 [csc.exe를 사용한 명령줄 빌드](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0ef15-118">For information about building this example from the command line for [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] or [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="0ef15-119">[!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]에서 코드를 새 프로젝트에 붙여넣어 이 예제를 빌드할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ef15-119">You can also build this example in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] by pasting the code into a new project.</span></span>  <span data-ttu-id="0ef15-120">[방법: Visual Studio를 사용하여 전체 Windows Forms 코드 예제 컴파일 및 실행](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\))을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0ef15-120">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ef15-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0ef15-121">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A>  
 <xref:System.Windows.Forms.DataGridView.GetClipboardContent%2A>  
 [<span data-ttu-id="0ef15-122">Windows Forms DataGridView 컨트롤에서 선택 및 클립보드 사용</span><span class="sxs-lookup"><span data-stu-id="0ef15-122">Selection and Clipboard Use with the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/selection-and-clipboard-use-with-the-windows-forms-datagridview-control.md)
