---
title: "방법: 전문적인 스타일의 ToolStrip 컨트롤 만들기"
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
- ToolStripProfessionalRenderer class [Windows Forms]
- ToolStripRenderer class [Windows Forms]
- ToolStrip control [Windows Forms]
ms.assetid: c208b2f6-8105-474b-9075-d582e1792870
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0199bad54d7b4ed4f1ed63b22914f8f99bbf6e85
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-professionally-styled-toolstrip-control"></a><span data-ttu-id="bcfbc-102">방법: 전문적인 스타일의 ToolStrip 컨트롤 만들기</span><span class="sxs-lookup"><span data-stu-id="bcfbc-102">How to: Create a Professionally Styled ToolStrip Control</span></span>
<span data-ttu-id="bcfbc-103"><xref:System.Windows.Forms.ToolStripProfessionalRenderer> 형식에서 파생된 고유한 클래스를 작성하여 응용 프로그램의 <xref:System.Windows.Forms.ToolStrip> 컨트롤에 전문적인 모양과 동작(모양 및 느낌)을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bcfbc-103">You can give your application’s <xref:System.Windows.Forms.ToolStrip> controls a professional appearance and behavior (look and feel) by writing your own class derived from the <xref:System.Windows.Forms.ToolStripProfessionalRenderer> type.</span></span>  
  
 <span data-ttu-id="bcfbc-104">[!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]에서는 이 기능이 광범위하게 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="bcfbc-104">There is extensive support for this feature in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)].</span></span>  
  
 <span data-ttu-id="bcfbc-105">[연습: 전문적인 스타일의 ToolStrip 컨트롤 만들기](../../../../docs/framework/winforms/controls/walkthrough-creating-a-professionally-styled-toolstrip-control.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bcfbc-105">See [Walkthrough: Creating a Professionally Styled ToolStrip Control](../../../../docs/framework/winforms/controls/walkthrough-creating-a-professionally-styled-toolstrip-control.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="bcfbc-106">예제</span><span class="sxs-lookup"><span data-stu-id="bcfbc-106">Example</span></span>  
 <span data-ttu-id="bcfbc-107">다음 코드 예제에서는 사용 하는 방법을 보여 줍니다. <xref:System.Windows.Forms.ToolStrip> 모방 하는 복합 컨트롤을 만들 컨트롤에는 **탐색 창** Microsoft® Outlook®에서 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcfbc-107">The following code example demonstrates how to use <xref:System.Windows.Forms.ToolStrip> controls to create a composite control that mimics the **Navigation Pane** provided by Microsoft® Outlook®.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.StackView#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.StackView#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="bcfbc-108">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="bcfbc-108">Compiling the Code</span></span>  
 <span data-ttu-id="bcfbc-109">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="bcfbc-109">This example requires:</span></span>  
  
-   <span data-ttu-id="bcfbc-110">System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="bcfbc-110">References to the System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="bcfbc-111">[!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] 또는 [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)]의 명령줄에서 이 예제를 빌드하는 방법에 대한 자세한 내용은 [명령줄에서 빌드](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) 또는 [csc.exe를 사용한 명령줄 빌드](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bcfbc-111">For information about building this example from the command line for [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] or [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="bcfbc-112">[!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]에서 코드를 새 프로젝트에 붙여넣어 이 예제를 빌드할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bcfbc-112">You can also build this example in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] by pasting the code into a new project.</span></span>  <span data-ttu-id="bcfbc-113">또한 [연습: 전문적인 스타일의 ToolStrip 컨트롤 만들기](http://msdn.microsoft.com/library/ms233664\(v=vs.110\))를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bcfbc-113">Also see [Walkthrough: Creating a Professionally Styled ToolStrip Control](http://msdn.microsoft.com/library/ms233664\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bcfbc-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bcfbc-114">See Also</span></span>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.StatusStrip>  
 [<span data-ttu-id="bcfbc-115">ToolStrip 컨트롤</span><span class="sxs-lookup"><span data-stu-id="bcfbc-115">ToolStrip Control</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)  
 [<span data-ttu-id="bcfbc-116">방법: 양식에 표준 메뉴 항목 제공</span><span class="sxs-lookup"><span data-stu-id="bcfbc-116">How to: Provide Standard Menu Items to a Form</span></span>](../../../../docs/framework/winforms/controls/how-to-provide-standard-menu-items-to-a-form.md)
