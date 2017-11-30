---
title: "방법: 메뉴 병합 및 ToolStrip 컨트롤을 사용하여 MDI 폼 만들기"
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
- toolbars [Windows Forms]
- ToolStripPanel control [Windows Forms]
- ToolStrip control [Windows Forms]
- MenuStrip control [Windows Forms]
ms.assetid: 64992ed9-44af-4baf-b45f-863e6ab35711
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4b99f68c970efc096bc4dfab264183de11beb135
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls"></a><span data-ttu-id="5de73-102">방법: 메뉴 병합 및 ToolStrip 컨트롤을 사용하여 MDI 폼 만들기</span><span class="sxs-lookup"><span data-stu-id="5de73-102">How to: Create an MDI Form with Menu Merging and ToolStrip Controls</span></span>
<span data-ttu-id="5de73-103"><xref:System.Windows.Forms?displayProperty=nameWithType> 네임스페이스는 MDI(다중 문서 인터페이스) 응용 프로그램을 지원하고 <xref:System.Windows.Forms.MenuStrip> 컨트롤은 메뉴 병합을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="5de73-103">The <xref:System.Windows.Forms?displayProperty=nameWithType> namespace supports multiple document interface (MDI) applications, and the <xref:System.Windows.Forms.MenuStrip> control supports menu merging.</span></span> <span data-ttu-id="5de73-104">MDI 폼은 <xref:System.Windows.Forms.ToolStrip> 컨트롤일 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5de73-104">MDI forms can also <xref:System.Windows.Forms.ToolStrip> controls.</span></span>  
  
 <span data-ttu-id="5de73-105">[!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]에서는 이 기능이 광범위하게 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="5de73-105">There is extensive support for this feature in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)].</span></span>  
  
 <span data-ttu-id="5de73-106">또한 [연습: 메뉴 병합 및 ToolStrip 컨트롤을 사용하여 MDI 양식 만들기](http://msdn.microsoft.com/library/ms233676\(v=vs.110\))를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5de73-106">Also see [Walkthrough: Creating an MDI Form with Menu Merging and ToolStrip Controls](http://msdn.microsoft.com/library/ms233676\(v=vs.110\)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5de73-107">예제</span><span class="sxs-lookup"><span data-stu-id="5de73-107">Example</span></span>  
 <span data-ttu-id="5de73-108">다음 코드 예제에서는 MDI 폼과 함께 <xref:System.Windows.Forms.ToolStripPanel> 컨트롤을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5de73-108">The following code example demonstrates how to use <xref:System.Windows.Forms.ToolStripPanel> controls with an MDI form.</span></span> <span data-ttu-id="5de73-109">폼은 자식 메뉴와 메뉴 병합도 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="5de73-109">The form also supports menu merging with child menus.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.MdiForm#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.MdiForm#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="5de73-110">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="5de73-110">Compiling the Code</span></span>  
 <span data-ttu-id="5de73-111">이 코드 예제에는 다음이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="5de73-111">This code example requires:</span></span>  
  
-   <span data-ttu-id="5de73-112">System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="5de73-112">References to the System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="5de73-113">[!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] 또는 [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)]의 명령줄에서 이 예제를 빌드하는 방법에 대한 자세한 내용은 [명령줄에서 빌드](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) 또는 [csc.exe를 사용한 명령줄 빌드](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5de73-113">For information about building this example from the command line for [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] or [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="5de73-114">[!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]에서 코드를 새 프로젝트에 붙여넣어 이 예제를 빌드할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5de73-114">You can also build this example in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] by pasting the code into a new project.</span></span>  <span data-ttu-id="5de73-115">또한 [방법: Visual Studio를 사용하여 전체 Windows Forms 코드 예제 컴파일 및 실행](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\))을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5de73-115">Also sssee [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5de73-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5de73-116">See Also</span></span>  
 [<span data-ttu-id="5de73-117">ToolStrip 컨트롤</span><span class="sxs-lookup"><span data-stu-id="5de73-117">ToolStrip Control</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)
