---
title: '방법: Windows Forms DataGridView 컨트롤에서 내용에 맞게 프로그래밍 방식으로 셀 크기 조정'
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
- cpp
helpviewer_keywords:
- data grids [Windows Forms], resizing cells to fit content
- cells [Windows Forms], resizing to fit contents
- DataGridView control [Windows Forms], resizing cells
- grids [Windows Forms], resizing cells to fit content
ms.assetid: 63d770dc-b3f5-462b-901a-3125b2753792
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e392e46b257fa7ef9b6bde3b5d6bb7274aaa01e6
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2018
---
# <a name="how-to-programmatically-resize-cells-to-fit-content-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="8f8d5-102">방법: Windows Forms DataGridView 컨트롤에서 내용에 맞게 프로그래밍 방식으로 셀 크기 조정</span><span class="sxs-lookup"><span data-stu-id="8f8d5-102">How to: Programmatically Resize Cells to Fit Content in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="8f8d5-103"><xref:System.Windows.Forms.DataGridView> 컨트롤 메서드를 사용하여 전체 값이 잘리지 않고 표시되도록 행, 열 및 머리글의 크기를 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f8d5-103">You can use the <xref:System.Windows.Forms.DataGridView> control methods to resize rows, columns, and headers so that they display their entire values without truncation.</span></span> <span data-ttu-id="8f8d5-104">언제든지 이러한 메서드를 통해 <xref:System.Windows.Forms.DataGridView> 요소의 크기를 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f8d5-104">You can use these methods to resize <xref:System.Windows.Forms.DataGridView> elements at times of your choosing.</span></span> <span data-ttu-id="8f8d5-105">또는 콘텐츠가 변경될 때마다 이러한 요소의 크기를 자동으로 조정하도록 컨트롤을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f8d5-105">Alternately, you can configure the control to resize these elements automatically whenever content changes.</span></span> <span data-ttu-id="8f8d5-106">그러나 이 기능은 큰 데이터 집합을 사용하거나 데이터가 자주 변경되는 경우 비효율적일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f8d5-106">This can be inefficient, however, when you are working with large data sets or when your data changes frequently.</span></span> <span data-ttu-id="8f8d5-107">자세한 내용은 참조 [Windows Forms DataGridView 컨트롤의 크기 조정 옵션](../../../../docs/framework/winforms/controls/sizing-options-in-the-windows-forms-datagridview-control.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8d5-107">For more information, see [Sizing Options in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/sizing-options-in-the-windows-forms-datagridview-control.md).</span></span>  
  
 <span data-ttu-id="8f8d5-108">일반적으로 <xref:System.Windows.Forms.DataGridView> 요소는 데이터 소스에서 새 데이터를 로드하는 경우 또는 사용자가 값을 편집한 경우에만 해당 콘텐츠에 맞게 프로그래밍 방식으로 조정합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8d5-108">Typically, you will programmatically adjust <xref:System.Windows.Forms.DataGridView> elements to fit their content only when you load new data from a data source or when the user has edited a value.</span></span> <span data-ttu-id="8f8d5-109">이 기능은 성능 최적화에 유용하지만, 사용자가 마우스를 사용하여 수동으로 행과 열의 크기를 조정할 수 있게 하려는 경우에도 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8d5-109">This is useful to optimize performance, but it is also useful when you want to enable your users to manually resize rows and columns with the mouse.</span></span>  
  
 <span data-ttu-id="8f8d5-110">다음 코드 예제에서는 프로그래밍 방식의 크기 조정에 사용할 수 있는 옵션을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8f8d5-110">The following code example demonstrates the options available to you for programmatic resizing.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8f8d5-111">예제</span><span class="sxs-lookup"><span data-stu-id="8f8d5-111">Example</span></span>  
 [!code-cpp[System.Windows.Forms.DataGridView.ProgrammaticResizing#0](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.ProgrammaticResizing/CPP/programmaticsizing.cpp#0)]
 [!code-csharp[System.Windows.Forms.DataGridView.ProgrammaticResizing#0](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.ProgrammaticResizing/CS/programmaticsizing.cs#0)]
 [!code-vb[System.Windows.Forms.DataGridView.ProgrammaticResizing#0](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.ProgrammaticResizing/VB/programmaticsizing.vb#0)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="8f8d5-112">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="8f8d5-112">Compiling the Code</span></span>  
 <span data-ttu-id="8f8d5-113">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8d5-113">This example requires:</span></span>  
  
-   <span data-ttu-id="8f8d5-114">System, System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="8f8d5-114">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="8f8d5-115">Visual Basic 또는 Visual C#에 대 한 명령줄에서이 예제를 빌드하는 방법에 대 한 정보를 참조 하십시오. [명령줄에서 빌드](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) 또는 [사용한 명령줄 빌드 csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8d5-115">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="8f8d5-116">새 프로젝트에 코드를 붙여 넣어 Visual Studio에서이 예제를 빌드할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f8d5-116">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="8f8d5-117">[방법: Visual Studio를 사용하여 전체 Windows Forms 코드 예제 컴파일 및 실행](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\))을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8f8d5-117">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f8d5-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8f8d5-118">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.AutoResizeColumn%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.AutoResizeColumnHeadersHeight%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.AutoResizeRow%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.AutoResizeRows%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.AutoResizeRowHeadersWidth%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewAutoSizeRowMode>  
 <xref:System.Windows.Forms.DataGridViewAutoSizeRowsMode>  
 <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode>  
 <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode>  
 <xref:System.Windows.Forms.DataGridViewColumnHeadersHeightSizeMode>  
 <xref:System.Windows.Forms.DataGridViewRowHeadersWidthSizeMode>  
 [<span data-ttu-id="8f8d5-119">Windows Forms DataGridView 컨트롤의 열 및 행 크기 조정</span><span class="sxs-lookup"><span data-stu-id="8f8d5-119">Resizing Columns and Rows in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/resizing-columns-and-rows-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="8f8d5-120">Windows Forms DataGridView 컨트롤의 크기 조정 옵션</span><span class="sxs-lookup"><span data-stu-id="8f8d5-120">Sizing Options in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/sizing-options-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="8f8d5-121">방법: Windows Forms DataGridView 컨트롤에서 내용이 변경되는 경우 자동으로 셀 크기 조정</span><span class="sxs-lookup"><span data-stu-id="8f8d5-121">How to: Automatically Resize Cells When Content Changes in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/automatically-resize-cells-when-content-changes-in-the-datagrid.md)
