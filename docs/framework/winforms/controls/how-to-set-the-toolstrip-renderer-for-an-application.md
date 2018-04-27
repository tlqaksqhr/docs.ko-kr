---
title: '방법: 응용 프로그램에 대한 ToolStrip 렌더러 설정'
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
- Renderer property [Windows Forms]
- ToolStripProfessionalRenderer class [Windows Forms]
- ToolStrip control [Windows Forms]
- MenuStrip control [Windows Forms]
- toolbars [Windows Forms], customizing
ms.assetid: 46acef3e-9844-4ae8-9a2e-3006fe99cadf
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 242bdd556a85c92d595c36b79b99756e8459dbf3
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2018
---
# <a name="how-to-set-the-toolstrip-renderer-for-an-application"></a><span data-ttu-id="9745b-102">방법: 응용 프로그램에 대한 ToolStrip 렌더러 설정</span><span class="sxs-lookup"><span data-stu-id="9745b-102">How to: Set the ToolStrip Renderer for an Application</span></span>
<span data-ttu-id="9745b-103"><xref:System.Windows.Forms.ToolStrip> 컨트롤의 모양을 개별적으로 또는 응용 프로그램의 모든 <xref:System.Windows.Forms.ToolStrip> 컨트롤에 대해 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9745b-103">You can customize the appearance of your <xref:System.Windows.Forms.ToolStrip> controls individually or for all the <xref:System.Windows.Forms.ToolStrip> controls in your application.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9745b-104">예제</span><span class="sxs-lookup"><span data-stu-id="9745b-104">Example</span></span>  
 <span data-ttu-id="9745b-105">다음 코드 예제에서는 <xref:System.Windows.Forms.ToolStrip> 컨트롤 및 <xref:System.Windows.Forms.MenuStrip> 컨트롤에 사용자 지정 렌더러를 선택적으로 적용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9745b-105">The following code example demonstrates how to selectively apply a custom renderer to a <xref:System.Windows.Forms.ToolStrip> control and a <xref:System.Windows.Forms.MenuStrip> control.</span></span>  
  
 <span data-ttu-id="9745b-106">이 코드 예제를 사용하려면 응용 프로그램을 컴파일 및 실행한 다음 <xref:System.Windows.Forms.ComboBox> 컨트롤에서 사용자 지정 렌더링 범위를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9745b-106">To use this code example, compile and run the application, and then select the scope of the custom rending from the <xref:System.Windows.Forms.ComboBox> control.</span></span> <span data-ttu-id="9745b-107">**적용**을 클릭하여 렌더러를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9745b-107">Click **Apply** to set the renderer.</span></span>  
  
 <span data-ttu-id="9745b-108">사용자 지정 메뉴 항목 렌더링을 보려면 선택는 <xref:System.Windows.Forms.MenuStrip> 에서 옵션는 <xref:System.Windows.Forms.ComboBox> 컨트롤을 클릭 하 여 **적용**, 연 다음는 **파일** 메뉴 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="9745b-108">To see custom menu item rendering, select the <xref:System.Windows.Forms.MenuStrip> option from the <xref:System.Windows.Forms.ComboBox> control, click **Apply**, and then open the **File** menu item.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#1)]  
[!code-csharp[System.Windows.Forms.ToolStrip.Misc#70](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#70)]
[!code-vb[System.Windows.Forms.ToolStrip.Misc#70](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#70)]  
  
 <span data-ttu-id="9745b-109"><xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> 속성을 설정하여 응용 프로그램의 모든 <xref:System.Windows.Forms.ToolStrip> 컨트롤에 사용자 지정 렌더러를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="9745b-109">Set the <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> property to apply a custom renderer to all the <xref:System.Windows.Forms.ToolStrip> controls in your application.</span></span>  
  
 <span data-ttu-id="9745b-110"><xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> 속성을 설정하여 개별 <xref:System.Windows.Forms.ToolStrip> 컨트롤에 사용자 지정 렌더러를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="9745b-110">Set the <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> property to apply a custom renderer to an individual <xref:System.Windows.Forms.ToolStrip> control.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9745b-111">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="9745b-111">Compiling the Code</span></span>  
 <span data-ttu-id="9745b-112">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="9745b-112">This example requires:</span></span>  
  
-   <span data-ttu-id="9745b-113">System.Design, System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="9745b-113">References to the System.Design, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="9745b-114">Visual Basic 또는 Visual C#에 대 한 명령줄에서이 예제를 빌드하는 방법에 대 한 정보를 참조 하십시오. [명령줄에서 빌드](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) 또는 [사용한 명령줄 빌드 csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9745b-114">For information about building this example from the command line for visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="9745b-115">새 프로젝트에 코드를 붙여 넣어 Visual Studio에서이 예제를 빌드할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9745b-115">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="9745b-116">[방법: Visual Studio를 사용하여 전체 Windows Forms 코드 예제 컴파일 및 실행](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\))을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9745b-116">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9745b-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9745b-117">See Also</span></span>  
 <xref:System.Windows.Forms.ToolStripManager>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.ToolStripProfessionalRenderer>  
 [<span data-ttu-id="9745b-118">ToolStrip 컨트롤</span><span class="sxs-lookup"><span data-stu-id="9745b-118">ToolStrip Control</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)
