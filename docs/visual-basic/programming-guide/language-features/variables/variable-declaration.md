---
title: "Visual Basic의 변수 선언 | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- variables [Visual Basic], declaring
- member variables, declarations
- Dim statement, variable declaration
- declaring variables
- variables [Visual Basic], scope
- variables [Visual Basic], data types
- data types [Visual Basic], variable declarations
- lifetime, variables
- variables [Visual Basic], lifetime
- access levels, variables
- scope, declaration statements
- variables [Visual Basic], access level
- local variables, declarations
- scope, variables
ms.assetid: d8f10226-92b1-480f-9f53-df377b2d7e15
caps.latest.revision: 31
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: dac536b99eb4515c75381dc4e28720a92e1001f0
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="variable-declaration-in-visual-basic"></a><span data-ttu-id="21369-102">Visual Basic의 변수 선언</span><span class="sxs-lookup"><span data-stu-id="21369-102">Variable Declaration in Visual Basic</span></span>
<span data-ttu-id="21369-103">이름 및 특성을 지정 하려면 변수를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="21369-103">You declare a variable to specify its name and characteristics.</span></span> <span data-ttu-id="21369-104">변수에 대 한 선언문은는 [Dim](../../../../visual-basic/language-reference/statements/dim-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="21369-104">The declaration statement for variables is the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md).</span></span> <span data-ttu-id="21369-105">위치 및 내용을 변수의 특성을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="21369-105">Its location and contents determine the variable's characteristics.</span></span>  
  
 <span data-ttu-id="21369-106">변수 명명 규칙 및 고려 사항에 대 한 참조 [선언 요소 이름](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="21369-106">For variable naming rules and considerations, see [Declared Element Names](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
## <a name="declaration-levels"></a><span data-ttu-id="21369-107">선언 수준</span><span class="sxs-lookup"><span data-stu-id="21369-107">Declaration Levels</span></span>  
  
### <a name="local-and-member-variables"></a><span data-ttu-id="21369-108">로컬 및 멤버 변수</span><span class="sxs-lookup"><span data-stu-id="21369-108">Local and Member Variables</span></span>  
 <span data-ttu-id="21369-109">A *지역 변수* 은 프로시저 내에서 선언입니다.</span><span class="sxs-lookup"><span data-stu-id="21369-109">A *local variable* is one that is declared within a procedure.</span></span> <span data-ttu-id="21369-110">A *멤버 변수* 의 멤버인는 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 입력; 해당 클래스, 구조체, 모듈의 내부 프로시저 내부가 아니라 내 클래스, 구조체 또는 모듈의 모듈 수준에서 선언 됩니다.</span><span class="sxs-lookup"><span data-stu-id="21369-110">A *member variable* is a member of a [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] type; it is declared at module level, inside a class, structure, or module, but not within any procedure internal to that class, structure, or module.</span></span>  
  
### <a name="shared-and-instance-variables"></a><span data-ttu-id="21369-111">공유 및 인스턴스 변수</span><span class="sxs-lookup"><span data-stu-id="21369-111">Shared and Instance Variables</span></span>  
 <span data-ttu-id="21369-112">클래스 또는 구조체에서 멤버 변수의 범주 공유 되는지 여부에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="21369-112">In a class or structure, the category of a member variable depends on whether or not it is shared.</span></span> <span data-ttu-id="21369-113">으로 선언 된 경우는 [공유](../../../../visual-basic/language-reference/modifiers/shared.md) 키워드를 *공유 변수*, 클래스 또는 구조체의 모든 인스턴스 간에 공유 하는 단일 복사본에 존재 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21369-113">If it is declared with the [Shared](../../../../visual-basic/language-reference/modifiers/shared.md) keyword, it is a *shared variable*, and it exists in a single copy shared among all instances of the class or structure.</span></span>  
  
 <span data-ttu-id="21369-114">그렇지 않으면이 생성자는 *인스턴스 변수*, 클래스 또는 구조체의 각 인스턴스에 대해 별도 사본을 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="21369-114">Otherwise it is an *instance variable*, and a separate copy of it is created for each instance of the class or structure.</span></span> <span data-ttu-id="21369-115">주어진된 사본을 인스턴스 변수는 클래스 또는 구조를 만든 인스턴스의 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21369-115">A given copy of an instance variable is available only to the instance of the class or structure in which it was created.</span></span> <span data-ttu-id="21369-116">그는 독립적 클래스 또는 구조체의 다른 인스턴스에서 인스턴스 변수의 복사본입니다.</span><span class="sxs-lookup"><span data-stu-id="21369-116">It is independent of a copy of the instance variable in any other instance of the class or structure.</span></span>  
  
## <a name="declaring-data-type"></a><span data-ttu-id="21369-117">데이터 형식 선언</span><span class="sxs-lookup"><span data-stu-id="21369-117">Declaring Data Type</span></span>  
 <span data-ttu-id="21369-118">[으로](../../../../visual-basic/language-reference/statements/as-clause.md) 선언문에 절을 사용 하면 데이터 형식이 나 개체 형식의 선언 하는 변수를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21369-118">The [As](../../../../visual-basic/language-reference/statements/as-clause.md) clause in the declaration statement allows you to define the data type or object type of the variable you are declaring.</span></span> <span data-ttu-id="21369-119">변수에 대 한 다음 유형 중 하나를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21369-119">You can specify any of the following types for a variable:</span></span>  
  
-   <span data-ttu-id="21369-120">등의 기본 데이터 형식 `Boolean`, `Long`, 또는`Decimal`</span><span class="sxs-lookup"><span data-stu-id="21369-120">An elementary data type, such as `Boolean`, `Long`, or `Decimal`</span></span>  
  
-   <span data-ttu-id="21369-121">복합 데이터 형식, 배열 또는 구조체와 같은</span><span class="sxs-lookup"><span data-stu-id="21369-121">A composite data type, such as an array or structure</span></span>  
  
-   <span data-ttu-id="21369-122">개체 유형 또는 응용 프로그램 또는 다른 응용 프로그램에 정의 된 클래스</span><span class="sxs-lookup"><span data-stu-id="21369-122">An object type, or class, defined either in your application or in another application</span></span>  
  
-   <span data-ttu-id="21369-123">A [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] 클래스 같은 <xref:System.Windows.Forms.Label>또는 <xref:System.Windows.Forms.TextBox></xref:System.Windows.Forms.TextBox> </xref:System.Windows.Forms.Label></span><span class="sxs-lookup"><span data-stu-id="21369-123">A [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] class, such as <xref:System.Windows.Forms.Label> or <xref:System.Windows.Forms.TextBox></span></span>  
  
-   <span data-ttu-id="21369-124">인터페이스와 같은 형식 <xref:System.IComparable>또는 <xref:System.IDisposable></xref:System.IDisposable> </xref:System.IComparable></span><span class="sxs-lookup"><span data-stu-id="21369-124">An interface type, such as <xref:System.IComparable> or <xref:System.IDisposable></span></span>  
  
 <span data-ttu-id="21369-125">데이터 형식을 반복 하지 않고 하나의 문에서 여러 변수를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21369-125">You can declare several variables in one statement without having to repeat the data type.</span></span> <span data-ttu-id="21369-126">다음 문에서 변수 `i`, `j`, 및 `k` 형식으로 선언 된 `Integer`, `l` 및 `m` 으로 `Long`, 및 `x` 및 `y` 으로 `Single`:</span><span class="sxs-lookup"><span data-stu-id="21369-126">In the following statements, the variables `i`, `j`, and `k` are declared as type `Integer`, `l` and `m` as `Long`, and `x` and `y` as `Single`:</span></span>  
  
```  
Dim i, j, k As Integer  
' All three variables in the preceding statement are declared as Integer.  
Dim l, m As Long, x, y As Single  
' In the preceding statement, l and m are Long, x and y are Single.  
```  
  
 <span data-ttu-id="21369-127">데이터 형식에 대 한 자세한 내용은 참조 하십시오. [데이터 형식](../../../../visual-basic/programming-guide/language-features/data-types/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="21369-127">For more information on data types, see [Data Types](../../../../visual-basic/programming-guide/language-features/data-types/index.md).</span></span> <span data-ttu-id="21369-128">개체에 대 한 자세한 내용은 참조 하십시오. [개체 및 클래스](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md) 및 [구성 요소를 사용한 프로그래밍](http://msdn.microsoft.com/library/d4d4fcb4-e0b8-46b3-b679-7ee0026eb9e3)합니다.</span><span class="sxs-lookup"><span data-stu-id="21369-128">For more information on objects, see [Objects and Classes](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md) and [Programming with Components](http://msdn.microsoft.com/library/d4d4fcb4-e0b8-46b3-b679-7ee0026eb9e3).</span></span>  
  
## <a name="local-type-inference"></a><span data-ttu-id="21369-129">지역 형식 유추</span><span class="sxs-lookup"><span data-stu-id="21369-129">Local Type Inference</span></span>  
 <span data-ttu-id="21369-130">*형식 유추* 없이 선언 된 지역 변수의 데이터 형식을 결정 하는 데 사용 되는 `As` 절.</span><span class="sxs-lookup"><span data-stu-id="21369-130">*Type inference* is used to determine the data types of local variables declared without an `As` clause.</span></span> <span data-ttu-id="21369-131">컴파일러는 초기화 식의 형식에서 변수의 형식을 유추합니다.</span><span class="sxs-lookup"><span data-stu-id="21369-131">The compiler infers the type of the variable from the type of the initialization expression.</span></span> <span data-ttu-id="21369-132">이렇게 하면 한 형식을 명시적으로 지정 하지 않고 변수를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21369-132">This enables you to declare variables without explicitly stating a type.</span></span> <span data-ttu-id="21369-133">다음 예제에서 모두 `num1` 및 `num2` 는 정수로 강력한 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="21369-133">In the following example, both `num1` and `num2` are strongly typed as integers.</span></span>  
  
 <span data-ttu-id="21369-134">[!code-vb[VbVbalrTypeInference #&1;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/variable-declaration_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="21369-134">[!code-vb[VbVbalrTypeInference#1](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/variable-declaration_1.vb)]</span></span>  
  
 <span data-ttu-id="21369-135">지역 형식 유추를 사용 하려는 경우 `Option Infer` 로 설정 해야 `On`합니다.</span><span class="sxs-lookup"><span data-stu-id="21369-135">If you want to use local type inference, `Option Infer` must be set to `On`.</span></span> <span data-ttu-id="21369-136">자세한 내용은 참조 [로컬 형식 유추](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) 및 [Option Infer 문](../../../../visual-basic/language-reference/statements/option-infer-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="21369-136">For more information, see [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) and [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md).</span></span>  
  
## <a name="characteristics-of-declared-variables"></a><span data-ttu-id="21369-137">선언 된 변수의 특징</span><span class="sxs-lookup"><span data-stu-id="21369-137">Characteristics of Declared Variables</span></span>  
 <span data-ttu-id="21369-138">*수명* 변수의 시간 동안 어떤 용도로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21369-138">The *lifetime* of a variable is the period of time during which it is available for use.</span></span> <span data-ttu-id="21369-139">일반적으로 변수 (예: 프로시저 또는 클래스) 변수를 선언 하는 요소는 계속 존재으로 존재 합니다.</span><span class="sxs-lookup"><span data-stu-id="21369-139">In general, a variable exists as long as the element that declares it (such as a procedure or class) continues to exist.</span></span> <span data-ttu-id="21369-140">변수는 포함 하는 요소의 수명 보다 더 오래 존재 하지 않아도, 선언에 특별 한 모든 작업을 수행할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="21369-140">If the variable does not need to continue existing beyond the lifetime of its containing element, you do not need to do anything special in the declaration.</span></span> <span data-ttu-id="21369-141">변수를 포함 하는 요소의 보다 오래 존재 해야 하는 경우 포함할 수 있습니다는 `Static` 또는 `Shared` 키워드에 해당 `Dim` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="21369-141">If the variable needs to continue to exist longer than its containing element, you can include the `Static` or `Shared` keyword in its `Dim` statement.</span></span> <span data-ttu-id="21369-142">자세한 내용은 참조 [Visual Basic의 수명](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="21369-142">For more information, see [Lifetime in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md).</span></span>  
  
 <span data-ttu-id="21369-143">*범위* 변수는 해당 이름을 한정 하지 않고 변수를 참조할 수 있는 모든 코드 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="21369-143">The *scope* of a variable is the set of all code that can refer to it without qualifying its name.</span></span> <span data-ttu-id="21369-144">변수의 범위는 선언 된 의해 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="21369-144">A variable's scope is determined by where it is declared.</span></span> <span data-ttu-id="21369-145">지정된 된 영역에 있는 코드의 이름을 정규화 하지 않고도 해당 지역에 정의 된 변수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21369-145">Code located in a given region can use the variables defined in that region without having to qualify their names.</span></span> <span data-ttu-id="21369-146">자세한 내용은 참조 [Visual Basic의 범위](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="21369-146">For more information, see [Scope in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md).</span></span>  
  
 <span data-ttu-id="21369-147">변수의 *액세스 수준* 에 액세스할 수 있는 권한을 가진 코드의 범위는 합니다.</span><span class="sxs-lookup"><span data-stu-id="21369-147">A variable's *access level* is the extent of code that has permission to access it.</span></span> <span data-ttu-id="21369-148">이 액세스 한정자에 의해 결정 됩니다 (예: [공용](../../../../visual-basic/language-reference/modifiers/public.md) 또는 [개인](../../../../visual-basic/language-reference/modifiers/private.md))에서 사용 하는 `Dim` 문.</span><span class="sxs-lookup"><span data-stu-id="21369-148">This is determined by the access modifier (such as [Public](../../../../visual-basic/language-reference/modifiers/public.md) or [Private](../../../../visual-basic/language-reference/modifiers/private.md)) that you use in the `Dim` statement.</span></span> <span data-ttu-id="21369-149">자세한 내용은 참조 [Visual Basic의 액세스 수준을](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="21369-149">For more information, see [Access Levels in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21369-150">참고 항목</span><span class="sxs-lookup"><span data-stu-id="21369-150">See Also</span></span>  
 <span data-ttu-id="21369-151">[방법: 새 변수 만들기](../../../../visual-basic/programming-guide/language-features/variables/how-to-create-a-new-variable.md) </span><span class="sxs-lookup"><span data-stu-id="21369-151">[How to: Create a New Variable](../../../../visual-basic/programming-guide/language-features/variables/how-to-create-a-new-variable.md) </span></span>  
<span data-ttu-id="21369-152"> [방법: 내부 및 외부로 변수 데이터를 이동 합니다.](../../../../visual-basic/programming-guide/language-features/variables/how-to-move-data-into-and-out-of-a-variable.md) </span><span class="sxs-lookup"><span data-stu-id="21369-152"> [How to: Move Data Into and Out of a Variable](../../../../visual-basic/programming-guide/language-features/variables/how-to-move-data-into-and-out-of-a-variable.md) </span></span>  
<span data-ttu-id="21369-153"> [데이터 형식](../../../../visual-basic/language-reference/data-types/data-type-summary.md) </span><span class="sxs-lookup"><span data-stu-id="21369-153"> [Data Types](../../../../visual-basic/language-reference/data-types/data-type-summary.md) </span></span>  
<span data-ttu-id="21369-154"> [보호](../../../../visual-basic/language-reference/modifiers/protected.md) </span><span class="sxs-lookup"><span data-stu-id="21369-154"> [Protected](../../../../visual-basic/language-reference/modifiers/protected.md) </span></span>  
<span data-ttu-id="21369-155"> [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) </span><span class="sxs-lookup"><span data-stu-id="21369-155"> [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) </span></span>  
<span data-ttu-id="21369-156"> [정적](../../../../visual-basic/language-reference/modifiers/static.md) </span><span class="sxs-lookup"><span data-stu-id="21369-156"> [Static](../../../../visual-basic/language-reference/modifiers/static.md) </span></span>  
<span data-ttu-id="21369-157"> [선언된 요소의 특징](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md) </span><span class="sxs-lookup"><span data-stu-id="21369-157"> [Declared Element Characteristics](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md) </span></span>  
<span data-ttu-id="21369-158"> [지역 형식 유추](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) </span><span class="sxs-lookup"><span data-stu-id="21369-158"> [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) </span></span>  
<span data-ttu-id="21369-159"> [Option Infer 문](../../../../visual-basic/language-reference/statements/option-infer-statement.md)</span><span class="sxs-lookup"><span data-stu-id="21369-159"> [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md)</span></span>
