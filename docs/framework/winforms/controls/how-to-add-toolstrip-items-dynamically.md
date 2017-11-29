---
title: "방법: 동적으로 ToolStrip 항목 추가"
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
- ContextMenuStrip control [Windows Forms]
- toolbars [Windows Forms], adding items dynamically
- ToolStrip control [Windows Forms]
ms.assetid: 0e8dea56-5f46-408b-914d-7e360341a234
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c7287365013ecd32d5ade6fa61d6c13364ce9b97
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-add-toolstrip-items-dynamically"></a><span data-ttu-id="8eaf0-102">방법: 동적으로 ToolStrip 항목 추가</span><span class="sxs-lookup"><span data-stu-id="8eaf0-102">How to: Add ToolStrip Items Dynamically</span></span>
<span data-ttu-id="8eaf0-103">메뉴가 열릴 때 <xref:System.Windows.Forms.ToolStrip> 컨트롤의 메뉴 항목 컬렉션을 동적으로 채울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8eaf0-103">You can dynamically populate the menu item collection of a <xref:System.Windows.Forms.ToolStrip> control when the menu opens.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8eaf0-104">예제</span><span class="sxs-lookup"><span data-stu-id="8eaf0-104">Example</span></span>  
 <span data-ttu-id="8eaf0-105">다음 코드 예제에서는 <xref:System.Windows.Forms.ContextMenuStrip> 컨트롤에 항목을 동적으로 추가하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8eaf0-105">The following code example demonstrates how to dynamically add items to a <xref:System.Windows.Forms.ContextMenuStrip> control.</span></span> <span data-ttu-id="8eaf0-106">예제에서는 양식에서 세 가지 다른 컨트롤에 대해 같은 <xref:System.Windows.Forms.ContextMenuStrip>을 다시 사용하는 방법도 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8eaf0-106">The example also shows how to reuse the same <xref:System.Windows.Forms.ContextMenuStrip> for three different controls on the form.</span></span>  
  
 <span data-ttu-id="8eaf0-107">예제에서 <xref:System.Windows.Forms.ToolStripDropDown.Opening> 이벤트 처리기는 메뉴 항목 컬렉션을 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="8eaf0-107">In the example, an <xref:System.Windows.Forms.ToolStripDropDown.Opening> event handler populates the menu item collection.</span></span> <span data-ttu-id="8eaf0-108"><xref:System.Windows.Forms.ToolStripDropDown.Opening> 이벤트 처리기는 <xref:System.Windows.Forms.ContextMenuStrip.SourceControl%2A?displayProperty=nameWithType> 및 <xref:System.Windows.Forms.ToolStripItem.OwnerItem%2A?displayProperty=nameWithType> 속성을 검사하고 소스 컨트롤을 설명하는 <xref:System.Windows.Forms.ToolStripItem>을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8eaf0-108">The <xref:System.Windows.Forms.ToolStripDropDown.Opening> event handler examines the <xref:System.Windows.Forms.ContextMenuStrip.SourceControl%2A?displayProperty=nameWithType> and <xref:System.Windows.Forms.ToolStripItem.OwnerItem%2A?displayProperty=nameWithType> properties and adds a <xref:System.Windows.Forms.ToolStripItem> describing the source control.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#1)]  
[!code-csharp[System.Windows.Forms.ToolStrip.Misc#40](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#40)]
[!code-vb[System.Windows.Forms.ToolStrip.Misc#40](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#40)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="8eaf0-109">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="8eaf0-109">Compiling the Code</span></span>  
 <span data-ttu-id="8eaf0-110">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="8eaf0-110">This example requires:</span></span>  
  
-   <span data-ttu-id="8eaf0-111">System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="8eaf0-111">References to the System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="8eaf0-112">[!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] 또는 [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)]의 명령줄에서 이 예제를 빌드하는 방법에 대한 자세한 내용은 [명령줄에서 빌드](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) 또는 [csc.exe를 사용한 명령줄 빌드](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8eaf0-112">For information about building this example from the command line for [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] or [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="8eaf0-113">[!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]에서 코드를 새 프로젝트에 붙여넣어 이 예제를 빌드할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8eaf0-113">You can also build this example in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8eaf0-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8eaf0-114">See Also</span></span>  
 <xref:System.Windows.Forms.ContextMenuStrip>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.ToolStripItem>  
 <xref:System.Windows.Forms.ToolStripMenuItem>  
 <xref:System.Windows.Forms.ToolStripDropDownButton>  
 [<span data-ttu-id="8eaf0-115">ToolStrip 컨트롤</span><span class="sxs-lookup"><span data-stu-id="8eaf0-115">ToolStrip Control</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)
