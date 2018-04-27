---
title: '방법: 폼에 표준 메뉴 항목 제공'
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
- toolbars [Windows Forms]
- menu items [Windows Forms], standard
- ToolStrip control [Windows Forms]
ms.assetid: 75db9126-e70c-4e81-921d-b83c0a4a9f50
caps.latest.revision: 7
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e6e2514adc2b2bbd5b2d1ab3371b48d760842140
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2018
---
# <a name="how-to-provide-standard-menu-items-to-a-form"></a><span data-ttu-id="dfb2e-102">방법: 폼에 표준 메뉴 항목 제공</span><span class="sxs-lookup"><span data-stu-id="dfb2e-102">How to: Provide Standard Menu Items to a Form</span></span>
<span data-ttu-id="dfb2e-103"><xref:System.Windows.Forms.MenuStrip> 컨트롤을 사용하여 폼에 표준 메뉴를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfb2e-103">You can provide a standard menu for your forms with the <xref:System.Windows.Forms.MenuStrip> control.</span></span>  
  
 <span data-ttu-id="dfb2e-104">Visual Studio에서는이 기능이 광범위 하 게 지원이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfb2e-104">There is extensive support for this feature in Visual Studio.</span></span>  
  
 <span data-ttu-id="dfb2e-105">또한 [연습: 양식에 표준 메뉴 항목 제공](http://msdn.microsoft.com/library/ms233662\(v=vs.110\))을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dfb2e-105">Also see [Walkthrough: Providing Standard Menu Items to a Form](http://msdn.microsoft.com/library/ms233662\(v=vs.110\)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="dfb2e-106">예제</span><span class="sxs-lookup"><span data-stu-id="dfb2e-106">Example</span></span>  
 <span data-ttu-id="dfb2e-107">다음 코드 예제에서는 <xref:System.Windows.Forms.MenuStrip> 컨트롤을 사용하여 표준 메뉴가 있는 폼을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="dfb2e-107">The following code example demonstrates how to use a <xref:System.Windows.Forms.MenuStrip> control to create a form with a standard menu.</span></span> <span data-ttu-id="dfb2e-108">메뉴 항목 선택이 <xref:System.Windows.Forms.StatusStrip> 컨트롤에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="dfb2e-108">Menu item selections are displayed in a <xref:System.Windows.Forms.StatusStrip> control.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="dfb2e-109">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="dfb2e-109">Compiling the Code</span></span>  
 <span data-ttu-id="dfb2e-110">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="dfb2e-110">This example requires:</span></span>  
  
-   <span data-ttu-id="dfb2e-111">System, System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="dfb2e-111">References to the System, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="dfb2e-112">Visual Basic 또는 Visual C#에 대 한 명령줄에서이 예제를 빌드하는 방법에 대 한 정보를 참조 하십시오. [명령줄에서 빌드](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) 또는 [사용한 명령줄 빌드 csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="dfb2e-112">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="dfb2e-113">새 프로젝트에 코드를 붙여 넣어 Visual Studio에서이 예제를 빌드할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfb2e-113">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="dfb2e-114">[방법: Visual Studio를 사용하여 전체 Windows Forms 코드 예제 컴파일 및 실행](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\))을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dfb2e-114">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfb2e-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dfb2e-115">See Also</span></span>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.StatusStrip>  
 [<span data-ttu-id="dfb2e-116">MenuStrip 컨트롤</span><span class="sxs-lookup"><span data-stu-id="dfb2e-116">MenuStrip Control</span></span>](../../../../docs/framework/winforms/controls/menustrip-control-windows-forms.md)
