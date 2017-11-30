---
title: "방법: MDI에 ToolStripPanels 사용"
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
- MDI [Windows Forms], using ToolStripPanels [Windows Forms]
- ToolStripPanel control [Windows Forms], using for MDI
- toolbars [Windows Forms], using for MDI
ms.assetid: d6b884fc-0846-465f-83c3-5dc0fe93b00f
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7b9d7c35a77a24ed9a531a46f0c8cd358134a41b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-toolstrippanels-for-mdi"></a><span data-ttu-id="cfcac-102">방법: MDI에 ToolStripPanels 사용</span><span class="sxs-lookup"><span data-stu-id="cfcac-102">How to: Use ToolStripPanels for MDI</span></span>
<span data-ttu-id="cfcac-103"><xref:System.Windows.Forms.ToolStripPanel>에서는 <xref:System.Windows.Forms.ToolStripPanel.Join%2A> 메서드를 사용하여 MDI(다중 문서 인터페이스) 응용 프로그램에 대한 유연성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cfcac-103">The <xref:System.Windows.Forms.ToolStripPanel> provides flexibility for multiple-document interface (MDI) applications by using the <xref:System.Windows.Forms.ToolStripPanel.Join%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cfcac-104">예제</span><span class="sxs-lookup"><span data-stu-id="cfcac-104">Example</span></span>  
 <span data-ttu-id="cfcac-105">다음 코드 예제에서는 MDI에 대해 <xref:System.Windows.Forms.ToolStripPanel> 컨트롤을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cfcac-105">The following code example demonstrates how to use <xref:System.Windows.Forms.ToolStripPanel> controls for MDI.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#10)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#10)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="cfcac-106">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="cfcac-106">Compiling the Code</span></span>  
 <span data-ttu-id="cfcac-107">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="cfcac-107">This example requires:</span></span>  
  
-   <span data-ttu-id="cfcac-108">System.Design, System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="cfcac-108">References to the System.Design, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="cfcac-109">[!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] 또는 [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)]의 명령줄에서 이 예제를 빌드하는 방법에 대한 자세한 내용은 [명령줄에서 빌드](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) 또는 [csc.exe를 사용한 명령줄 빌드](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cfcac-109">For information about building this example from the command line for [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] or [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="cfcac-110">[!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]에서 코드를 새 프로젝트에 붙여넣어 이 예제를 빌드할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfcac-110">You can also build this example in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] by pasting the code into a new project.</span></span>  <span data-ttu-id="cfcac-111">[방법: Visual Studio를 사용하여 전체 Windows Forms 코드 예제 컴파일 및 실행](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\))을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cfcac-111">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfcac-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cfcac-112">See Also</span></span>  
 <xref:System.Windows.Forms.ToolStripPanel>  
 [<span data-ttu-id="cfcac-113">방법: ToolStripPanels 조인</span><span class="sxs-lookup"><span data-stu-id="cfcac-113">How to: Join ToolStripPanels</span></span>](../../../../docs/framework/winforms/controls/how-to-join-toolstrippanels.md)
