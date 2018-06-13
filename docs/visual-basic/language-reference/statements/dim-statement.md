---
title: Dim 문(Visual Basic)
ms.date: 05/12/2018
f1_keywords:
- vb.Dim
- Dim
helpviewer_keywords:
- Public keyword [Visual Basic], in Dim statement
- Dim statement [Visual Basic]
- fixed-length strings [Visual Basic], declaring
- variables [Visual Basic], declaring
- WithEvents keyword [Visual Basic], Dim statement
- dynamic arrays [Visual Basic], Dim statement
- variables [Visual Basic], initializing
- '{} braces'
- fields [Visual Basic], as member variables
- declarations [Visual Basic], dynamic arrays
- member variables [Visual Basic]
- default values [Visual Basic]
- data types [Visual Basic], assigning
- braces {}
- As keyword [Visual Basic], in Dim statement
- arrays [Visual Basic], declaring
- New keyword [Visual Basic], Dim statement
- To keyword [Visual Basic], in Dim statement
- storage [Visual Basic], allocating
- local variables [Visual Basic]
- declaration statements [Visual Basic]
- Dim statement [Visual Basic], syntax
- variables [Visual Basic], member and local
ms.assetid: fae3eca1-f0b2-4400-994b-7aa58a848448
ms.openlocfilehash: b3384b771748a1f2c9e841407042f81ce6ebe76d
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/17/2018
ms.locfileid: "34234729"
---
# <a name="dim-statement-visual-basic"></a><span data-ttu-id="49bb3-102">Dim 문(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="49bb3-102">Dim Statement (Visual Basic)</span></span>
<span data-ttu-id="49bb3-103">선언 하 고 하나 이상의 변수에 대 한 저장 공간을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-103">Declares and allocates storage space for one or more variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49bb3-104">구문</span><span class="sxs-lookup"><span data-stu-id="49bb3-104">Syntax</span></span>  
  
```  
[ <attributelist> ] [ accessmodifier ] [[ Shared ] [ Shadows ] | [ Static ]] [ ReadOnly ]   
Dim [ WithEvents ] variablelist  
```  
  
## <a name="parts"></a><span data-ttu-id="49bb3-105">요소</span><span class="sxs-lookup"><span data-stu-id="49bb3-105">Parts</span></span>  
  
-   `attributelist`  
  
     <span data-ttu-id="49bb3-106">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-106">Optional.</span></span> <span data-ttu-id="49bb3-107">참조 [특성 목록](../../../visual-basic/language-reference/statements/attribute-list.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-107">See [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md).</span></span>  
  
-   `accessmodifier`  
  
     <span data-ttu-id="49bb3-108">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-108">Optional.</span></span> <span data-ttu-id="49bb3-109">다음 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-109">Can be one of the following:</span></span>  
  
    -   [<span data-ttu-id="49bb3-110">공용</span><span class="sxs-lookup"><span data-stu-id="49bb3-110">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
  
    -   [<span data-ttu-id="49bb3-111">보호됨</span><span class="sxs-lookup"><span data-stu-id="49bb3-111">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)  
  
    -   [<span data-ttu-id="49bb3-112">Friend</span><span class="sxs-lookup"><span data-stu-id="49bb3-112">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)  
  
    -   [<span data-ttu-id="49bb3-113">전용</span><span class="sxs-lookup"><span data-stu-id="49bb3-113">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)  
  
    -   [<span data-ttu-id="49bb3-114">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="49bb3-114">Protected Friend</span></span>](../../language-reference/modifiers/protected-friend.md)
    
    - [<span data-ttu-id="49bb3-115">보호 된 개인</span><span class="sxs-lookup"><span data-stu-id="49bb3-115">Private Protected</span></span>](../../language-reference/modifiers/private-protected.md)

     <span data-ttu-id="49bb3-116">참조 [액세스 수준을 Visual Basic의](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-116">See [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
-   `Shared`  
  
     <span data-ttu-id="49bb3-117">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-117">Optional.</span></span> <span data-ttu-id="49bb3-118">참조 [공유](../../../visual-basic/language-reference/modifiers/shared.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-118">See [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span></span>  
  
-   `Shadows`  
  
     <span data-ttu-id="49bb3-119">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-119">Optional.</span></span> <span data-ttu-id="49bb3-120">참조 [그림자](../../../visual-basic/language-reference/modifiers/shadows.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-120">See [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span></span>  
  
-   `Static`  
  
     <span data-ttu-id="49bb3-121">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-121">Optional.</span></span> <span data-ttu-id="49bb3-122">참조 [정적](../../../visual-basic/language-reference/modifiers/static.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-122">See [Static](../../../visual-basic/language-reference/modifiers/static.md).</span></span>  
  
-   `ReadOnly`  
  
     <span data-ttu-id="49bb3-123">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-123">Optional.</span></span> <span data-ttu-id="49bb3-124">참조 [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-124">See [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
-   `WithEvents`  
  
     <span data-ttu-id="49bb3-125">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-125">Optional.</span></span> <span data-ttu-id="49bb3-126">이 이벤트를 발생 시킬 수 있는 클래스의 인스턴스를 참조 하는 개체 변수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-126">Specifies that these are object variables that refer to instances of a class that can raise events.</span></span> <span data-ttu-id="49bb3-127">참조 [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-127">See [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md).</span></span>  
  
-   `variablelist`  
  
     <span data-ttu-id="49bb3-128">필수.</span><span class="sxs-lookup"><span data-stu-id="49bb3-128">Required.</span></span> <span data-ttu-id="49bb3-129">이 문에서 선언 되는 변수의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-129">List of variables being declared in this statement.</span></span>  
  
     `variable [ , variable ... ]`  
  
     <span data-ttu-id="49bb3-130">각 `variable`에는 다음과 같은 구문과 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-130">Each `variable` has the following syntax and parts:</span></span>  
  
     <span data-ttu-id="49bb3-131">`variablename [ ( [ boundslist ] ) ] [ As [ New ] datatype [ With`{`[ .propertyname = propinitializer [ , ... ] ] } ] ] [ = initializer ]`</span><span class="sxs-lookup"><span data-stu-id="49bb3-131">`variablename [ ( [ boundslist ] ) ] [ As [ New ] datatype [ With`{`[ .propertyname = propinitializer [ , ... ] ] } ] ] [ = initializer ]`</span></span>  
  
    |<span data-ttu-id="49bb3-132">파트</span><span class="sxs-lookup"><span data-stu-id="49bb3-132">Part</span></span>|<span data-ttu-id="49bb3-133">설명</span><span class="sxs-lookup"><span data-stu-id="49bb3-133">Description</span></span>|  
    |---|---|  
    |`variablename`|<span data-ttu-id="49bb3-134">필수.</span><span class="sxs-lookup"><span data-stu-id="49bb3-134">Required.</span></span> <span data-ttu-id="49bb3-135">변수의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-135">Name of the variable.</span></span> <span data-ttu-id="49bb3-136">참조 [선언 된 요소 이름](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-136">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>|  
    |`boundslist`|<span data-ttu-id="49bb3-137">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-137">Optional.</span></span> <span data-ttu-id="49bb3-138">각 차원의 배열 변수의 범위 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-138">List of bounds of each dimension of an array variable.</span></span>|  
    |`New`|<span data-ttu-id="49bb3-139">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-139">Optional.</span></span> <span data-ttu-id="49bb3-140">클래스의 새 인스턴스를 만듭니다 때는 `Dim` 문 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-140">Creates a new instance of the class when the `Dim` statement runs.</span></span>|  
    |`datatype`|<span data-ttu-id="49bb3-141">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-141">Optional.</span></span> <span data-ttu-id="49bb3-142">변수의 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-142">Data type of the variable.</span></span>|  
    |`With`|<span data-ttu-id="49bb3-143">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-143">Optional.</span></span> <span data-ttu-id="49bb3-144">개체 이니셜라이저 목록을 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-144">Introduces the object initializer list.</span></span>|  
    |`propertyname`|<span data-ttu-id="49bb3-145">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-145">Optional.</span></span> <span data-ttu-id="49bb3-146">인스턴스를 하는 클래스에서 속성의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-146">The name of a property in the class you are making an instance of.</span></span>|  
    |`propinitializer`|<span data-ttu-id="49bb3-147">후 필요한 `propertyname` = 합니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-147">Required after `propertyname` =.</span></span> <span data-ttu-id="49bb3-148">계산 되 고 속성 이름에 할당 하는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-148">The expression that is evaluated and assigned to the property name.</span></span>|  
    |`initializer`|<span data-ttu-id="49bb3-149">선택적 `New` 지정 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-149">Optional if `New` is not specified.</span></span> <span data-ttu-id="49bb3-150">계산 되 고 만들어질 때 변수에 할당 되는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-150">Expression that is evaluated and assigned to the variable when it is created.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="49bb3-151">설명</span><span class="sxs-lookup"><span data-stu-id="49bb3-151">Remarks</span></span>  
 <span data-ttu-id="49bb3-152">Visual Basic 컴파일러에서 사용 하는 `Dim` 문에를 변수의 데이터 형식 및 변수를 액세스할 수 있는 코드 등의 기타 정보를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-152">The Visual Basic compiler uses the `Dim` statement to determine the variable's data type and other information, such as what code can access the variable.</span></span> <span data-ttu-id="49bb3-153">다음 예제에서는 선언 보유 하는 변수는 `Integer` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-153">The following example declares a variable to hold an `Integer` value.</span></span>  
  
```vb  
Dim numberOfStudents As Integer  
```  
  
 <span data-ttu-id="49bb3-154">모든 데이터 형식이 나 열거형, 구조체, 클래스 또는 인터페이스의 이름을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-154">You can specify any data type or the name of an enumeration, structure, class, or interface.</span></span>  
  
```vb  
Dim finished As Boolean  
Dim monitorBox As System.Windows.Forms.Form  
```  
  
 <span data-ttu-id="49bb3-155">사용 된 참조 형식에 대 한는 `New` 데이터 형식에 따라 클래스의 새 인스턴스를 만들거나 구조체 키워드를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-155">For a reference type, you use the `New` keyword to create a new instance of the class or structure that is specified by the data type.</span></span> <span data-ttu-id="49bb3-156">사용 하는 경우 `New`, 이니셜라이저 식 사용 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="49bb3-156">If you use `New`, you do not use an initializer expression.</span></span> <span data-ttu-id="49bb3-157">대신, 변수 만드는 클래스의 생성자에 필요한 경우 인수를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-157">Instead, you supply arguments, if they are required, to the constructor of the class from which you are creating the variable.</span></span>  
  
```vb  
Dim bottomLabel As New System.Windows.Forms.Label  
```  
  
 <span data-ttu-id="49bb3-158">프로시저, 블록, 클래스, 구조체 또는 모듈의 변수를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-158">You can declare a variable in a procedure, block, class, structure, or module.</span></span> <span data-ttu-id="49bb3-159">소스 파일, 네임 스페이스 또는 인터페이스의 변수를 선언할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-159">You cannot declare a variable in a source file, namespace, or interface.</span></span> <span data-ttu-id="49bb3-160">자세한 내용은 [선언 컨텍스트 및 기본 액세스 수준](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="49bb3-160">For more information, see [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>  
  
 <span data-ttu-id="49bb3-161">모든 프로시저 외부의 모듈 수준에서 선언 된 변수는 한 *멤버 변수* 또는 *필드*합니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-161">A variable that is declared at module level, outside any procedure, is a *member variable* or *field*.</span></span> <span data-ttu-id="49bb3-162">멤버 변수는 해당 클래스, 구조체 또는 모듈 전체에서 범위에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-162">Member variables are in scope throughout their class, structure, or module.</span></span> <span data-ttu-id="49bb3-163">프로시저 수준에서 선언 된 변수는 한 *지역 변수*합니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-163">A variable that is declared at procedure level is a *local variable*.</span></span> <span data-ttu-id="49bb3-164">지역 변수는 해당 프로시저 또는 블록 내 에서만 범위에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-164">Local variables are in scope only within their procedure or block.</span></span>  
  
 <span data-ttu-id="49bb3-165">다음 액세스 한정자는 프로시저 외부 변수를 선언 하는 데 사용 됩니다: `Public`, `Protected`, `Friend`, `Protected Friend`, 및 `Private`합니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-165">The following access modifiers are used to declare variables outside a procedure: `Public`, `Protected`, `Friend`, `Protected Friend`, and `Private`.</span></span> <span data-ttu-id="49bb3-166">자세한 내용은 참조 [액세스 수준을 Visual Basic의](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-166">For more information, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 <span data-ttu-id="49bb3-167">`Dim` 키워드는 선택 사항 및 다음 한정자 중 하나를 지정 하는 경우에 일반적으로 생략: `Public`, `Protected`, `Friend`, `Protected Friend`, `Private`, `Shared`, `Shadows`, `Static`, `ReadOnly`, 또는 `WithEvents`합니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-167">The `Dim` keyword is optional and usually omitted if you specify any of the following modifiers: `Public`, `Protected`, `Friend`, `Protected Friend`, `Private`, `Shared`, `Shadows`, `Static`, `ReadOnly`, or `WithEvents`.</span></span>  
  
```vb  
Public maximumAllowed As Double  
Protected Friend currentUserName As String  
Private salary As Decimal  
Static runningTotal As Integer  
```  
  
 <span data-ttu-id="49bb3-168">경우 `Option Explicit` 은 컴파일러 사용 하면 모든 변수에 대 한 선언이 필요 (기본값).</span><span class="sxs-lookup"><span data-stu-id="49bb3-168">If `Option Explicit` is on (the default), the compiler requires a declaration for every variable you use.</span></span> <span data-ttu-id="49bb3-169">자세한 내용은 참조 [Option Explicit 문](../../../visual-basic/language-reference/statements/option-explicit-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-169">For more information, see [Option Explicit Statement](../../../visual-basic/language-reference/statements/option-explicit-statement.md).</span></span>  
  
## <a name="specifying-an-initial-value"></a><span data-ttu-id="49bb3-170">초기 값을 지정</span><span class="sxs-lookup"><span data-stu-id="49bb3-170">Specifying an Initial Value</span></span>  
 <span data-ttu-id="49bb3-171">생성 될 때 값을 변수에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-171">You can assign a value to a variable when it is created.</span></span> <span data-ttu-id="49bb3-172">값 형식에 대 한 사용 하는 *이니셜라이저* 을 변수에 할당 하는 식을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-172">For a value type, you use an *initializer* to supply an expression to be assigned to the variable.</span></span> <span data-ttu-id="49bb3-173">컴파일 타임에 계산 될 수 있는 상수 식 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-173">The expression must evaluate to a constant that can be calculated at compile time.</span></span>  
  
```vb  
Dim quantity As Integer = 10  
Dim message As String = "Just started"  
```  
  
 <span data-ttu-id="49bb3-174">이니셜라이저를 지정 하 고 데이터 형식에 지정 하지 않은 경우는 `As` 절 *형식 유추* 이니셜라이저의 데이터 형식을 유추 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-174">If an initializer is specified and a data type is not specified in an `As` clause, *type inference* is used to infer the data type from the initializer.</span></span> <span data-ttu-id="49bb3-175">다음 예제에서는 모두 `num1` 및 `num2` 는 정수로 강력한 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-175">In the following example, both `num1` and `num2` are strongly typed as integers.</span></span> <span data-ttu-id="49bb3-176">두 번째 선언에서 형식 유추 3 값에서 형식을 유추합니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-176">In the second declaration, type inference infers the type from the value 3.</span></span>  
  
```vb  
' Use explicit typing.  
Dim num1 As Integer = 3  
  
' Use local type inference.  
Dim num2 = 3  
```  
  
 <span data-ttu-id="49bb3-177">형식 유추는 프로시저 수준에서 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-177">Type inference applies at the procedure level.</span></span> <span data-ttu-id="49bb3-178">클래스, 구조체, 모듈 또는 인터페이스의 프로시저 외부에 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-178">It does not apply outside a procedure in a class, structure, module, or interface.</span></span> <span data-ttu-id="49bb3-179">형식 유추 하는 방법에 대 한 자세한 내용은 참조 [Option Infer 문](../../../visual-basic/language-reference/statements/option-infer-statement.md) 및 [지역 형식 유추](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-179">For more information about type inference, see [Option Infer Statement](../../../visual-basic/language-reference/statements/option-infer-statement.md) and [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span>  
  
 <span data-ttu-id="49bb3-180">데이터 형식 또는 이니셜라이저가 지정 되지 않은 경우 수행 되는 작업에 대 한 정보를 참조 하십시오. [기본 데이터 형식 및 값](../../../visual-basic/language-reference/statements/dim-statement.md#default) 이 항목의 뒷부분에 나오는 합니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-180">For information about what happens when a data type or initializer is not specified, see [Default Data Types and Values](../../../visual-basic/language-reference/statements/dim-statement.md#default) later in this topic.</span></span>  
  
 <span data-ttu-id="49bb3-181">사용할 수는 *개체 이니셜라이저* 를 명명 된 형식과 익명 형식의 인스턴스를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-181">You can use an *object initializer* to declare instances of named and anonymous types.</span></span> <span data-ttu-id="49bb3-182">인스턴스를 만들고 다음 코드는 `Student` 클래스 및 개체 이니셜라이저를 사용 하 여 속성을 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-182">The following code creates an instance of a `Student` class and uses an object initializer to initialize properties.</span></span>  
  
```vb  
Dim student1 As New Student With {.First = "Michael",   
                                  .Last = "Tucker"}  
```  
  
 <span data-ttu-id="49bb3-183">개체 이니셜라이저에 대 한 자세한 내용은 참조 [하는 방법: 개체 이니셜라이저를 사용 하 여 개체 선언](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md), [개체 이니셜라이저: 명명 된 형식과 익명 형식](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md), 및 [익명 형식 ](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="49bb3-183">For more information about object initializers, see [How to: Declare an Object by Using an Object Initializer](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md), [Object Initializers: Named and Anonymous Types](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md), and [Anonymous Types](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span>  
  
## <a name="declaring-multiple-variables"></a><span data-ttu-id="49bb3-184">여러 변수 선언</span><span class="sxs-lookup"><span data-stu-id="49bb3-184">Declaring Multiple Variables</span></span>  
 <span data-ttu-id="49bb3-185">괄호를 사용 하 여 각각에 대 한, 및 각 배열 이름 다음 변수 이름을 지정 하나의 선언문에서 여러 변수를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-185">You can declare several variables in one declaration statement, specifying the variable name for each one, and following each array name with parentheses.</span></span> <span data-ttu-id="49bb3-186">여러 변수는 쉼표로 구분됩니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-186">Multiple variables are separated by commas.</span></span>  
  
```vb  
Dim lastTime, nextTime, allTimes() As Date  
```  
  
 <span data-ttu-id="49bb3-187">하나 이상의 변수를 선언 하는 경우 `As` 절 변수 해당 그룹에 대 한 이니셜라이저를 지정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-187">If you declare more than one variable with one `As` clause, you cannot supply an initializer for that group of variables.</span></span>  
  
 <span data-ttu-id="49bb3-188">별도 사용 하 여 서로 다른 데이터 형식이 서로 다른 변수를 지정할 수 있습니다 `As` 선언 하는 각 변수에 대해 절.</span><span class="sxs-lookup"><span data-stu-id="49bb3-188">You can specify different data types for different variables by using a separate `As` clause for each variable you declare.</span></span> <span data-ttu-id="49bb3-189">각 변수는 첫 번째 범위에서 지정 된 데이터 형식이 `As` 절 다음에 오는 해당 `variablename` 부분입니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-189">Each variable takes the data type specified in the first `As` clause encountered after its `variablename` part.</span></span>  
  
```vb  
Dim a, b, c As Single, x, y As Double, i As Integer  
' a, b, and c are all Single; x and y are both Double  
```  
  
## <a name="arrays"></a><span data-ttu-id="49bb3-190">배열</span><span class="sxs-lookup"><span data-stu-id="49bb3-190">Arrays</span></span>  
 <span data-ttu-id="49bb3-191">보유 하는 변수를 선언할 수는 *배열*, 여러 값을 보유할 수 있는 합니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-191">You can declare a variable to hold an *array*, which can hold multiple values.</span></span> <span data-ttu-id="49bb3-192">배열을 포함 하는 변수를 지정 하려면에 따라 해당 `variablename` 괄호와 함께 즉시 합니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-192">To specify that a variable holds an array, follow its `variablename` immediately with parentheses.</span></span> <span data-ttu-id="49bb3-193">배열에 대 한 자세한 내용은 참조 [배열](../../../visual-basic/programming-guide/language-features/arrays/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-193">For more information about arrays, see [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>  
  
 <span data-ttu-id="49bb3-194">하 한과 배열의 각 차원의 상한을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-194">You can specify the lower and upper bound of each dimension of an array.</span></span> <span data-ttu-id="49bb3-195">이 작업을 수행 하려면 포함 한 `boundslist` 괄호 안에 넣으세요.</span><span class="sxs-lookup"><span data-stu-id="49bb3-195">To do this, include a `boundslist` inside the parentheses.</span></span> <span data-ttu-id="49bb3-196">각 차원에 대 한는 `boundslist` 상한 및 필요에 따라 하한값을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-196">For each dimension, the `boundslist` specifies the upper bound and optionally the lower bound.</span></span> <span data-ttu-id="49bb3-197">하 한은 항상 0 여부 지정 여부입니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-197">The lower bound is always zero, whether you specify it or not.</span></span> <span data-ttu-id="49bb3-198">각 인덱스는 0부터 상한 값 달라질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-198">Each index can vary from zero through its upper bound value.</span></span>  
  
 <span data-ttu-id="49bb3-199">다음 두 문은 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-199">The following two statements are equivalent.</span></span> <span data-ttu-id="49bb3-200">각 문은 21 배열을 `Integer` 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-200">Each statement declares an array of 21 `Integer` elements.</span></span> <span data-ttu-id="49bb3-201">배열에 액세스할 때 인덱스는 0부터 20 까지의 달라질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-201">When you access the array, the index can vary from 0 through 20.</span></span>  
  
```vb  
Dim totals(20) As Integer  
Dim totals(0 To 20) As Integer  
```  
  
 <span data-ttu-id="49bb3-202">다음 문은 형식의 2 차원 배열을 선언 `Double`합니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-202">The following statement declares a two-dimensional array of type `Double`.</span></span> <span data-ttu-id="49bb3-203">배열에는 각 6 열 (5 + 1) 4 행 (3 + 1).</span><span class="sxs-lookup"><span data-stu-id="49bb3-203">The array has 4 rows (3 + 1) of 6 columns (5 + 1) each.</span></span> <span data-ttu-id="49bb3-204">참고 상한 차원 길이의 인덱스에 대 한 가능한 가장 높은 값을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-204">Note that an upper bound represents the highest possible value for the index, not the length of the dimension.</span></span> <span data-ttu-id="49bb3-205">차원의 길이 상한 + 1입니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-205">The length of the dimension is the upper bound plus one.</span></span>  
  
```vb  
Dim matrix2(3, 5) As Double  
```  
  
 <span data-ttu-id="49bb3-206">배열 1에서 32 차원을 초과에 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-206">An array can have from 1 to 32 dimensions.</span></span>  
  
 <span data-ttu-id="49bb3-207">모든 범위를 배열 선언에서 비워 둘 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-207">You can leave all the bounds blank in an array declaration.</span></span> <span data-ttu-id="49bb3-208">이 작업을 수행 하는 경우 배열에를 지정 하면 차원의 수 있지만 초기화 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-208">If you do this, the array has the number of dimensions you specify, but it is uninitialized.</span></span> <span data-ttu-id="49bb3-209">해당 값이 `Nothing` 초기화 하기 전까지 배열 요소의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-209">It has a value of `Nothing` until you initialize at least some of its elements.</span></span> <span data-ttu-id="49bb3-210">`Dim` 문은 차원이 없습니다. 또는 모든 차원에 대해 범위를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-210">The `Dim` statement must specify bounds either for all dimensions or for no dimensions.</span></span>  
  
```vb  
' Declare an array with blank array bounds.  
Dim messages() As String  
' Initialize the array.  
ReDim messages(4)  
```  
  
 <span data-ttu-id="49bb3-211">배열에 둘 이상의 차원, 차원 수를 나타내는 괄호 사이 쉼표를 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-211">If the array has more than one dimension, you must include commas between the parentheses to indicate the number of dimensions.</span></span>  
  
```vb  
Dim oneDimension(), twoDimensions(,), threeDimensions(,,) As Byte  
```  
  
 <span data-ttu-id="49bb3-212">선언할 수는 *길이가 0 인 배열을* -1로 배열의 차원 중 하나를 선언 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-212">You can declare a *zero-length array* by declaring one of the array's dimensions to be -1.</span></span> <span data-ttu-id="49bb3-213">길이가 0 인 배열을 저장 하는 변수는 값이 없는 `Nothing`합니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-213">A variable that holds a zero-length array does not have the value `Nothing`.</span></span> <span data-ttu-id="49bb3-214">길이가 0 인 배열이 특정 공용 언어 런타임 함수는 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-214">Zero-length arrays are required by certain common language runtime functions.</span></span> <span data-ttu-id="49bb3-215">이러한 배열에 액세스 하려고 하면 런타임 예외가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-215">If you try to access such an array, a runtime exception occurs.</span></span> <span data-ttu-id="49bb3-216">자세한 내용은 참조 [배열](../../../visual-basic/programming-guide/language-features/arrays/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-216">For more information, see [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>  
  
 <span data-ttu-id="49bb3-217">배열 리터럴을 사용 하 여 배열 값을 초기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-217">You can initialize the values of an array by using an array literal.</span></span> <span data-ttu-id="49bb3-218">이 위해 초기화 값을 중괄호를 묶습니다 (`{}`).</span><span class="sxs-lookup"><span data-stu-id="49bb3-218">To do this, surround the initialization values with braces (`{}`).</span></span>  
  
```vb  
Dim longArray() As Long = {0, 1, 2, 3}  
```  
  
 <span data-ttu-id="49bb3-219">다차원 배열에 대 한 별도 각 차원에 대 한 초기화는 중괄호로 외부 차원에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-219">For multidimensional arrays, the initialization for each separate dimension is enclosed in braces in the outer dimension.</span></span> <span data-ttu-id="49bb3-220">요소는 행 중심 순서로 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-220">The elements are specified in row-major order.</span></span>  
  
```vb  
Dim twoDimensions(,) As Integer = {{0, 1, 2}, {10, 11, 12}}  
```  
  
 <span data-ttu-id="49bb3-221">배열 리터럴에 대 한 자세한 내용은 참조 [배열](../../../visual-basic/programming-guide/language-features/arrays/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-221">For more information about array literals, see [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>  
  
##  <a name="default"></a> <span data-ttu-id="49bb3-222">기본 데이터 형식 및 값</span><span class="sxs-lookup"><span data-stu-id="49bb3-222">Default Data Types and Values</span></span>  
 <span data-ttu-id="49bb3-223">다음 테이블에는 `Dim` 문에서 데이터 형식과 이니셜라이저를 지정하는 다양한 조합의 결과에 대한 설명이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-223">The following table describes the results of various combinations of specifying the data type and initializer in a `Dim` statement.</span></span>  
  
|<span data-ttu-id="49bb3-224">데이터 형식 지정 여부</span><span class="sxs-lookup"><span data-stu-id="49bb3-224">Data type specified?</span></span>|<span data-ttu-id="49bb3-225">이니셜라이저 지정 여부</span><span class="sxs-lookup"><span data-stu-id="49bb3-225">Initializer specified?</span></span>|<span data-ttu-id="49bb3-226">예제</span><span class="sxs-lookup"><span data-stu-id="49bb3-226">Example</span></span>|<span data-ttu-id="49bb3-227">결과</span><span class="sxs-lookup"><span data-stu-id="49bb3-227">Result</span></span>|  
|---|---|---|---|  
|<span data-ttu-id="49bb3-228">아니요</span><span class="sxs-lookup"><span data-stu-id="49bb3-228">No</span></span>|<span data-ttu-id="49bb3-229">아니요</span><span class="sxs-lookup"><span data-stu-id="49bb3-229">No</span></span>|`Dim qty`|<span data-ttu-id="49bb3-230">경우 [Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md) 은 off (기본값) 변수로 설정 `Nothing`합니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-230">If [Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md) is off (the default), the variable is set to `Nothing`.</span></span><br /><br /> <span data-ttu-id="49bb3-231">`Option Strict`가 on이면 컴파일 타임 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-231">If `Option Strict` is on, a compile-time error occurs.</span></span>|  
|<span data-ttu-id="49bb3-232">아니요</span><span class="sxs-lookup"><span data-stu-id="49bb3-232">No</span></span>|<span data-ttu-id="49bb3-233">예</span><span class="sxs-lookup"><span data-stu-id="49bb3-233">Yes</span></span>|`Dim qty = 5`|<span data-ttu-id="49bb3-234">경우 [Option Infer](../../../visual-basic/language-reference/statements/option-infer-statement.md) 는 변수 데이터 형식은 이니셜라이저의 on (기본값) 됩니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-234">If [Option Infer](../../../visual-basic/language-reference/statements/option-infer-statement.md) is on (the default), the variable takes the data type of the initializer.</span></span> <span data-ttu-id="49bb3-235">참조 [지역 형식 유추](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-235">See [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span><br /><br /> <span data-ttu-id="49bb3-236">`Option Infer`가 off이고 `Option Strict`고 off이면 변수가 `Object`의 데이터 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-236">If `Option Infer` is off and `Option Strict` is off, the variable takes the data type of `Object`.</span></span><br /><br /> <span data-ttu-id="49bb3-237">`Option Infer`가 off이고 `Option Strict`는 on이면 컴파일 타임 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-237">If `Option Infer` is off and `Option Strict` is on, a compile-time error occurs.</span></span>|  
|<span data-ttu-id="49bb3-238">예</span><span class="sxs-lookup"><span data-stu-id="49bb3-238">Yes</span></span>|<span data-ttu-id="49bb3-239">아니요</span><span class="sxs-lookup"><span data-stu-id="49bb3-239">No</span></span>|`Dim qty As Integer`|<span data-ttu-id="49bb3-240">변수는 데이터 형식의 기본값으로 초기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-240">The variable is initialized to the default value for the data type.</span></span> <span data-ttu-id="49bb3-241">이 섹션의 뒷부분에 나오는 표를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="49bb3-241">See the table later in this section.</span></span>|  
|<span data-ttu-id="49bb3-242">예</span><span class="sxs-lookup"><span data-stu-id="49bb3-242">Yes</span></span>|<span data-ttu-id="49bb3-243">예</span><span class="sxs-lookup"><span data-stu-id="49bb3-243">Yes</span></span>|`Dim qty  As Integer = 5`|<span data-ttu-id="49bb3-244">이니셜라이저의 데이터 형식을 지정한 데이터 형식으로 변환할 수 없으면 컴파일 시간 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-244">If the data type of the initializer is not convertible to the specified data type, a compile-time error occurs.</span></span>|  
  
 <span data-ttu-id="49bb3-245">데이터 형식을 지정 해도 이니셜라이저를 지정 하지 않은 경우 Visual Basic 데이터 형식에 대 한 기본 값으로 변수를 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-245">If you specify a data type but do not specify an initializer, Visual Basic initializes the variable to the default value for its data type.</span></span> <span data-ttu-id="49bb3-246">다음 표에서 기본 초기화 값을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-246">The following table shows the default initialization values.</span></span>  
  
|<span data-ttu-id="49bb3-247">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="49bb3-247">Data type</span></span>|<span data-ttu-id="49bb3-248">기본값</span><span class="sxs-lookup"><span data-stu-id="49bb3-248">Default value</span></span>|  
|---|---|  
|<span data-ttu-id="49bb3-249">모든 숫자 형식 (포함 하 여 `Byte` 및 `SByte`)</span><span class="sxs-lookup"><span data-stu-id="49bb3-249">All numeric types (including `Byte` and `SByte`)</span></span>|<span data-ttu-id="49bb3-250">0</span><span class="sxs-lookup"><span data-stu-id="49bb3-250">0</span></span>|  
|`Char`|<span data-ttu-id="49bb3-251">이진 0</span><span class="sxs-lookup"><span data-stu-id="49bb3-251">Binary 0</span></span>|  
|<span data-ttu-id="49bb3-252">모든 참조 형식이 (포함 하 여 `Object`, `String`, 및 모든 배열)</span><span class="sxs-lookup"><span data-stu-id="49bb3-252">All reference types (including `Object`, `String`, and all arrays)</span></span>|`Nothing`|  
|`Boolean`|`False`|  
|`Date`|<span data-ttu-id="49bb3-253">1 년 1 월 1의 오전 12시 (01/01/0001 오전 12시: 00)</span><span class="sxs-lookup"><span data-stu-id="49bb3-253">12:00 AM of January 1 of the year 1 (01/01/0001 12:00:00 AM)</span></span>|  
  
 <span data-ttu-id="49bb3-254">구조체의 각 요소는 별도 변수인 것 처럼 초기화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-254">Each element of a structure is initialized as if it were a separate variable.</span></span> <span data-ttu-id="49bb3-255">배열 길이 선언 하지만 해당 요소를 초기화 하지 않는 경우 각 요소는 별도 변수 처럼 초기화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-255">If you declare the length of an array but do not initialize its elements, each element is initialized as if it were a separate variable.</span></span>  
  
## <a name="static-local-variable-lifetime"></a><span data-ttu-id="49bb3-256">정적 지역 변수 수명</span><span class="sxs-lookup"><span data-stu-id="49bb3-256">Static Local Variable Lifetime</span></span>  
 <span data-ttu-id="49bb3-257">A `Static` 지역 변수에 수명 선언 된 프로시저의 보다 깁니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-257">A `Static` local variable has a longer lifetime than that of the procedure in which it is declared.</span></span> <span data-ttu-id="49bb3-258">변수의 수명은 프로시저 선언 된 위치와 인지에 따라 달라 집니다 `Shared`합니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-258">The boundaries of the variable's lifetime depend on where the procedure is declared and whether it is `Shared`.</span></span>  
  
|<span data-ttu-id="49bb3-259">프로시저 선언</span><span class="sxs-lookup"><span data-stu-id="49bb3-259">Procedure declaration</span></span>|<span data-ttu-id="49bb3-260">변수 초기화</span><span class="sxs-lookup"><span data-stu-id="49bb3-260">Variable initialized</span></span>|<span data-ttu-id="49bb3-261">기존 변수 중지</span><span class="sxs-lookup"><span data-stu-id="49bb3-261">Variable stops existing</span></span>|  
|---|---|---|  
|<span data-ttu-id="49bb3-262">모듈에서</span><span class="sxs-lookup"><span data-stu-id="49bb3-262">In a module</span></span>|<span data-ttu-id="49bb3-263">처음에 프로시저 호출 될 때</span><span class="sxs-lookup"><span data-stu-id="49bb3-263">The first time the procedure is called</span></span>|<span data-ttu-id="49bb3-264">프로그램 실행을 중지 하는 경우</span><span class="sxs-lookup"><span data-stu-id="49bb3-264">When your program stops execution</span></span>|  
|<span data-ttu-id="49bb3-265">클래스 또는 구조체에서 절차는 `Shared`</span><span class="sxs-lookup"><span data-stu-id="49bb3-265">In a class or structure, procedure is `Shared`</span></span>|<span data-ttu-id="49bb3-266">처음으로 프로시저를 호출할 특정 인스턴스 또는 클래스 또는 구조체 자체</span><span class="sxs-lookup"><span data-stu-id="49bb3-266">The first time the procedure is called either on a specific instance or on the class or structure itself</span></span>|<span data-ttu-id="49bb3-267">프로그램 실행을 중지 하는 경우</span><span class="sxs-lookup"><span data-stu-id="49bb3-267">When your program stops execution</span></span>|  
|<span data-ttu-id="49bb3-268">클래스 또는 구조체에서 프로시저 되지 않습니다. `Shared`</span><span class="sxs-lookup"><span data-stu-id="49bb3-268">In a class or structure, procedure isn't `Shared`</span></span>|<span data-ttu-id="49bb3-269">처음 절차 특정 인스턴스에서 호출</span><span class="sxs-lookup"><span data-stu-id="49bb3-269">The first time the procedure is called on a specific instance</span></span>|<span data-ttu-id="49bb3-270">가비지 수집 (GC) 인스턴스가 해제 될 때</span><span class="sxs-lookup"><span data-stu-id="49bb3-270">When the instance is released for garbage collection (GC)</span></span>|  
  
## <a name="attributes-and-modifiers"></a><span data-ttu-id="49bb3-271">특성 및 한정자</span><span class="sxs-lookup"><span data-stu-id="49bb3-271">Attributes and Modifiers</span></span>  
 <span data-ttu-id="49bb3-272">지역 변수가 아니라 멤버 변수에만 특성을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-272">You can apply attributes only to member variables, not to local variables.</span></span> <span data-ttu-id="49bb3-273">특성은 지역 변수 같은 임시 저장소에 의미가 없습니다 어셈블리의 메타 데이터에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-273">An attribute contributes information to the assembly's metadata, which is not meaningful for temporary storage such as local variables.</span></span>  
  
 <span data-ttu-id="49bb3-274">모듈 수준에서 사용할 수 없습니다는 `Static` 멤버 변수를 선언 하는 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-274">At module level, you cannot use the `Static` modifier to declare member variables.</span></span> <span data-ttu-id="49bb3-275">프로시저 수준에서 사용할 수 없습니다 `Shared`, `Shadows`, `ReadOnly`, `WithEvents`, 또는 액세스 한정자를 지역 변수를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-275">At procedure level, you cannot use `Shared`, `Shadows`, `ReadOnly`, `WithEvents`, or any access modifiers to declare local variables.</span></span>  
  
 <span data-ttu-id="49bb3-276">변수를 제공 하 여 액세스할 수 있는 코드를 지정할 수 있습니다는 `accessmodifier`합니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-276">You can specify what code can access a variable by supplying an `accessmodifier`.</span></span> <span data-ttu-id="49bb3-277">클래스 및 모듈 멤버 변수 (외부 프로시저)는 기본적으로 private 액세스 및 구조 멤버 변수는 기본적으로 공용 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-277">Class and module member variables (outside any procedure) default to private access, and structure member variables default to public access.</span></span> <span data-ttu-id="49bb3-278">액세스 한정자로 액세스 수준을 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-278">You can adjust their access levels with the access modifiers.</span></span> <span data-ttu-id="49bb3-279">프로시저의 경우) (내 로컬 변수에 액세스 한정자를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-279">You cannot use access modifiers on local variables (inside a procedure).</span></span>  
  
 <span data-ttu-id="49bb3-280">지정할 수 있습니다 `WithEvents` 만 멤버 변수가 아니라를 프로시저 내의 지역 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-280">You can specify `WithEvents` only on member variables, not on local variables inside a procedure.</span></span> <span data-ttu-id="49bb3-281">지정 하는 경우 `WithEvents`, 변수의 데이터 형식을 특정 클래스 형식 이어야, 하지 `Object`합니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-281">If you specify `WithEvents`, the data type of the variable must be a specific class type, not `Object`.</span></span> <span data-ttu-id="49bb3-282">된 배열을 선언할 수 없습니다 `WithEvents`합니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-282">You cannot declare an array with `WithEvents`.</span></span> <span data-ttu-id="49bb3-283">이벤트에 대 한 자세한 내용은 참조 [이벤트](../../../visual-basic/programming-guide/language-features/events/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-283">For more information about events, see [Events](../../../visual-basic/programming-guide/language-features/events/index.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="49bb3-284">코드는 클래스 외부 또는 모듈 이름을 한 정해야 멤버 변수의 해당 클래스, 구조체 또는 모듈의 이름으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-284">Code outside a class, structure, or module must qualify a member variable's name with the name of that class, structure, or module.</span></span> <span data-ttu-id="49bb3-285">코드 바깥쪽 블록 또는 프로시저일 해당 프로시저 또는 블록 내에서 지역 변수를 참조할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-285">Code outside a procedure or block cannot refer to any local variables within that procedure or block.</span></span>  
  
## <a name="releasing-managed-resources"></a><span data-ttu-id="49bb3-286">관리 되는 리소스를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-286">Releasing Managed Resources</span></span>  
 <span data-ttu-id="49bb3-287">.NET Framework 가비지 수집기는 사용자의 추가 코딩 없이 관리 되는 리소스를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-287">The .NET Framework garbage collector disposes of managed resources without any extra coding on your part.</span></span> <span data-ttu-id="49bb3-288">그러나 가비지 수집기에 대 한 대기 하지 않고 관리 되는 리소스의 삭제를 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-288">However, you can force the disposal of a managed resource instead of waiting for the garbage collector.</span></span>  
  
 <span data-ttu-id="49bb3-289">클래스에 특히 중요 하 고 부족 한 리소스 (예: 데이터베이스 연결 또는 파일 핸들)을 갖는 경우 더 이상 사용 되는 클래스 인스턴스를 정리 하는 다음 가비지 수집 될 때까지 대기 하지 않을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-289">If a class holds onto a particularly valuable and scarce resource (such as a database connection or file handle), you might not want to wait until the next garbage collection to clean up a class instance that's no longer in use.</span></span> <span data-ttu-id="49bb3-290">클래스를 구현할 수 있습니다는 <xref:System.IDisposable> 가비지 수집 전에 리소스를 해제 하는 방법을 제공 하는 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-290">A class may implement the <xref:System.IDisposable> interface to provide a way to release resources before a garbage collection.</span></span> <span data-ttu-id="49bb3-291">해당 인터페이스를 구현 하는 클래스를 노출 한 `Dispose` 메서드를 즉시 해제 될을 위해 소중한 리소스를 강제로 호출 될 수 있는 합니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-291">A class that implements that interface exposes a `Dispose` method that can be called to force valuable resources to be released immediately.</span></span>  
  
 <span data-ttu-id="49bb3-292">`Using` 문을의 리소스를 확보 문 집합을 실행 한 다음 리소스를 삭제 하는 프로세스를 자동화 합니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-292">The `Using` statement automates the process of acquiring a resource, executing a set of statements, and then disposing of the resource.</span></span> <span data-ttu-id="49bb3-293">그러나 리소스를 구현 해야는 <xref:System.IDisposable> 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-293">However, the resource must implement the <xref:System.IDisposable> interface.</span></span> <span data-ttu-id="49bb3-294">자세한 내용은 [using 문](../../../visual-basic/language-reference/statements/using-statement.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="49bb3-294">For more information, see [Using Statement](../../../visual-basic/language-reference/statements/using-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="49bb3-295">예제</span><span class="sxs-lookup"><span data-stu-id="49bb3-295">Example</span></span>  
 <span data-ttu-id="49bb3-296">다음 예에서는 변수를 사용 하 여 선언 된 `Dim` 다양 한 옵션을 사용 하 여 문을 합니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-296">The following example declares variables by using the `Dim` statement with various options.</span></span>  
  
 [!code-vb[VbVbalrStatements#141](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/dim-statement_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="49bb3-297">예제</span><span class="sxs-lookup"><span data-stu-id="49bb3-297">Example</span></span>  
 <span data-ttu-id="49bb3-298">다음 예제에서는 1에서 30 사이의 소수를 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-298">The following example lists the prime numbers between 1 and 30.</span></span> <span data-ttu-id="49bb3-299">코드 주석 지역 변수의 범위를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-299">The scope of local variables is described in code comments.</span></span>  
  
 [!code-vb[VbVbalrStatements#142](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/dim-statement_2.vb)]  
  
## <a name="example"></a><span data-ttu-id="49bb3-300">예제</span><span class="sxs-lookup"><span data-stu-id="49bb3-300">Example</span></span>  
 <span data-ttu-id="49bb3-301">다음 예제에서는 `speedValue` 변수가 클래스 수준에서 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-301">In the following example, the `speedValue` variable is declared at the class level.</span></span> <span data-ttu-id="49bb3-302">`Private` 키워드는 변수를 선언 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-302">The `Private` keyword is used to declare the variable.</span></span> <span data-ttu-id="49bb3-303">변수는 모든 프로시저에서 액세스할 수 있습니다는 `Car` 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="49bb3-303">The variable can be accessed by any procedure in the `Car` class.</span></span>  
  
 [!code-vb[VbVbalrStatements#144](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/dim-statement_3.vb)]  
  
 [!code-vb[VbVbalrStatements#145](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/dim-statement_4.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="49bb3-304">참고 항목</span><span class="sxs-lookup"><span data-stu-id="49bb3-304">See Also</span></span>  
 [<span data-ttu-id="49bb3-305">Const 문</span><span class="sxs-lookup"><span data-stu-id="49bb3-305">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
 [<span data-ttu-id="49bb3-306">ReDim 문</span><span class="sxs-lookup"><span data-stu-id="49bb3-306">ReDim Statement</span></span>](../../../visual-basic/language-reference/statements/redim-statement.md)  
 [<span data-ttu-id="49bb3-307">Option Explicit 문</span><span class="sxs-lookup"><span data-stu-id="49bb3-307">Option Explicit Statement</span></span>](../../../visual-basic/language-reference/statements/option-explicit-statement.md)  
 [<span data-ttu-id="49bb3-308">Option Infer 문</span><span class="sxs-lookup"><span data-stu-id="49bb3-308">Option Infer Statement</span></span>](../../../visual-basic/language-reference/statements/option-infer-statement.md)  
 [<span data-ttu-id="49bb3-309">Option Strict 문</span><span class="sxs-lookup"><span data-stu-id="49bb3-309">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [<span data-ttu-id="49bb3-310">프로젝트 디자이너, 컴파일 페이지(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="49bb3-310">Compile Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)  
 [<span data-ttu-id="49bb3-311">변수 선언</span><span class="sxs-lookup"><span data-stu-id="49bb3-311">Variable Declaration</span></span>](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [<span data-ttu-id="49bb3-312">배열</span><span class="sxs-lookup"><span data-stu-id="49bb3-312">Arrays</span></span>](../../../visual-basic/programming-guide/language-features/arrays/index.md)  
 [<span data-ttu-id="49bb3-313">개체 이니셜라이저: 명명된 형식과 익명 형식</span><span class="sxs-lookup"><span data-stu-id="49bb3-313">Object Initializers: Named and Anonymous Types</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)  
 [<span data-ttu-id="49bb3-314">익명 형식</span><span class="sxs-lookup"><span data-stu-id="49bb3-314">Anonymous Types</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)  
 [<span data-ttu-id="49bb3-315">개체 이니셜라이저: 명명된 형식과 익명 형식</span><span class="sxs-lookup"><span data-stu-id="49bb3-315">Object Initializers: Named and Anonymous Types</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)  
 [<span data-ttu-id="49bb3-316">방법: 개체 이니셜라이저를 사용하여 개체 선언</span><span class="sxs-lookup"><span data-stu-id="49bb3-316">How to: Declare an Object by Using an Object Initializer</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)  
 [<span data-ttu-id="49bb3-317">지역 형식 유추</span><span class="sxs-lookup"><span data-stu-id="49bb3-317">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
