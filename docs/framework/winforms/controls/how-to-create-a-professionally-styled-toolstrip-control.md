---
title: '방법: 전문적인 스타일의 ToolStrip 컨트롤 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms]
- ToolStripProfessionalRenderer class [Windows Forms]
- ToolStripRenderer class [Windows Forms]
- ToolStrip control [Windows Forms]
ms.assetid: c208b2f6-8105-474b-9075-d582e1792870
ms.openlocfilehash: 3fe99fadc7ddccd5c4921c4694c5b546f4fd4749
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33533187"
---
# <a name="how-to-create-a-professionally-styled-toolstrip-control"></a><span data-ttu-id="d23e0-102">방법: 전문적인 스타일의 ToolStrip 컨트롤 만들기</span><span class="sxs-lookup"><span data-stu-id="d23e0-102">How to: Create a Professionally Styled ToolStrip Control</span></span>
<span data-ttu-id="d23e0-103"><xref:System.Windows.Forms.ToolStripProfessionalRenderer> 형식에서 파생된 고유한 클래스를 작성하여 응용 프로그램의 <xref:System.Windows.Forms.ToolStrip> 컨트롤에 전문적인 모양과 동작(모양 및 느낌)을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d23e0-103">You can give your application’s <xref:System.Windows.Forms.ToolStrip> controls a professional appearance and behavior (look and feel) by writing your own class derived from the <xref:System.Windows.Forms.ToolStripProfessionalRenderer> type.</span></span>  
  
 <span data-ttu-id="d23e0-104">Visual Studio에서는이 기능이 광범위 하 게 지원이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d23e0-104">There is extensive support for this feature in Visual Studio.</span></span>  
  
 <span data-ttu-id="d23e0-105">[연습: 전문적인 스타일의 ToolStrip 컨트롤 만들기](../../../../docs/framework/winforms/controls/walkthrough-creating-a-professionally-styled-toolstrip-control.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d23e0-105">See [Walkthrough: Creating a Professionally Styled ToolStrip Control](../../../../docs/framework/winforms/controls/walkthrough-creating-a-professionally-styled-toolstrip-control.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d23e0-106">예제</span><span class="sxs-lookup"><span data-stu-id="d23e0-106">Example</span></span>  
 <span data-ttu-id="d23e0-107">다음 코드 예제에서는 사용 하는 방법을 보여 줍니다. <xref:System.Windows.Forms.ToolStrip> 모방 하는 복합 컨트롤을 만들 컨트롤에는 **탐색 창** Microsoft® Outlook®에서 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d23e0-107">The following code example demonstrates how to use <xref:System.Windows.Forms.ToolStrip> controls to create a composite control that mimics the **Navigation Pane** provided by Microsoft® Outlook®.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.StackView#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.StackView#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d23e0-108">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="d23e0-108">Compiling the Code</span></span>  
 <span data-ttu-id="d23e0-109">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d23e0-109">This example requires:</span></span>  
  
-   <span data-ttu-id="d23e0-110">System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="d23e0-110">References to the System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="d23e0-111">Visual Basic 또는 Visual C#에 대 한 명령줄에서이 예제를 빌드하는 방법에 대 한 정보를 참조 하십시오. [명령줄에서 빌드](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) 또는 [사용한 명령줄 빌드 csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d23e0-111">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="d23e0-112">새 프로젝트에 코드를 붙여 넣어 Visual Studio에서이 예제를 빌드할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d23e0-112">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="d23e0-113">또한 [연습: 전문적인 스타일의 ToolStrip 컨트롤 만들기](http://msdn.microsoft.com/library/ms233664\(v=vs.110\))를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d23e0-113">Also see [Walkthrough: Creating a Professionally Styled ToolStrip Control](http://msdn.microsoft.com/library/ms233664\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d23e0-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d23e0-114">See Also</span></span>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.StatusStrip>  
 [<span data-ttu-id="d23e0-115">ToolStrip 컨트롤</span><span class="sxs-lookup"><span data-stu-id="d23e0-115">ToolStrip Control</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)  
 [<span data-ttu-id="d23e0-116">방법: 양식에 표준 메뉴 항목 제공</span><span class="sxs-lookup"><span data-stu-id="d23e0-116">How to: Provide Standard Menu Items to a Form</span></span>](../../../../docs/framework/winforms/controls/how-to-provide-standard-menu-items-to-a-form.md)
