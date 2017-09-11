---
title: "방법: (Visual Basic) 코드 섹션 축소 및 숨기기 | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Visual Basic, code collapsing
- Visual Basic, code hiding
- Visual Basic code, collapsing and hiding
ms.assetid: b770e8f5-e07d-491a-ab4b-a977980f9ba2
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 4dcd5cd5d79629fd008534112cb72d5bcfec476e
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-collapse-and-hide-sections-of-code-visual-basic"></a><span data-ttu-id="f0473-102">방법: 코드 섹션 축소 및 숨기기(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f0473-102">How to: Collapse and Hide Sections of Code (Visual Basic)</span></span>
<span data-ttu-id="f0473-103">`#Region` 지시문을 사용 하면 코드 섹션 축소 및 숨기기 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="f0473-103">The `#Region` directive enables you to collapse and hide sections of code in [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] files.</span></span> <span data-ttu-id="f0473-104">`#Region` 지시문을 사용 하면 사용 하는 경우 축소 하거나 확장할 수 있는 코드 블록을 지정할 수는 [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] 코드 편집기입니다.</span><span class="sxs-lookup"><span data-stu-id="f0473-104">The `#Region` directive lets you specify a block of code that you can expand or collapse when using the [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] code editor.</span></span> <span data-ttu-id="f0473-105">코드를 선택적으로 숨길 수에 파일 사용 하면 관리 가능 하 고 쉽게 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0473-105">The ability to hide code selectively makes your files more manageable and easier to read.</span></span> <span data-ttu-id="f0473-106">자세한 내용은 참조 [개요](https://docs.microsoft.com/visualstudio/ide/outlining)합니다.</span><span class="sxs-lookup"><span data-stu-id="f0473-106">For more information, see [Outlining](https://docs.microsoft.com/visualstudio/ide/outlining).</span></span>  
  
 <span data-ttu-id="f0473-107">`#Region`지시문을 코드 블록의 의미와 같은 지원 `#If...#End If`합니다.</span><span class="sxs-lookup"><span data-stu-id="f0473-107">`#Region` directives support code block semantics such as `#If...#End If`.</span></span> <span data-ttu-id="f0473-108">즉, 없습니다 한 블록에서 시작과 종료 다른; 시작 및 종료 같은 블록에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0473-108">This means they cannot begin in one block and end in another; the start and end must be in the same block.</span></span> <span data-ttu-id="f0473-109">`#Region`지시문 함수 내에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f0473-109">`#Region` directives are not supported within functions.</span></span>  
  
### <a name="to-collapse-and-hide-a-section-of-code"></a><span data-ttu-id="f0473-110">축소 하 고 코드의 섹션을 숨기려면</span><span class="sxs-lookup"><span data-stu-id="f0473-110">To collapse and hide a section of code</span></span>  
  
-   <span data-ttu-id="f0473-111">섹션 사이 코드의 배치는 `#Region` 및 `#End Region` 다음 예제와 같이 문:</span><span class="sxs-lookup"><span data-stu-id="f0473-111">Place the section of code between the `#Region` and `#End Region` statements, as in the following example:</span></span>  
  
     <span data-ttu-id="f0473-112">[!code-vb[VbVbalrConditionalComp #&6;](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/how-to-collapse-and-hide-sections-of-code_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="f0473-112">[!code-vb[VbVbalrConditionalComp#6](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/how-to-collapse-and-hide-sections-of-code_1.vb)]</span></span>  
  
     <span data-ttu-id="f0473-113">`#Region` 블록 코드 파일에 여러 번 사용할 수 있습니다; 따라서 사용자 고유의 블록 프로시저 및를 차례로 축소할 수 있는 클래스를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0473-113">The `#Region` block can be used multiple times in a code file; thus, users can define their own blocks of procedures and classes that can, in turn, be collapsed.</span></span> <span data-ttu-id="f0473-114">`#Region`블록은 다른 내에서 중첩 될 수도 있습니다 `#Region` 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="f0473-114">`#Region` blocks can also be nested within other `#Region` blocks.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f0473-115">코드를 숨기 더라도 컴파일에서 하지 않는 및 영향을 주지 않습니다 `#If...#End If` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="f0473-115">Hiding code does not prevent it from being compiled and does not affect `#If...#End If` statements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0473-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f0473-116">See Also</span></span>  
 <span data-ttu-id="f0473-117">[조건부 컴파일](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md) </span><span class="sxs-lookup"><span data-stu-id="f0473-117">[Conditional Compilation](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md) </span></span>  
<span data-ttu-id="f0473-118"> [#Region 지시문](../../../visual-basic/language-reference/directives/region-directive.md) </span><span class="sxs-lookup"><span data-stu-id="f0473-118"> [#Region Directive](../../../visual-basic/language-reference/directives/region-directive.md) </span></span>  
<span data-ttu-id="f0473-119"> [#If... ... #Else 지시문](../../../visual-basic/language-reference/directives/if-then-else-directives.md) </span><span class="sxs-lookup"><span data-stu-id="f0473-119"> [#If...Then...#Else Directives](../../../visual-basic/language-reference/directives/if-then-else-directives.md) </span></span>  
<span data-ttu-id="f0473-120"> [개요](https://docs.microsoft.com/visualstudio/ide/outlining)</span><span class="sxs-lookup"><span data-stu-id="f0473-120"> [Outlining](https://docs.microsoft.com/visualstudio/ide/outlining)</span></span>
