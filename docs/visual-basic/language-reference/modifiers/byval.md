---
title: ByVal(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.ByVal
- ByVal
helpviewer_keywords:
- ByVal keyword [Visual Basic], contexts
- ByVal keyword [Visual Basic]
ms.assetid: 1eaf4e58-b305-4785-9e3d-e416b9c75598
ms.openlocfilehash: 076289ff303dce58f036d6c7cb1505b151da19f6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33602985"
---
# <a name="byval-visual-basic"></a><span data-ttu-id="c9854-102">ByVal(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c9854-102">ByVal (Visual Basic)</span></span>
<span data-ttu-id="c9854-103">호출된 된 프로시저 또는 속성 호출 코드의 기반이 되는 변수 값을 변경할 수 없는 방식으로 인수가 전달 되도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9854-103">Specifies that an argument is passed in such a way that the called procedure or property cannot change the value of a variable underlying the argument in the calling code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c9854-104">설명</span><span class="sxs-lookup"><span data-stu-id="c9854-104">Remarks</span></span>  
 <span data-ttu-id="c9854-105">`ByVal` 한정자는 다음 컨텍스트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9854-105">The `ByVal` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="c9854-106">Declare 문</span><span class="sxs-lookup"><span data-stu-id="c9854-106">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="c9854-107">Function 문</span><span class="sxs-lookup"><span data-stu-id="c9854-107">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="c9854-108">Operator 문</span><span class="sxs-lookup"><span data-stu-id="c9854-108">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [<span data-ttu-id="c9854-109">Property 문</span><span class="sxs-lookup"><span data-stu-id="c9854-109">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="c9854-110">Sub 문</span><span class="sxs-lookup"><span data-stu-id="c9854-110">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="example"></a><span data-ttu-id="c9854-111">예제</span><span class="sxs-lookup"><span data-stu-id="c9854-111">Example</span></span>  
 <span data-ttu-id="c9854-112">다음 예제에서는 `ByVal` 매개 변수는 참조 형식 인수를 가진 메커니즘을 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9854-112">The following example demonstrates the use of the `ByVal` parameter passing mechanism with a reference type argument.</span></span> <span data-ttu-id="c9854-113">예에서 인수는 `c1`, 클래스의 인스턴스 `Class1`합니다.</span><span class="sxs-lookup"><span data-stu-id="c9854-113">In the example, the argument is `c1`, an instance of class `Class1`.</span></span> <span data-ttu-id="c9854-114">`ByVal` 절차의 코드는 참조 인수를 내부 값을 변경 하는 것을 금지 `c1`, 액세스할 수 있는 필드와 속성을 보호 되지 않습니다 되지만 `c1`합니다.</span><span class="sxs-lookup"><span data-stu-id="c9854-114">`ByVal` prevents the code in the procedures from changing the underlying value of the reference argument, `c1`, but does not protect the accessible fields and properties of `c1`.</span></span>  
  
 [!code-vb[VbVbalrKeywords#10](../../../visual-basic/language-reference/codesnippet/VisualBasic/byval_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="c9854-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c9854-115">See Also</span></span>  
 [<span data-ttu-id="c9854-116">키워드</span><span class="sxs-lookup"><span data-stu-id="c9854-116">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)  
 [<span data-ttu-id="c9854-117">값 또는 참조로 인수 전달</span><span class="sxs-lookup"><span data-stu-id="c9854-117">Passing Arguments by Value and by Reference</span></span>](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
