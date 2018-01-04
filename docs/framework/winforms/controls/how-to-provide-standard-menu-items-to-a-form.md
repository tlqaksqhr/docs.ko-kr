---
title: "방법: 폼에 표준 메뉴 항목 제공"
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
- menu items [Windows Forms], standard
- ToolStrip control [Windows Forms]
ms.assetid: 75db9126-e70c-4e81-921d-b83c0a4a9f50
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 934be102373440c9eb867e33addd96c544599a87
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-provide-standard-menu-items-to-a-form"></a><span data-ttu-id="f20bf-102">방법: 폼에 표준 메뉴 항목 제공</span><span class="sxs-lookup"><span data-stu-id="f20bf-102">How to: Provide Standard Menu Items to a Form</span></span>
<span data-ttu-id="f20bf-103"><xref:System.Windows.Forms.MenuStrip> 컨트롤을 사용하여 폼에 표준 메뉴를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f20bf-103">You can provide a standard menu for your forms with the <xref:System.Windows.Forms.MenuStrip> control.</span></span>  
  
 <span data-ttu-id="f20bf-104">[!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]에서는 이 기능이 광범위하게 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="f20bf-104">There is extensive support for this feature in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)].</span></span>  
  
 <span data-ttu-id="f20bf-105">또한 [연습: 양식에 표준 메뉴 항목 제공](http://msdn.microsoft.com/library/ms233662\(v=vs.110\))을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f20bf-105">Also see [Walkthrough: Providing Standard Menu Items to a Form](http://msdn.microsoft.com/library/ms233662\(v=vs.110\)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f20bf-106">예</span><span class="sxs-lookup"><span data-stu-id="f20bf-106">Example</span></span>  
 <span data-ttu-id="f20bf-107">다음 코드 예제에서는 <xref:System.Windows.Forms.MenuStrip> 컨트롤을 사용하여 표준 메뉴가 있는 폼을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f20bf-107">The following code example demonstrates how to use a <xref:System.Windows.Forms.MenuStrip> control to create a form with a standard menu.</span></span> <span data-ttu-id="f20bf-108">메뉴 항목 선택이 <xref:System.Windows.Forms.StatusStrip> 컨트롤에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f20bf-108">Menu item selections are displayed in a <xref:System.Windows.Forms.StatusStrip> control.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f20bf-109">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="f20bf-109">Compiling the Code</span></span>  
 <span data-ttu-id="f20bf-110">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f20bf-110">This example requires:</span></span>  
  
-   <span data-ttu-id="f20bf-111">System, System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="f20bf-111">References to the System, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="f20bf-112">[!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] 또는 [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)]의 명령줄에서 이 예제를 빌드하는 방법에 대한 자세한 내용은 [명령줄에서 빌드](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) 또는 [csc.exe를 사용한 명령줄 빌드](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f20bf-112">For information about building this example from the command line for [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] or [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="f20bf-113">[!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]에서 코드를 새 프로젝트에 붙여넣어 이 예제를 빌드할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f20bf-113">You can also build this example in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] by pasting the code into a new project.</span></span>  <span data-ttu-id="f20bf-114">[방법: Visual Studio를 사용하여 전체 Windows Forms 코드 예제 컴파일 및 실행](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\))을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f20bf-114">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f20bf-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f20bf-115">See Also</span></span>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.StatusStrip>  
 [<span data-ttu-id="f20bf-116">MenuStrip 컨트롤</span><span class="sxs-lookup"><span data-stu-id="f20bf-116">MenuStrip Control</span></span>](../../../../docs/framework/winforms/controls/menustrip-control-windows-forms.md)
