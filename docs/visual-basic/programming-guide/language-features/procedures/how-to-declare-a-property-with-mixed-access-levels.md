---
title: '방법: 액세스 수준이 혼합된 속성 선언(Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- access levels [Visual Basic], properties
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- mixed access levels
- Visual Basic code, properties
- properties [Visual Basic], access levels
- Property statement [Visual Basic], declaring mixed access levels
ms.assetid: fdbb2d97-279a-4956-b26c-cbdfbc34915a
ms.openlocfilehash: 8d25086fe6f8b5f5300006466ef49782cb065edf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33651413"
---
# <a name="how-to-declare-a-property-with-mixed-access-levels-visual-basic"></a><span data-ttu-id="f0832-102">방법: 액세스 수준이 혼합된 속성 선언(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f0832-102">How to: Declare a Property with Mixed Access Levels (Visual Basic)</span></span>
<span data-ttu-id="f0832-103">원하는 경우는 `Get` 및 `Set` 액세스 수준이 서로 속성에 프로시저에서 더 수준을 사용할 수 있습니다는 `Property` 문과 더 제한적인 수준 중 하나에 `Get` 또는 `Set` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="f0832-103">If you want the `Get` and `Set` procedures on a property to have different access levels, you can use the more permissive level in the `Property` statement and the more restrictive level in either the `Get` or `Set` statement.</span></span> <span data-ttu-id="f0832-104">일부 속성의 값을 가져올 수 있게 되기를 코드와 값을 변경 하려면 코드의 다른 구성 요소 속성에 액세스 수준이 혼합된를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0832-104">You use mixed access levels on a property when you want certain parts of the code to be able to get the property's value, and certain other parts of the code to be able to change the value.</span></span>  
  
 <span data-ttu-id="f0832-105">액세스 수준에 대 한 자세한 내용은 참조 하십시오. [액세스 수준을 Visual Basic의](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f0832-105">For more information on access levels, see [Access levels in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
### <a name="to-declare-a-property-with-mixed-access-levels"></a><span data-ttu-id="f0832-106">액세스 수준이 혼합된 된 속성을 선언 하려면</span><span class="sxs-lookup"><span data-stu-id="f0832-106">To declare a property with mixed access levels</span></span>  
  
1.  <span data-ttu-id="f0832-107">일반적인 방법으로 속성을 선언 하 고 덜 제한적인 액세스 수준을 지정할 (같은 `Public`)에 `Property` 문.</span><span class="sxs-lookup"><span data-stu-id="f0832-107">Declare the property in the normal way, and specify the less restrictive access level (such as `Public`) in the `Property` statement.</span></span>  
  
2.  <span data-ttu-id="f0832-108">선언 중 하나는 `Get` 또는 `Set` 더 제한적인 액세스 수준을 지정 하는 프로시저 (같은 `Friend`).</span><span class="sxs-lookup"><span data-stu-id="f0832-108">Declare either the `Get` or the `Set` procedure specifying the more restrictive access level (such as `Friend`).</span></span>  
  
3.  <span data-ttu-id="f0832-109">다른 속성 프로시저에 대 한 액세스 수준을 지정 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="f0832-109">Do not specify an access level on the other property procedure.</span></span> <span data-ttu-id="f0832-110">액세스 수준에 선언 된 것으로 가정은 `Property` 문.</span><span class="sxs-lookup"><span data-stu-id="f0832-110">It assumes the access level declared in the `Property` statement.</span></span> <span data-ttu-id="f0832-111">속성 프로시저 중 하나 에서만 액세스를 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0832-111">You can restrict access on only one of the property procedures.</span></span>  
  
     [!code-vb[VbVbcnProcedures#10](./codesnippet/VisualBasic/how-to-declare-a-property-with-mixed-access-levels_1.vb)]  
  
     <span data-ttu-id="f0832-112">앞의 예제에는 `Get` 프로시저에 동일한 `Protected` 자체를 속성으로 액세스 하는 동안는 `Set` 프로시저에 `Private` 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0832-112">In the preceding example, the `Get` procedure has the same `Protected` access as the property itself, while the `Set` procedure has `Private` access.</span></span> <span data-ttu-id="f0832-113">클래스에서 파생 `employee` 읽을 수는 `salary` 값만 `employee` 클래스에서 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0832-113">A class derived from `employee` can read the `salary` value, but only the `employee` class can set it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0832-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f0832-114">See Also</span></span>  
 [<span data-ttu-id="f0832-115">절차</span><span class="sxs-lookup"><span data-stu-id="f0832-115">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="f0832-116">속성 프로시저</span><span class="sxs-lookup"><span data-stu-id="f0832-116">Property Procedures</span></span>](./property-procedures.md)  
 [<span data-ttu-id="f0832-117">프로시저 매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="f0832-117">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="f0832-118">Property 문</span><span class="sxs-lookup"><span data-stu-id="f0832-118">Property Statement</span></span>](../../../../visual-basic/language-reference/statements/property-statement.md)  
 [<span data-ttu-id="f0832-119">Visual Basic에서 속성과 변수의 차이점</span><span class="sxs-lookup"><span data-stu-id="f0832-119">Differences Between Properties and Variables in Visual Basic</span></span>](./differences-between-properties-and-variables.md)  
 [<span data-ttu-id="f0832-120">방법: 속성 만들기</span><span class="sxs-lookup"><span data-stu-id="f0832-120">How to: Create a Property</span></span>](./how-to-create-a-property.md)  
 [<span data-ttu-id="f0832-121">방법: 속성 프로시저 호출</span><span class="sxs-lookup"><span data-stu-id="f0832-121">How to: Call a Property Procedure</span></span>](./how-to-call-a-property-procedure.md)  
 [<span data-ttu-id="f0832-122">방법: 선언 하 고 Visual Basic의 기본 속성 호출</span><span class="sxs-lookup"><span data-stu-id="f0832-122">How to: Declare and Call a Default Property in Visual Basic</span></span>](./how-to-declare-and-call-a-default-property.md)  
 [<span data-ttu-id="f0832-123">방법: 속성 값 입력</span><span class="sxs-lookup"><span data-stu-id="f0832-123">How to: Put a Value in a Property</span></span>](./how-to-put-a-value-in-a-property.md)  
 [<span data-ttu-id="f0832-124">방법: 속성에서 값 가져오기</span><span class="sxs-lookup"><span data-stu-id="f0832-124">How to: Get a Value from a Property</span></span>](./how-to-get-a-value-from-a-property.md)
