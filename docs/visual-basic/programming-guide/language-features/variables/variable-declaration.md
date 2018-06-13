---
title: Visual Basic의 변수 선언
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], declaring
- member variables [Visual Basic], declarations
- Dim statement [Visual Basic], variable declaration
- declaring variables [Visual Basic]
- variables [Visual Basic], scope
- variables [Visual Basic], data types
- data types [Visual Basic], variable declarations
- lifetime [Visual Basic], variables
- variables [Visual Basic], lifetime
- access levels [Visual Basic], variables
- scope [Visual Basic], declaration statements
- variables [Visual Basic], access level
- local variables [Visual Basic], declarations
- scope [Visual Basic], variables
ms.assetid: d8f10226-92b1-480f-9f53-df377b2d7e15
ms.openlocfilehash: 6890ddfd8b463cd731ab3d8f39565b50a31a1192
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33656141"
---
# <a name="variable-declaration-in-visual-basic"></a><span data-ttu-id="32271-102">Visual Basic의 변수 선언</span><span class="sxs-lookup"><span data-stu-id="32271-102">Variable Declaration in Visual Basic</span></span>
<span data-ttu-id="32271-103">이름 및 특성을 지정 하려면 변수를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="32271-103">You declare a variable to specify its name and characteristics.</span></span> <span data-ttu-id="32271-104">변수에 대 한 선언문이 [Dim 문](../../../../visual-basic/language-reference/statements/dim-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="32271-104">The declaration statement for variables is the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md).</span></span> <span data-ttu-id="32271-105">해당 위치 및 내용을 변수의 특성을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="32271-105">Its location and contents determine the variable's characteristics.</span></span>  
  
 <span data-ttu-id="32271-106">변수 명명 규칙 및 고려 사항에 대 한 참조 [선언 요소 이름](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="32271-106">For variable naming rules and considerations, see [Declared Element Names](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
## <a name="declaration-levels"></a><span data-ttu-id="32271-107">선언 수준</span><span class="sxs-lookup"><span data-stu-id="32271-107">Declaration Levels</span></span>  
  
### <a name="local-and-member-variables"></a><span data-ttu-id="32271-108">로컬 및 멤버 변수</span><span class="sxs-lookup"><span data-stu-id="32271-108">Local and Member Variables</span></span>  
 <span data-ttu-id="32271-109">A *지역 변수* 은 프로시저 내에서 선언입니다.</span><span class="sxs-lookup"><span data-stu-id="32271-109">A *local variable* is one that is declared within a procedure.</span></span> <span data-ttu-id="32271-110">A *멤버 변수* Visual Basic 형식의 멤버는 해당 클래스, 구조체 또는 모듈의 내부 프로시저 내부가 아니라 내 클래스, 구조체 또는 모듈의 모듈 수준에서 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="32271-110">A *member variable* is a member of a Visual Basic type; it is declared at module level, inside a class, structure, or module, but not within any procedure internal to that class, structure, or module.</span></span>  
  
### <a name="shared-and-instance-variables"></a><span data-ttu-id="32271-111">공유 및 인스턴스 변수</span><span class="sxs-lookup"><span data-stu-id="32271-111">Shared and Instance Variables</span></span>  
 <span data-ttu-id="32271-112">클래스 또는 구조체에서 멤버 변수 범주의 공유 되는지 여부에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="32271-112">In a class or structure, the category of a member variable depends on whether or not it is shared.</span></span> <span data-ttu-id="32271-113">으로 선언 된 경우는 [Shared](../../../../visual-basic/language-reference/modifiers/shared.md) 키워드를 *공유 변수*, 클래스 또는 구조체의 모든 인스턴스에서 공유 하는 단일 복사본에 존재 합니다.</span><span class="sxs-lookup"><span data-stu-id="32271-113">If it is declared with the [Shared](../../../../visual-basic/language-reference/modifiers/shared.md) keyword, it is a *shared variable*, and it exists in a single copy shared among all instances of the class or structure.</span></span>  
  
 <span data-ttu-id="32271-114">그렇지 않으면이 생성자는 *인스턴스 변수*, 클래스 또는 구조체의 각 인스턴스에 대해 별도 사본을 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="32271-114">Otherwise it is an *instance variable*, and a separate copy of it is created for each instance of the class or structure.</span></span> <span data-ttu-id="32271-115">인스턴스 변수 주어진 복사본이 작성 된 구조체 또는 클래스의 인스턴스에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32271-115">A given copy of an instance variable is available only to the instance of the class or structure in which it was created.</span></span> <span data-ttu-id="32271-116">것은 클래스 또는 구조체의 다른 인스턴스에 인스턴스 변수 사본을 무관 합니다.</span><span class="sxs-lookup"><span data-stu-id="32271-116">It is independent of a copy of the instance variable in any other instance of the class or structure.</span></span>  
  
## <a name="declaring-data-type"></a><span data-ttu-id="32271-117">데이터 형식 선언</span><span class="sxs-lookup"><span data-stu-id="32271-117">Declaring Data Type</span></span>  
 <span data-ttu-id="32271-118">[으로](../../../../visual-basic/language-reference/statements/as-clause.md) 선언문에 절을 사용 하면 데이터 형식 또는 선언 하는 변수의 개체 유형을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32271-118">The [As](../../../../visual-basic/language-reference/statements/as-clause.md) clause in the declaration statement allows you to define the data type or object type of the variable you are declaring.</span></span> <span data-ttu-id="32271-119">변수에 대 한 다음 유형 중 하나를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32271-119">You can specify any of the following types for a variable:</span></span>  
  
-   <span data-ttu-id="32271-120">등의 기본 데이터 형식 `Boolean`, `Long`, 또는 `Decimal`</span><span class="sxs-lookup"><span data-stu-id="32271-120">An elementary data type, such as `Boolean`, `Long`, or `Decimal`</span></span>  
  
-   <span data-ttu-id="32271-121">배열 또는 구조체와 같은 복합 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="32271-121">A composite data type, such as an array or structure</span></span>  
  
-   <span data-ttu-id="32271-122">개체 유형 또는 다른 응용 프로그램 또는 응용 프로그램에 정의 된 클래스</span><span class="sxs-lookup"><span data-stu-id="32271-122">An object type, or class, defined either in your application or in another application</span></span>  
  
-   <span data-ttu-id="32271-123">A [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 클래스 같은 <xref:System.Windows.Forms.Label> 또는 <xref:System.Windows.Forms.TextBox></span><span class="sxs-lookup"><span data-stu-id="32271-123">A [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] class, such as <xref:System.Windows.Forms.Label> or <xref:System.Windows.Forms.TextBox></span></span>  
  
-   <span data-ttu-id="32271-124">와 같은 인터페이스 형식 <xref:System.IComparable> 또는 <xref:System.IDisposable></span><span class="sxs-lookup"><span data-stu-id="32271-124">An interface type, such as <xref:System.IComparable> or <xref:System.IDisposable></span></span>  
  
 <span data-ttu-id="32271-125">데이터 형식을 반복 하지 않고 하나의 문에서 여러 변수를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32271-125">You can declare several variables in one statement without having to repeat the data type.</span></span> <span data-ttu-id="32271-126">다음 문에서 변수 `i`, `j`, 및 `k` 유형으로 선언 `Integer`, `l` 및 `m` 으로 `Long`, 및 `x` 및 `y` 로`Single`:</span><span class="sxs-lookup"><span data-stu-id="32271-126">In the following statements, the variables `i`, `j`, and `k` are declared as type `Integer`, `l` and `m` as `Long`, and `x` and `y` as `Single`:</span></span>  
  
```  
Dim i, j, k As Integer  
' All three variables in the preceding statement are declared as Integer.  
Dim l, m As Long, x, y As Single  
' In the preceding statement, l and m are Long, x and y are Single.  
```  
  
 <span data-ttu-id="32271-127">데이터 형식에 대 한 자세한 내용은 참조 하십시오. [데이터 형식](../../../../visual-basic/programming-guide/language-features/data-types/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="32271-127">For more information on data types, see [Data Types](../../../../visual-basic/programming-guide/language-features/data-types/index.md).</span></span> <span data-ttu-id="32271-128">개체에 대 한 자세한 내용은 참조 하십시오. [개체 및 클래스](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md) 및 [구성 요소를 사용한 프로그래밍](http://msdn.microsoft.com/library/d4d4fcb4-e0b8-46b3-b679-7ee0026eb9e3)합니다.</span><span class="sxs-lookup"><span data-stu-id="32271-128">For more information on objects, see [Objects and Classes](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md) and [Programming with Components](http://msdn.microsoft.com/library/d4d4fcb4-e0b8-46b3-b679-7ee0026eb9e3).</span></span>  
  
## <a name="local-type-inference"></a><span data-ttu-id="32271-129">지역 형식 유추</span><span class="sxs-lookup"><span data-stu-id="32271-129">Local Type Inference</span></span>  
 <span data-ttu-id="32271-130">*형식 유추* 없이 선언 된 지역 변수의 데이터 형식을 결정 하는 데 사용 되는 `As` 절.</span><span class="sxs-lookup"><span data-stu-id="32271-130">*Type inference* is used to determine the data types of local variables declared without an `As` clause.</span></span> <span data-ttu-id="32271-131">컴파일러는 초기화 식의 형식에서 변수의 형식을 유추합니다.</span><span class="sxs-lookup"><span data-stu-id="32271-131">The compiler infers the type of the variable from the type of the initialization expression.</span></span> <span data-ttu-id="32271-132">이렇게 하면 명시적으로 형식을 선언 하지 않고 변수를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32271-132">This enables you to declare variables without explicitly stating a type.</span></span> <span data-ttu-id="32271-133">다음 예제에서는 모두 `num1` 및 `num2` 는 정수로 강력한 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="32271-133">In the following example, both `num1` and `num2` are strongly typed as integers.</span></span>  
  
 [!code-vb[VbVbalrTypeInference#1](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/variable-declaration_1.vb)]  
  
 <span data-ttu-id="32271-134">지역 형식 유추를 사용 하려는 경우 `Option Infer` 로 설정 해야 `On`합니다.</span><span class="sxs-lookup"><span data-stu-id="32271-134">If you want to use local type inference, `Option Infer` must be set to `On`.</span></span> <span data-ttu-id="32271-135">자세한 내용은 [지역 형식 유추](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) 및 [Option Infer 문](../../../../visual-basic/language-reference/statements/option-infer-statement.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="32271-135">For more information, see [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) and [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md).</span></span>  
  
## <a name="characteristics-of-declared-variables"></a><span data-ttu-id="32271-136">선언 된 변수의 특징</span><span class="sxs-lookup"><span data-stu-id="32271-136">Characteristics of Declared Variables</span></span>  
 <span data-ttu-id="32271-137">*수명* 변수의 시간 동안 어떤 용도로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32271-137">The *lifetime* of a variable is the period of time during which it is available for use.</span></span> <span data-ttu-id="32271-138">일반적으로 변수가으로 (예: 프로시저 또는 클래스) 선언 하는 요소는 계속 남아 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32271-138">In general, a variable exists as long as the element that declares it (such as a procedure or class) continues to exist.</span></span> <span data-ttu-id="32271-139">변수는 포함 하는 요소의 수명 보다 더 오래 존재 하지 않아도, 선언에는 특별 한 어떤 작업도 수행할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="32271-139">If the variable does not need to continue existing beyond the lifetime of its containing element, you do not need to do anything special in the declaration.</span></span> <span data-ttu-id="32271-140">포함할 수 있습니다는 변수를 포함 하는 요소 보다 오래 존재 하는 경우는 `Static` 또는 `Shared` 키워드에 해당 `Dim` 문.</span><span class="sxs-lookup"><span data-stu-id="32271-140">If the variable needs to continue to exist longer than its containing element, you can include the `Static` or `Shared` keyword in its `Dim` statement.</span></span> <span data-ttu-id="32271-141">자세한 내용은 참조 [Visual Basic의 수명](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="32271-141">For more information, see [Lifetime in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md).</span></span>  
  
 <span data-ttu-id="32271-142">*범위* 변수 이름을 한정 하지 않고 변수를 참조할 수 있는 모든 코드의 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="32271-142">The *scope* of a variable is the set of all code that can refer to it without qualifying its name.</span></span> <span data-ttu-id="32271-143">변수의 범위는 선언 된 의해 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="32271-143">A variable's scope is determined by where it is declared.</span></span> <span data-ttu-id="32271-144">지정된 된 영역에 있는 코드를 해당 이름을 한정할 필요 없이 해당 영역에 정의 된 변수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32271-144">Code located in a given region can use the variables defined in that region without having to qualify their names.</span></span> <span data-ttu-id="32271-145">자세한 내용은 참조 [Visual Basic의 범위](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="32271-145">For more information, see [Scope in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md).</span></span>  
  
 <span data-ttu-id="32271-146">변수의 *액세스 수준* 에 액세스할 수 있는 권한을 가진 코드의 범위입니다.</span><span class="sxs-lookup"><span data-stu-id="32271-146">A variable's *access level* is the extent of code that has permission to access it.</span></span> <span data-ttu-id="32271-147">이 액세스 한정자에 의해 결정 됩니다 (같은 [공용](../../../../visual-basic/language-reference/modifiers/public.md) 또는 [개인](../../../../visual-basic/language-reference/modifiers/private.md))에서 사용 하는 `Dim` 문.</span><span class="sxs-lookup"><span data-stu-id="32271-147">This is determined by the access modifier (such as [Public](../../../../visual-basic/language-reference/modifiers/public.md) or [Private](../../../../visual-basic/language-reference/modifiers/private.md)) that you use in the `Dim` statement.</span></span> <span data-ttu-id="32271-148">자세한 내용은 참조 [액세스 수준을 Visual Basic의](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="32271-148">For more information, see [Access levels in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32271-149">참고 항목</span><span class="sxs-lookup"><span data-stu-id="32271-149">See Also</span></span>  
 [<span data-ttu-id="32271-150">방법: 새 변수 만들기</span><span class="sxs-lookup"><span data-stu-id="32271-150">How to: Create a New Variable</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-create-a-new-variable.md)  
 [<span data-ttu-id="32271-151">방법: 변수 값 저장 및 검색</span><span class="sxs-lookup"><span data-stu-id="32271-151">How to: Move Data Into and Out of a Variable</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-move-data-into-and-out-of-a-variable.md)  
 [<span data-ttu-id="32271-152">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="32271-152">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [<span data-ttu-id="32271-153">보호됨</span><span class="sxs-lookup"><span data-stu-id="32271-153">Protected</span></span>](../../../../visual-basic/language-reference/modifiers/protected.md)  
 [<span data-ttu-id="32271-154">Friend</span><span class="sxs-lookup"><span data-stu-id="32271-154">Friend</span></span>](../../../../visual-basic/language-reference/modifiers/friend.md)  
 [<span data-ttu-id="32271-155">정적</span><span class="sxs-lookup"><span data-stu-id="32271-155">Static</span></span>](../../../../visual-basic/language-reference/modifiers/static.md)  
 [<span data-ttu-id="32271-156">선언 요소의 특징</span><span class="sxs-lookup"><span data-stu-id="32271-156">Declared Element Characteristics</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)  
 [<span data-ttu-id="32271-157">지역 형식 유추</span><span class="sxs-lookup"><span data-stu-id="32271-157">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [<span data-ttu-id="32271-158">Option Infer 문</span><span class="sxs-lookup"><span data-stu-id="32271-158">Option Infer Statement</span></span>](../../../../visual-basic/language-reference/statements/option-infer-statement.md)
