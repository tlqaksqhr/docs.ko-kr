---
title: 코드 주석(Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Uncomment button
- REM statement [Visual Basic]
- comments [Visual Basic], in code
- comments [Visual Basic], Visual Basic code
- Comment button
- buttons [Visual Basic], Uncomment
- buttons [Visual Basic], Comment
- code comments [Visual Basic], Visual Basic
- Visual Basic code, comments
- comments
- code comments
ms.assetid: 90136fba-22eb-49f9-ba81-63db629b4a47
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9cd3277ea61ac9b46d8d20028bd100811988f611
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="comments-in-code-visual-basic"></a><span data-ttu-id="7d0e3-102">코드 주석(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7d0e3-102">Comments in Code (Visual Basic)</span></span>
<span data-ttu-id="7d0e3-103">코드 예제를 읽다 보면 종종 주석 기호(`'`)를 보게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d0e3-103">As you read the code examples, you often encounter the comment symbol (`'`).</span></span> <span data-ttu-id="7d0e3-104">이 기호는 Visual Basic 컴파일러가, 다음의 텍스트를 무시 또는 *주석*합니다.</span><span class="sxs-lookup"><span data-stu-id="7d0e3-104">This symbol tells the Visual Basic compiler to ignore the text following it, or the *comment*.</span></span> <span data-ttu-id="7d0e3-105">주석이란 해당 코드를 읽을 사람의 편의를 위해 코드에 추가되는 간단한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="7d0e3-105">Comments are brief explanatory notes added to code for the benefit of those reading it.</span></span>  
  
 <span data-ttu-id="7d0e3-106">모든 프로시저를 시작할 때 프로시저의 기능적 특징, 즉 해당 프로시저가 수행하는 작업에 대한 간단한 주석을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="7d0e3-106">It is good programming practice to begin all procedures with a brief comment describing the functional characteristics of the procedure (what it does).</span></span> <span data-ttu-id="7d0e3-107">이는 사용자 자신이나 코드를 보게 될 다른 사용자를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7d0e3-107">This is for your own benefit and the benefit of anyone else who examines the code.</span></span> <span data-ttu-id="7d0e3-108">프로시저의 구현 방식 등 구현에 대한 자세한 정보는 기능적 특징을 설명하는 주석과 분리되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d0e3-108">You should separate the implementation details (how the procedure does it) from comments that describe the functional characteristics.</span></span> <span data-ttu-id="7d0e3-109">이 정보를 설명하는 부분에 포함시킨 경우에는 함수를 업데이트할 때 이 정보도 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d0e3-109">When you include implementation details in the description, remember to update them when you update the function.</span></span>  
  
 <span data-ttu-id="7d0e3-110">주석은 문과 같은 줄에서 문 다음에 나올 수도 있고 한 줄을 차지할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d0e3-110">Comments can follow a statement on the same line, or occupy an entire line.</span></span> <span data-ttu-id="7d0e3-111">다음 코드에서는 이 두 가지 경우를 모두 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7d0e3-111">Both are illustrated in the following code.</span></span>  
  
 [!code-vb[VbVbcnConventions#16](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/comments-in-code_1.vb)]  
  
 <span data-ttu-id="7d0e3-112">주석에 둘 이상의 줄이 필요하면 다음 예제와 같이 각 줄에 주석 기호를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7d0e3-112">If your comment requires more than one line, use the comment symbol on each line, as the following example illustrates.</span></span>  
  
 [!code-vb[VbVbcnConventions#17](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/comments-in-code_2.vb)]  
  
## <a name="commenting-guidelines"></a><span data-ttu-id="7d0e3-113">주석 지침</span><span class="sxs-lookup"><span data-stu-id="7d0e3-113">Commenting Guidelines</span></span>  
 <span data-ttu-id="7d0e3-114">다음 표에서는 코드 부분의 앞에 올 수 있는 주석의 종류에 대한 일반적인 지침을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7d0e3-114">The following table provides general guidelines for what types of comments can precede a section of code.</span></span> <span data-ttu-id="7d0e3-115">이러한 권장 사항이 며 Visual Basic에서 메모 추가 대 한 규칙을 적용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7d0e3-115">These are suggestions; Visual Basic does not enforce rules for adding comments.</span></span> <span data-ttu-id="7d0e3-116">사용자 자신이나 해당 코드를 읽을 다른 모든 사용자에게 적합하도록 주석을 쓰면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d0e3-116">Write what works best, both for you and for anyone else who reads your code.</span></span>  
  
|||  
|---|---|  
|<span data-ttu-id="7d0e3-117">주석 형식</span><span class="sxs-lookup"><span data-stu-id="7d0e3-117">Comment type</span></span>|<span data-ttu-id="7d0e3-118">주석 설명</span><span class="sxs-lookup"><span data-stu-id="7d0e3-118">Comment description</span></span>|  
|<span data-ttu-id="7d0e3-119">용도</span><span class="sxs-lookup"><span data-stu-id="7d0e3-119">Purpose</span></span>|<span data-ttu-id="7d0e3-120">프로시저의 작업 수행 방식이 아니라 해당 프로시저에서 수행하는 작업에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7d0e3-120">Describes what the procedure does (not how it does it)</span></span>|  
|<span data-ttu-id="7d0e3-121">Assumptions</span><span class="sxs-lookup"><span data-stu-id="7d0e3-121">Assumptions</span></span>|<span data-ttu-id="7d0e3-122">프로시저에서 액세스하는 외부 변수, 컨트롤, 열린 파일 또는 기타 요소를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="7d0e3-122">Lists each external variable, control, open file, or other element accessed by the procedure</span></span>|  
|<span data-ttu-id="7d0e3-123">효과</span><span class="sxs-lookup"><span data-stu-id="7d0e3-123">Effects</span></span>|<span data-ttu-id="7d0e3-124">영향을 받은 외부 변수, 컨트롤 또는 파일을 나열하고, 분명하지 않은 경우에는 그 효과를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="7d0e3-124">Lists each affected external variable, control, or file, and the effect it has (only if it is not obvious)</span></span>|  
|<span data-ttu-id="7d0e3-125">Inputs</span><span class="sxs-lookup"><span data-stu-id="7d0e3-125">Inputs</span></span>|<span data-ttu-id="7d0e3-126">인수의 용도를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7d0e3-126">Specifies the purpose of the argument</span></span>|  
|<span data-ttu-id="7d0e3-127">반환 값</span><span class="sxs-lookup"><span data-stu-id="7d0e3-127">Returns</span></span>|<span data-ttu-id="7d0e3-128">프로시저에 의해 반환된 값에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7d0e3-128">Explains the values returned by the procedure</span></span>|  
  
 <span data-ttu-id="7d0e3-129">다음은 주의해야 할 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="7d0e3-129">Remember the following points:</span></span>  
  
-   <span data-ttu-id="7d0e3-130">중요한 모든 변수 선언에는 선언되는 변수의 용도에 대해 설명하는 주석이 앞에 와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d0e3-130">Every important variable declaration should be preceded by a comment describing the use of the variable being declared.</span></span>  
  
-   <span data-ttu-id="7d0e3-131">변수, 컨트롤 및 프로시저의 이름은 쉽게 알 수 있는 이름으로 지정하며, 복잡한 구현에 대해 자세히 설명하는 경우에만 주석을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7d0e3-131">Variables, controls, and procedures should be named clearly enough that commenting is needed only for complex implementation details.</span></span>  
  
-   <span data-ttu-id="7d0e3-132">줄 연속 시퀀스를 사용한 후에는 같은 줄에 주석을 쓸 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7d0e3-132">Comments cannot follow a line-continuation sequence on the same line.</span></span>  
  
 <span data-ttu-id="7d0e3-133">추가 하거나 하나 이상의 코드 줄을 선택 하 고 선택 하 여 코드 블록에 대 한 주석 기호를 제거할 수 있습니다는 **주석** (![VisualBasicWinAppCodeEditorCommentButton](../../../visual-basic/programming-guide/program-structure/media/vacommentbutton.gif "vaCommentButton ")) 및 **주석 제거** (![VisualStudioWinAppProjectUncommentButton](../../../visual-basic/programming-guide/program-structure/media/vauncommentbutton.gif "vaUncommentButton"))에 단추는 **편집**  도구 모음입니다.</span><span class="sxs-lookup"><span data-stu-id="7d0e3-133">You can add or remove comment symbols for a block of code by selecting one or more lines of code and choosing the **Comment** (![VisualBasicWinAppCodeEditorCommentButton](../../../visual-basic/programming-guide/program-structure/media/vacommentbutton.gif "vaCommentButton")) and **Uncomment** (![VisualStudioWinAppProjectUncommentButton](../../../visual-basic/programming-guide/program-structure/media/vauncommentbutton.gif "vaUncommentButton")) buttons on the **Edit** toolbar.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7d0e3-134">`REM` 키워드로 텍스트를 시작하여 코드에 주석을 추가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d0e3-134">You can also add comments to your code by preceding the text with the `REM` keyword.</span></span> <span data-ttu-id="7d0e3-135">그러나는 `'` 기호 및 **주석**/**주석 제거** 단추는 쉽게 사용 하 고 필요한 공간 및 메모리도 절약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d0e3-135">However, the `'` symbol and the **Comment**/**Uncomment** buttons are easier to use and require less space and memory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d0e3-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7d0e3-136">See Also</span></span>  
 [<span data-ttu-id="7d0e3-137">XML 주석 사용 하 여 코드 문서화</span><span class="sxs-lookup"><span data-stu-id="7d0e3-137">Documenting Your Code With XML Comments</span></span>](http://msdn.microsoft.com/magazine/dd722812.aspx)  
 [<span data-ttu-id="7d0e3-138">방법: XML 문서 만들기</span><span class="sxs-lookup"><span data-stu-id="7d0e3-138">How to: Create XML Documentation</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)  
 [<span data-ttu-id="7d0e3-139">XML 주석 태그</span><span class="sxs-lookup"><span data-stu-id="7d0e3-139">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)  
 [<span data-ttu-id="7d0e3-140">프로그램 구조 및 코드 규칙</span><span class="sxs-lookup"><span data-stu-id="7d0e3-140">Program Structure and Code Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)  
 [<span data-ttu-id="7d0e3-141">REM 문</span><span class="sxs-lookup"><span data-stu-id="7d0e3-141">REM Statement</span></span>](../../../visual-basic/language-reference/statements/rem-statement.md)
