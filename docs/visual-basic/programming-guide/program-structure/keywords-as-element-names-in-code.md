---
title: 코드에서 요소 이름으로 사용되는 키워드(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, naming conventions
- keywords [Visual Basic], in code
- name conflicts [Visual Basic]
- element names [Visual Basic], in code
ms.assetid: 2e4e8e02-23f7-49b9-a1c8-2b0402b6b525
ms.openlocfilehash: 53c3172e8518115d001c23be2430fbc87ae1b60f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33652580"
---
# <a name="keywords-as-element-names-in-code-visual-basic"></a><span data-ttu-id="b6f9e-102">코드에서 요소 이름으로 사용되는 키워드(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b6f9e-102">Keywords as Element Names in Code (Visual Basic)</span></span>
<span data-ttu-id="b6f9e-103">모든 프로그램 요소-변수, 클래스 또는 멤버와 같은-제한 된 키워드와 동일한 이름을 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6f9e-103">Any program element — such as a variable, class, or member — can have the same name as a restricted keyword.</span></span> <span data-ttu-id="b6f9e-104">예를 들어 라는 변수를 만들 수 있습니다 `Loop`합니다.</span><span class="sxs-lookup"><span data-stu-id="b6f9e-104">For example, you can create a variable named `Loop`.</span></span> <span data-ttu-id="b6f9e-105">그러나 구별 참조 하려면-제한 된와 동일한 이름이 있는 `Loop` 키워드-앞에 정규화 문자열 하거나 대괄호로 묶어야 합니다 (`[ ]`) 다음 예제와 같이 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6f9e-105">However, to refer to your version of it — which has the same name as the restricted `Loop` keyword — you must either precede it with a full qualification string or enclose it in square brackets (`[ ]`), as the following example shows.</span></span>  
  
 [!code-vb[VbVbcnConventions#8](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/keywords-as-element-names-in-code_1.vb)]  
  
 <span data-ttu-id="b6f9e-106">이 중 하나를 수행 하지 않는 경우 Visual Basic은 내장 함수를 사용 한다고 가정 `Loop` 키워드와 다음 예제와 같이 오류를 발생 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="b6f9e-106">If you do not do either of these, then Visual Basic assumes use of the intrinsic `Loop` keyword and produces an error, as in the following example:</span></span>  
  
 `' The following statement causes a compiler error.`  
  
 `Loop.Visible = True`  
  
 <span data-ttu-id="b6f9e-107">폼과 컨트롤을 나타낼 때와 때 대괄호를 사용할 수 있습니다 변수를 선언 하거나 제한 된 키워드와 같은 이름의 프로시저를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6f9e-107">You can use square brackets when referring to forms and controls, and when declaring a variable or defining a procedure with the same name as a restricted keyword.</span></span> <span data-ttu-id="b6f9e-108">이름 한정 포함 대괄호를 하 고 따라서 코드에 오류가 발생 하 고 읽기 하기가 더 어려워지며를 잊기 쉬울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6f9e-108">It can be easy to forget to qualify names or include square brackets, and thus introduce errors into your code and make it harder to read.</span></span> <span data-ttu-id="b6f9e-109">이러한 이유로 프로그램 요소 이름으로 제한 된 키워드를 사용 하지는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b6f9e-109">For this reason, we recommend that you not use restricted keywords as the names of program elements.</span></span> <span data-ttu-id="b6f9e-110">그러나 이후 버전의 Visual Basic의 기존 폼 또는 컨트롤 이름 충돌 하는 새로운 키워드를 정의 다음 사용할 수 있습니다이 방법은 코드를 업데이트할 때 새 버전으로 작업 하도록.</span><span class="sxs-lookup"><span data-stu-id="b6f9e-110">However, if a future version of Visual Basic defines a new keyword that conflicts with an existing form or control name, then you can use this technique when updating your code to work with the new version.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b6f9e-111">또한 프로그램 다른 참조 된 어셈블리에서 제공 되는 요소 이름이 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6f9e-111">Your program also might include element names provided by other referenced assemblies.</span></span> <span data-ttu-id="b6f9e-112">이러한 이름은 제한 된 키워드와 충돌 하는 경우 대괄호로 묶으면 Visual Basic 정의 된 요소를 해석할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6f9e-112">If these names conflict with restricted keywords, then placing square brackets around them causes Visual Basic to interpret them as your defined elements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6f9e-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b6f9e-113">See Also</span></span>  
 [<span data-ttu-id="b6f9e-114">Visual Basic 명명 규칙</span><span class="sxs-lookup"><span data-stu-id="b6f9e-114">Visual Basic Naming Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)  
 [<span data-ttu-id="b6f9e-115">프로그램 구조 및 코드 규칙</span><span class="sxs-lookup"><span data-stu-id="b6f9e-115">Program Structure and Code Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)  
 [<span data-ttu-id="b6f9e-116">키워드</span><span class="sxs-lookup"><span data-stu-id="b6f9e-116">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
