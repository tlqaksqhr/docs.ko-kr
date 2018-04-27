---
title: '방법: Windows Forms DataGridView 컨트롤에서 이미지 열 작업'
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
- image columns
- image columns [Windows Forms], Windows Forms
- DataGridView control [Windows Forms], image columns
ms.assetid: 8a37aa75-3c6e-4893-91d0-7a5f34bfe287
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 569b57f9efdd3bbcf39eb2df78cdf40b792008dc
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2018
---
# <a name="how-to-work-with-image-columns-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="8fa94-102">방법: Windows Forms DataGridView 컨트롤에서 이미지 열 작업</span><span class="sxs-lookup"><span data-stu-id="8fa94-102">How to: Work with Image Columns in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="8fa94-103">다음 코드 예제에서는 대화형 UI(사용자 인터페이스)에서 <xref:System.Windows.Forms.DataGridView> 이미지 열을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8fa94-103">The following code example shows how to use the <xref:System.Windows.Forms.DataGridView> image columns in an interactive user interface (UI).</span></span> <span data-ttu-id="8fa94-104">또한 <xref:System.Windows.Forms.DataGridViewImageColumn>에서 가능한 이미지 크기 조정 및 레이아웃 기능을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8fa94-104">The example also demonstrates image sizing and layout possibilities with the <xref:System.Windows.Forms.DataGridViewImageColumn>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8fa94-105">예제</span><span class="sxs-lookup"><span data-stu-id="8fa94-105">Example</span></span>  
 [!code-cpp[System.Windows.Forms.DataGridView.ImageColumn_TicTacToe#0](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.ImageColumn_TicTacToe/CPP/tictactoe.cpp#0)]
 [!code-csharp[System.Windows.Forms.DataGridView.ImageColumn_TicTacToe#0](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.ImageColumn_TicTacToe/CS/tictactoe.cs#0)]
 [!code-vb[System.Windows.Forms.DataGridView.ImageColumn_TicTacToe#0](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.ImageColumn_TicTacToe/VB/tictactoe.vb#0)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="8fa94-106">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="8fa94-106">Compiling the Code</span></span>  
 <span data-ttu-id="8fa94-107">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="8fa94-107">This example requires:</span></span>  
  
-   <span data-ttu-id="8fa94-108">System 및 System.Windows.Forms 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="8fa94-108">References to the System and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="8fa94-109">Visual Basic 또는 Visual C#에 대 한 명령줄에서이 예제를 빌드하는 방법에 대 한 정보를 참조 하십시오. [명령줄에서 빌드](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) 또는 [사용한 명령줄 빌드 csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8fa94-109">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="8fa94-110">새 프로젝트에 코드를 붙여 넣어 Visual Studio에서이 예제를 빌드할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8fa94-110">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="8fa94-111">[방법: Visual Studio를 사용하여 전체 Windows Forms 코드 예제 컴파일 및 실행](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\))을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8fa94-111">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fa94-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8fa94-112">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewImageColumn>  
 [<span data-ttu-id="8fa94-113">Windows Forms DataGridView 컨트롤에서 셀, 행 및 열 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="8fa94-113">Programming with Cells, Rows, and Columns in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/programming-with-cells-rows-and-columns-in-the-datagrid.md)  
 [<span data-ttu-id="8fa94-114">방법: Windows Forms DataGridView 컨트롤의 셀에 이미지 표시</span><span class="sxs-lookup"><span data-stu-id="8fa94-114">How to: Display Images in Cells of the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-display-images-in-cells-of-the-windows-forms-datagridview-control.md)
