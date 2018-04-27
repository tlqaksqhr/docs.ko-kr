---
title: '방법: Windows Forms DataGridView 컨트롤에서 데이터 형식 사용자 지정'
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
- DataGridView control [Windows Forms], formatting data
- DataGridView control [Windows Forms], cell styles
- cells [Windows Forms], changing colors in DataGridView control [Windows Forms]
- colors [Windows Forms], changing in DataGridView control [Windows Forms]
- data [Windows Forms], formatting in DataGridView control
- DataGridView control [Windows Forms], cell customization
- DataGridView control [Windows Forms], changing cell colors
- Windows Forms, changing colors of DataGridView cells
- DataGridView control [Windows Forms], substituting cell values for display
- data grids [Windows Forms], formatting data
ms.assetid: a6e72c70-ce18-425f-828d-d57be6f96ab6
caps.latest.revision: 21
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: da016bf659f9eef06074f52e5b716e73d514e48b
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2018
---
# <a name="how-to-customize-data-formatting-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="afa1f-102">방법: Windows Forms DataGridView 컨트롤에서 데이터 형식 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="afa1f-102">How to: Customize Data Formatting in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="afa1f-103">다음 코드 예제에서는 열과 값에 따라 셀이 표시되는 방식을 변경하는 <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> 이벤트에 대한 처리기를 구현하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="afa1f-103">The following code example demonstrates how to implement a handler for the <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> event that changes how cells are displayed depending on their columns and values.</span></span>  
  
 <span data-ttu-id="afa1f-104">음수를 포함하는 `Balance` 열의 셀에는 빨간색 배경이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="afa1f-104">Cells in the `Balance` column that contain negative numbers are given a red background.</span></span> <span data-ttu-id="afa1f-105">또한 이러한 셀에 통화 형식을 지정하여 음수 값을 괄호 안에 표시할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="afa1f-105">You can also format these cells as currency to display parentheses around negative values.</span></span> <span data-ttu-id="afa1f-106">자세한 내용은 [방법: Windows Forms DataGridView 컨트롤의 데이터 형식 지정](../../../../docs/framework/winforms/controls/how-to-format-data-in-the-windows-forms-datagridview-control.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="afa1f-106">For more information, see [How to: Format Data in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/how-to-format-data-in-the-windows-forms-datagridview-control.md).</span></span>  
  
 <span data-ttu-id="afa1f-107">`Priority` 열의 셀에는 해당하는 텍스트 셀 값 대신 이미지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="afa1f-107">Cells in the `Priority` column display images in place of corresponding textual cell values.</span></span> <span data-ttu-id="afa1f-108"><xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs>의 <xref:System.Windows.Forms.ConvertEventArgs.Value%2A> 속성은 텍스트 셀 값을 가져오고 해당하는 이미지 표시 값을 설정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="afa1f-108">The <xref:System.Windows.Forms.ConvertEventArgs.Value%2A> property of the <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs> is used both to get the textual cell value and to set the corresponding image display value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="afa1f-109">예제</span><span class="sxs-lookup"><span data-stu-id="afa1f-109">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewCustomizeDataFormatting#00](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCustomizeDataFormatting/cs/customFormatting.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewCustomizeDataFormatting#00](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCustomizeDataFormatting/vb/customFormatting.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="afa1f-110">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="afa1f-110">Compiling the Code</span></span>  
 <span data-ttu-id="afa1f-111">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="afa1f-111">This example requires:</span></span>  
  
-   <span data-ttu-id="afa1f-112">System, System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="afa1f-112">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
-   <span data-ttu-id="afa1f-113">실행 파일과 동일한 디렉터리에 있는 `highPri.bmp`, `mediumPri.bmp` 및 `lowPri.bmp`로 명명된 <xref:System.Drawing.Bitmap> 이미지</span><span class="sxs-lookup"><span data-stu-id="afa1f-113"><xref:System.Drawing.Bitmap> images named `highPri.bmp`, `mediumPri.bmp`, and `lowPri.bmp` residing in the same directory as the executable file.</span></span>  
  
 <span data-ttu-id="afa1f-114">Visual Basic 또는 Visual C#에 대 한 명령줄에서이 예제를 빌드하는 방법에 대 한 정보를 참조 하십시오. [명령줄에서 빌드](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) 또는 [사용한 명령줄 빌드 csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="afa1f-114">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="afa1f-115">새 프로젝트에 코드를 붙여 넣어 Visual Studio에서이 예제를 빌드할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="afa1f-115">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="afa1f-116">[방법: Visual Studio를 사용하여 전체 Windows Forms 코드 예제 컴파일 및 실행](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\))을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="afa1f-116">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="afa1f-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="afa1f-117">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewCellStyle>  
 <xref:System.Drawing.Bitmap>  
 [<span data-ttu-id="afa1f-118">Windows Forms DataGridView 컨트롤에서 데이터 표시</span><span class="sxs-lookup"><span data-stu-id="afa1f-118">Displaying Data in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="afa1f-119">방법: Windows Forms DataGridView 컨트롤의 데이터 형식 지정</span><span class="sxs-lookup"><span data-stu-id="afa1f-119">How to: Format Data in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-format-data-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="afa1f-120">Windows Forms DataGridView 컨트롤의 셀 스타일</span><span class="sxs-lookup"><span data-stu-id="afa1f-120">Cell Styles in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="afa1f-121">Windows Forms DataGridView 컨트롤의 데이터 형식 지정</span><span class="sxs-lookup"><span data-stu-id="afa1f-121">Data Formatting in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/data-formatting-in-the-windows-forms-datagridview-control.md)
