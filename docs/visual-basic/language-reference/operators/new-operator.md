---
title: "New 연산자(Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.new
- vb.NewConstraint
helpviewer_keywords:
- constraints, Visual Basic generic types
- generics [Visual Basic], constraints
- constraints, New keyword [Visual Basic]
- New constraint
- New keyword [Visual Basic]
ms.assetid: d7d566d7-fe0e-4336-91f7-641a542de4d0
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 74f0352379e861ad135ea23d31ea07d638f9e6c1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="new-operator-visual-basic"></a><span data-ttu-id="e0591-102">New 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e0591-102">New Operator (Visual Basic)</span></span>
<span data-ttu-id="e0591-103">소개는 `New` 절을 새 개체 인스턴스를 만드는 형식 매개 변수에 생성자 제약 조건을 지정 하거나 식별 한 `Sub` 클래스 생성자와 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="e0591-103">Introduces a `New` clause to create a new object instance, specifies a constructor constraint on a type parameter, or identifies a `Sub` procedure as a class constructor.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e0591-104">설명</span><span class="sxs-lookup"><span data-stu-id="e0591-104">Remarks</span></span>  
 <span data-ttu-id="e0591-105">선언 또는 대입문에 `New` 절은 인스턴스를 만들 수 있는 정의 된 클래스를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0591-105">In a declaration or assignment statement, a `New` clause must specify a defined class from which the instance can be created.</span></span> <span data-ttu-id="e0591-106">이 클래스에서 호출 코드에 액세스할 수 있는 하나 이상의 생성자를 노출 해야 한다는 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0591-106">This means that the class must expose one or more constructors that the calling code can access.</span></span>  
  
 <span data-ttu-id="e0591-107">사용할 수는 `New` 선언 문 또는 대입문 절.</span><span class="sxs-lookup"><span data-stu-id="e0591-107">You can use a `New` clause in a declaration statement or an assignment statement.</span></span> <span data-ttu-id="e0591-108">문이 실행 될 때 제공한 인수를 전달 하며, 지정된 된 클래스의 적절 한 생성자를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0591-108">When the statement runs, it calls the appropriate constructor of the specified class, passing any arguments you have supplied.</span></span> <span data-ttu-id="e0591-109">다음 예제에서는이의 인스턴스를 만들어 한 `Customer` 두 명의 생성자가 클래스, 매개 변수를 사용 하 고 다른 하나는 문자열 매개 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0591-109">The following example demonstrates this by creating instances of a `Customer` class that has two constructors, one that takes no parameters and one that takes a string parameter.</span></span>  
  
 [!code-vb[VbVbalrKeywords#11](../../../visual-basic/language-reference/codesnippet/VisualBasic/new-operator_1.vb)]  
  
 <span data-ttu-id="e0591-110">배열은 클래스, 이므로 `New` 다음 예제에 나와 있는 것 처럼 새 배열 인스턴스를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0591-110">Since arrays are classes, `New` can create a new array instance, as shown in the following examples.</span></span>  
  
 [!code-vb[VbVbalrKeywords#12](../../../visual-basic/language-reference/codesnippet/VisualBasic/new-operator_2.vb)]  
  
 <span data-ttu-id="e0591-111">공용 언어 런타임 (CLR)를 throw 한 <xref:System.OutOfMemoryException> 메모리가 부족 한 새 인스턴스를 만드는 경우 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0591-111">The common language runtime (CLR) throws an <xref:System.OutOfMemoryException> error if there is insufficient memory to create the new instance.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e0591-112">`New` 키워드는 또한 형식 매개 변수 목록에 지정 된 형식 액세스 가능한 매개 변수가 없는 생성자를 노출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0591-112">The `New` keyword is also used in type parameter lists to specify that the supplied type must expose an accessible parameterless constructor.</span></span> <span data-ttu-id="e0591-113">형식 매개 변수 및 제약 조건에 대 한 자세한 내용은 참조 [유형 목록](../../../visual-basic/language-reference/statements/type-list.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e0591-113">For more information about type parameters and constraints, see [Type List](../../../visual-basic/language-reference/statements/type-list.md).</span></span>  
  
 <span data-ttu-id="e0591-114">생성자를 클래스에 대 한 프로시저를 만들려면 설정의 이름을 `Sub` 프로시저에는 `New` 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="e0591-114">To create a constructor procedure for a class, set the name of a `Sub` procedure to the `New` keyword.</span></span> <span data-ttu-id="e0591-115">자세한 내용은 참조 [개체 수명: 개체가 만들어지고 소멸 되는 하는 방법을](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e0591-115">For more information, see [Object Lifetime: How Objects Are Created and Destroyed](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).</span></span>  
  
 <span data-ttu-id="e0591-116">`New` 키워드는 다음 컨텍스트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0591-116">The `New` keyword can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="e0591-117">Dim 문</span><span class="sxs-lookup"><span data-stu-id="e0591-117">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="e0591-118">Of</span><span class="sxs-lookup"><span data-stu-id="e0591-118">Of</span></span>](../../../visual-basic/language-reference/statements/of-clause.md)  
  
 [<span data-ttu-id="e0591-119">Sub 문</span><span class="sxs-lookup"><span data-stu-id="e0591-119">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="e0591-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e0591-120">See Also</span></span>  
 <xref:System.OutOfMemoryException>  
 [<span data-ttu-id="e0591-121">키워드</span><span class="sxs-lookup"><span data-stu-id="e0591-121">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)  
 [<span data-ttu-id="e0591-122">형식 목록</span><span class="sxs-lookup"><span data-stu-id="e0591-122">Type List</span></span>](../../../visual-basic/language-reference/statements/type-list.md)  
 [<span data-ttu-id="e0591-123">Visual Basic의 제네릭 형식</span><span class="sxs-lookup"><span data-stu-id="e0591-123">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [<span data-ttu-id="e0591-124">개체 수명: 개체가 만들어지고 제거되는 방법</span><span class="sxs-lookup"><span data-stu-id="e0591-124">Object Lifetime: How Objects Are Created and Destroyed</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
