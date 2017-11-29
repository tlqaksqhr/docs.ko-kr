---
title: "방법: 코드 섹션 축소 및 숨기기(Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Visual Basic, code collapsing
- Visual Basic, code hiding
- Visual Basic code, collapsing and hiding
ms.assetid: b770e8f5-e07d-491a-ab4b-a977980f9ba2
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 56a31f0c8af9b84e87ebe1e5191d72d19be8340f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-collapse-and-hide-sections-of-code-visual-basic"></a><span data-ttu-id="602a5-102">방법: 코드 섹션 축소 및 숨기기(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="602a5-102">How to: Collapse and Hide Sections of Code (Visual Basic)</span></span>
<span data-ttu-id="602a5-103">`#Region` 지시문을 사용 하면 코드 섹션 축소 및 숨기기 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="602a5-103">The `#Region` directive enables you to collapse and hide sections of code in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] files.</span></span> <span data-ttu-id="602a5-104">`#Region` 지시문을 사용 하면 사용 하는 경우 축소 또는 확장할 수 있는 코드 블록을 지정할 수는 [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] 코드 편집기.</span><span class="sxs-lookup"><span data-stu-id="602a5-104">The `#Region` directive lets you specify a block of code that you can expand or collapse when using the [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] code editor.</span></span> <span data-ttu-id="602a5-105">선택적으로 코드를 숨기는 기능은 좀 더 관리 및 보다 쉽게 읽을 수 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="602a5-105">The ability to hide code selectively makes your files more manageable and easier to read.</span></span> <span data-ttu-id="602a5-106">자세한 내용은 [개요](/visualstudio/ide/outlining)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="602a5-106">For more information, see [Outlining](/visualstudio/ide/outlining).</span></span>  
  
 <span data-ttu-id="602a5-107">`#Region`지시문을 코드 블록의 의미와 같은 지원 `#If...#End If`합니다.</span><span class="sxs-lookup"><span data-stu-id="602a5-107">`#Region` directives support code block semantics such as `#If...#End If`.</span></span> <span data-ttu-id="602a5-108">즉, 끝 엔티티; 있으며 한 블록에서 시작할 수 없습니다. 시작 및 종료 같은 블록에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="602a5-108">This means they cannot begin in one block and end in another; the start and end must be in the same block.</span></span> <span data-ttu-id="602a5-109">`#Region`지시문 함수 내에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="602a5-109">`#Region` directives are not supported within functions.</span></span>  
  
### <a name="to-collapse-and-hide-a-section-of-code"></a><span data-ttu-id="602a5-110">축소 하 고 숨기 코드의 섹션</span><span class="sxs-lookup"><span data-stu-id="602a5-110">To collapse and hide a section of code</span></span>  
  
-   <span data-ttu-id="602a5-111">사이 코드의 섹션 배치는 `#Region` 및 `#End Region` 다음 예제와 같이 문:</span><span class="sxs-lookup"><span data-stu-id="602a5-111">Place the section of code between the `#Region` and `#End Region` statements, as in the following example:</span></span>  
  
     [!code-vb[VbVbalrConditionalComp#6](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/how-to-collapse-and-hide-sections-of-code_1.vb)]  
  
     <span data-ttu-id="602a5-112">`#Region` 블록 코드 파일에 여러 번 사용할 수 있습니다; 즉, 사용자가 자신의 프로시저 및 블록을를 차례로 축소할 수 있는 클래스를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="602a5-112">The `#Region` block can be used multiple times in a code file; thus, users can define their own blocks of procedures and classes that can, in turn, be collapsed.</span></span> <span data-ttu-id="602a5-113">`#Region`블록 내의 다른 중첩 될 수도 있습니다 `#Region` 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="602a5-113">`#Region` blocks can also be nested within other `#Region` blocks.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="602a5-114">코드를 숨기 더라도 컴파일에서 하지 않는 및 영향을 주지 않습니다 `#If...#End If` 문.</span><span class="sxs-lookup"><span data-stu-id="602a5-114">Hiding code does not prevent it from being compiled and does not affect `#If...#End If` statements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="602a5-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="602a5-115">See Also</span></span>  
 [<span data-ttu-id="602a5-116">조건부 컴파일</span><span class="sxs-lookup"><span data-stu-id="602a5-116">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)  
 [<span data-ttu-id="602a5-117">#Region 지시문</span><span class="sxs-lookup"><span data-stu-id="602a5-117">#Region Directive</span></span>](../../../visual-basic/language-reference/directives/region-directive.md)  
 [<span data-ttu-id="602a5-118">#If...Then...#Else 지시문</span><span class="sxs-lookup"><span data-stu-id="602a5-118">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)  
 [<span data-ttu-id="602a5-119">개요</span><span class="sxs-lookup"><span data-stu-id="602a5-119">Outlining</span></span>](/visualstudio/ide/outlining)
