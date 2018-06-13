---
title: '방법: 도킹된 ToolStrip 컨트롤의 Z 순서 정의'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms]
- MenuStrip control [Windows Forms]
- toolbars [Windows Forms], specifying z-order
- z-order
ms.assetid: 8b595429-ba9f-46af-9c55-3d5cc53f7fff
ms.openlocfilehash: 48b7338568de17e941e1e464b9ff906a4bc93c3d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33532111"
---
# <a name="how-to-define-z-ordering-of-docked-toolstrip-controls"></a><span data-ttu-id="3d99d-102">방법: 도킹된 ToolStrip 컨트롤의 Z 순서 정의</span><span class="sxs-lookup"><span data-stu-id="3d99d-102">How to: Define Z-Ordering of Docked ToolStrip Controls</span></span>
<span data-ttu-id="3d99d-103">도킹을 사용하여 <xref:System.Windows.Forms.ToolStrip> 컨트롤을 올바르게 배치하려면 폼의 z 순서에 컨트롤을 올바르게 배치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d99d-103">To position a <xref:System.Windows.Forms.ToolStrip> control correctly with docking, you must position the control correctly in the form's z-order.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3d99d-104">예제</span><span class="sxs-lookup"><span data-stu-id="3d99d-104">Example</span></span>  
 <span data-ttu-id="3d99d-105">다음 코드 예제에서는 z 순서를 지정하여 <xref:System.Windows.Forms.ToolStrip> 컨트롤 및 도킹된 <xref:System.Windows.Forms.MenuStrip> 컨트롤을 정렬하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3d99d-105">The following code example demonstrates how to arrange a <xref:System.Windows.Forms.ToolStrip> control and a docked <xref:System.Windows.Forms.MenuStrip> control by specifying the z-order.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#21)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#21)]  
  
 <span data-ttu-id="3d99d-106">z 순서는 <xref:System.Windows.Forms.ToolStrip> 및 <xref:System.Windows.Forms.MenuStrip></span><span class="sxs-lookup"><span data-stu-id="3d99d-106">The z-order is determined by the order in which the <xref:System.Windows.Forms.ToolStrip> and <xref:System.Windows.Forms.MenuStrip></span></span>  
  
 <span data-ttu-id="3d99d-107">컨트롤이 폼의 <xref:System.Windows.Forms.Control.Controls%2A> 컬렉션에 추가된 순서에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d99d-107">controls are added to the form's <xref:System.Windows.Forms.Control.Controls%2A> collection.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#23)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#23)]  
  
 <span data-ttu-id="3d99d-108">이러한 <xref:System.Windows.Forms.Control.ControlCollection.Add%2A> 메서드 호출 순서를 반대로 바꾸고 레이아웃에 미치는 영향을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="3d99d-108">Reverse the order of these calls to the <xref:System.Windows.Forms.Control.ControlCollection.Add%2A> method and view the effect on the layout.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="3d99d-109">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="3d99d-109">Compiling the Code</span></span>  
 <span data-ttu-id="3d99d-110">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="3d99d-110">This example requires:</span></span>  
  
-   <span data-ttu-id="3d99d-111">System.Design, System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="3d99d-111">References to the System.Design, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="3d99d-112">Visual Basic 또는 Visual C#에 대 한 명령줄에서이 예제를 빌드하는 방법에 대 한 정보를 참조 하십시오. [명령줄에서 빌드](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) 또는 [사용한 명령줄 빌드 csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3d99d-112">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="3d99d-113">새 프로젝트에 코드를 붙여 넣어 Visual Studio에서이 예제를 빌드할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d99d-113">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="3d99d-114">또한 [방법: Visual Studio를 사용하여 전체 Windows Forms 코드 예제 컴파일 및 실행](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\))을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3d99d-114">Also se [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d99d-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3d99d-115">See Also</span></span>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.Control.ControlCollection.Add%2A>  
 <xref:System.Windows.Forms.Control.Controls%2A>  
 <xref:System.Windows.Forms.Control.Dock%2A>  
 [<span data-ttu-id="3d99d-116">ToolStrip 컨트롤</span><span class="sxs-lookup"><span data-stu-id="3d99d-116">ToolStrip Control</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)
