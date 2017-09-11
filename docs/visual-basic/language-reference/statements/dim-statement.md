---
title: "Dim 문 (Visual Basic) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Dim
- Dim
dev_langs:
- VB
helpviewer_keywords:
- Public keyword, in Dim statement
- Dim statement
- fixed-length strings, declaring
- variables [Visual Basic], declaring
- WithEvents keyword, Dim statement
- dynamic arrays, Dim statement
- variables [Visual Basic], initializing
- '{} braces'
- fields, as member variables
- declarations, dynamic arrays
- member variables
- default values
- data types [Visual Basic], assigning
- braces {}
- As keyword, in Dim statement
- arrays [Visual Basic], declaring
- New keyword, Dim statement
- To keyword, in Dim statement
- storage, allocating
- local variables
- declaration statements
- Dim statement, syntax
- variables [Visual Basic], member and local
ms.assetid: fae3eca1-f0b2-4400-994b-7aa58a848448
caps.latest.revision: 72
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
ms.sourcegitcommit: dc1c456c71efb3cc6e60a8fdc77384e65975f110
ms.openlocfilehash: 049ab1e82bac6c9f94bc411cd3e7c859e334d739
ms.contentlocale: ko-kr
ms.lasthandoff: 05/15/2017

---
# <a name="dim-statement-visual-basic"></a><span data-ttu-id="dffdd-102">Dim 문(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dffdd-102">Dim Statement (Visual Basic)</span></span>
<span data-ttu-id="dffdd-103">선언 하 고 하나 이상의 변수에 대 한 저장 공간을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-103">Declares and allocates storage space for one or more variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dffdd-104">구문</span><span class="sxs-lookup"><span data-stu-id="dffdd-104">Syntax</span></span>  
  
```  
[ <attributelist> ] [ accessmodifier ] [[ Shared ] [ Shadows ] | [ Static ]] [ ReadOnly ]   
Dim [ WithEvents ] variablelist  
```  
  
## <a name="parts"></a><span data-ttu-id="dffdd-105">요소</span><span class="sxs-lookup"><span data-stu-id="dffdd-105">Parts</span></span>  
  
-   `attributelist`  
  
     <span data-ttu-id="dffdd-106">선택적 요소.</span><span class="sxs-lookup"><span data-stu-id="dffdd-106">Optional.</span></span> <span data-ttu-id="dffdd-107">참조 [특성 목록](../../../visual-basic/language-reference/statements/attribute-list.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-107">See [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md).</span></span>  
  
-   `accessmodifier`  
  
     <span data-ttu-id="dffdd-108">선택적 요소.</span><span class="sxs-lookup"><span data-stu-id="dffdd-108">Optional.</span></span> <span data-ttu-id="dffdd-109">다음 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-109">Can be one of the following:</span></span>  
  
    -   [<span data-ttu-id="dffdd-110">공용</span><span class="sxs-lookup"><span data-stu-id="dffdd-110">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
  
    -   [<span data-ttu-id="dffdd-111">보호됨</span><span class="sxs-lookup"><span data-stu-id="dffdd-111">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)  
  
    -   [<span data-ttu-id="dffdd-112">Friend</span><span class="sxs-lookup"><span data-stu-id="dffdd-112">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)  
  
    -   [<span data-ttu-id="dffdd-113">전용</span><span class="sxs-lookup"><span data-stu-id="dffdd-113">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)  
  
    -   `Protected Friend`  
  
     <span data-ttu-id="dffdd-114">참조 [액세스 수준 Visual Basic의](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-114">See [Access Levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
-   `Shared`  
  
     <span data-ttu-id="dffdd-115">선택적 요소.</span><span class="sxs-lookup"><span data-stu-id="dffdd-115">Optional.</span></span> <span data-ttu-id="dffdd-116">참조 [공유](../../../visual-basic/language-reference/modifiers/shared.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-116">See [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span></span>  
  
-   `Shadows`  
  
     <span data-ttu-id="dffdd-117">선택적 요소.</span><span class="sxs-lookup"><span data-stu-id="dffdd-117">Optional.</span></span> <span data-ttu-id="dffdd-118">참조 [그림자](../../../visual-basic/language-reference/modifiers/shadows.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-118">See [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span></span>  
  
-   `Static`  
  
     <span data-ttu-id="dffdd-119">선택적 요소.</span><span class="sxs-lookup"><span data-stu-id="dffdd-119">Optional.</span></span> <span data-ttu-id="dffdd-120">참조 [정적](../../../visual-basic/language-reference/modifiers/static.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-120">See [Static](../../../visual-basic/language-reference/modifiers/static.md).</span></span>  
  
-   `ReadOnly`  
  
     <span data-ttu-id="dffdd-121">선택적 요소.</span><span class="sxs-lookup"><span data-stu-id="dffdd-121">Optional.</span></span> <span data-ttu-id="dffdd-122">참조 [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-122">See [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
-   `WithEvents`  
  
     <span data-ttu-id="dffdd-123">선택적 요소.</span><span class="sxs-lookup"><span data-stu-id="dffdd-123">Optional.</span></span> <span data-ttu-id="dffdd-124">이 이벤트를 발생 시킬 수 있는 클래스의 인스턴스를 참조 하는 개체 변수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-124">Specifies that these are object variables that refer to instances of a class that can raise events.</span></span> <span data-ttu-id="dffdd-125">참조 [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-125">See [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md).</span></span>  
  
-   `variablelist`  
  
     <span data-ttu-id="dffdd-126">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="dffdd-126">Required.</span></span> <span data-ttu-id="dffdd-127">이 문에서 선언 되는 변수의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-127">List of variables being declared in this statement.</span></span>  
  
     `variable [ , variable ... ]`  
  
     <span data-ttu-id="dffdd-128">각 `variable`에는 다음과 같은 구문과 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-128">Each `variable` has the following syntax and parts:</span></span>  
  
     <span data-ttu-id="dffdd-129">`variablename [ ( [ boundslist ] ) ] [ As [ New ] datatype [ With`{`[ .propertyname = propinitializer [ , ... ] ] } ] ] [ = initializer ]`</span><span class="sxs-lookup"><span data-stu-id="dffdd-129">`variablename [ ( [ boundslist ] ) ] [ As [ New ] datatype [ With`{`[ .propertyname = propinitializer [ , ... ] ] } ] ] [ = initializer ]`</span></span>  
  
    |<span data-ttu-id="dffdd-130">파트</span><span class="sxs-lookup"><span data-stu-id="dffdd-130">Part</span></span>|<span data-ttu-id="dffdd-131">설명</span><span class="sxs-lookup"><span data-stu-id="dffdd-131">Description</span></span>|  
    |---|---|  
    |`variablename`|<span data-ttu-id="dffdd-132">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="dffdd-132">Required.</span></span> <span data-ttu-id="dffdd-133">변수의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-133">Name of the variable.</span></span> <span data-ttu-id="dffdd-134">참조 [선언 된 요소 이름](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-134">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>|  
    |`boundslist`|<span data-ttu-id="dffdd-135">선택적 요소.</span><span class="sxs-lookup"><span data-stu-id="dffdd-135">Optional.</span></span> <span data-ttu-id="dffdd-136">배열 변수의 각 차원 범위 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-136">List of bounds of each dimension of an array variable.</span></span>|  
    |`New`|<span data-ttu-id="dffdd-137">선택적 요소.</span><span class="sxs-lookup"><span data-stu-id="dffdd-137">Optional.</span></span> <span data-ttu-id="dffdd-138">클래스의 새 인스턴스를 만듭니다 때는 `Dim` 문 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-138">Creates a new instance of the class when the `Dim` statement runs.</span></span>|  
    |`datatype`|<span data-ttu-id="dffdd-139">선택적 요소.</span><span class="sxs-lookup"><span data-stu-id="dffdd-139">Optional.</span></span> <span data-ttu-id="dffdd-140">변수의 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-140">Data type of the variable.</span></span>|  
    |`With`|<span data-ttu-id="dffdd-141">선택적 요소.</span><span class="sxs-lookup"><span data-stu-id="dffdd-141">Optional.</span></span> <span data-ttu-id="dffdd-142">개체 이니셜라이저 목록을 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-142">Introduces the object initializer list.</span></span>|  
    |`propertyname`|<span data-ttu-id="dffdd-143">선택적 요소.</span><span class="sxs-lookup"><span data-stu-id="dffdd-143">Optional.</span></span> <span data-ttu-id="dffdd-144">클래스에서 속성의 이름의 인스턴스로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-144">The name of a property in the class you are making an instance of.</span></span>|  
    |`propinitializer`|<span data-ttu-id="dffdd-145">후 필요한 `propertyname` =.</span><span class="sxs-lookup"><span data-stu-id="dffdd-145">Required after `propertyname` =.</span></span> <span data-ttu-id="dffdd-146">계산 되 고 속성 이름에 할당 하는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-146">The expression that is evaluated and assigned to the property name.</span></span>|  
    |`initializer`|<span data-ttu-id="dffdd-147">선택적 if `New` 지정 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-147">Optional if `New` is not specified.</span></span> <span data-ttu-id="dffdd-148">계산 되 고 만들어질 때 변수에 할당 되는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-148">Expression that is evaluated and assigned to the variable when it is created.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dffdd-149">설명</span><span class="sxs-lookup"><span data-stu-id="dffdd-149">Remarks</span></span>  
 <span data-ttu-id="dffdd-150">Visual Basic 컴파일러를 사용 하는 `Dim` 문에를 변수의 데이터 형식 및 변수를 액세스할 수 있는 코드 등의 기타 정보를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-150">The Visual Basic compiler uses the `Dim` statement to determine the variable's data type and other information, such as what code can access the variable.</span></span> <span data-ttu-id="dffdd-151">다음 예제에서는 선언 보유 하는 변수는 `Integer` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-151">The following example declares a variable to hold an `Integer` value.</span></span>  
  
```vb  
Dim numberOfStudents As Integer  
```  
  
 <span data-ttu-id="dffdd-152">모든 데이터 형식이 나 열거형, 구조체, 클래스 또는 인터페이스의 이름을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-152">You can specify any data type or the name of an enumeration, structure, class, or interface.</span></span>  
  
```vb  
Dim finished As Boolean  
Dim monitorBox As System.Windows.Forms.Form  
```  
  
 <span data-ttu-id="dffdd-153">사용 된 참조 형식에 대 한는 `New` 데이터 형식에 따라 클래스의 새 인스턴스를 만들거나 구조체 키워드를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-153">For a reference type, you use the `New` keyword to create a new instance of the class or structure that is specified by the data type.</span></span> <span data-ttu-id="dffdd-154">사용 하는 경우 `New`, 이니셜라이저 식 사용 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="dffdd-154">If you use `New`, you do not use an initializer expression.</span></span> <span data-ttu-id="dffdd-155">대신, 변수 만들 클래스의 생성자에 필요한 경우 인수를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-155">Instead, you supply arguments, if they are required, to the constructor of the class from which you are creating the variable.</span></span>  
  
```vb  
Dim bottomLabel As New System.Windows.Forms.Label  
```  
  
 <span data-ttu-id="dffdd-156">프로시저, 블록, 클래스, 구조체 또는 모듈에서 변수를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-156">You can declare a variable in a procedure, block, class, structure, or module.</span></span> <span data-ttu-id="dffdd-157">소스 파일, 네임 스페이스 또는 인터페이스에서 변수를 선언할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-157">You cannot declare a variable in a source file, namespace, or interface.</span></span> <span data-ttu-id="dffdd-158">자세한 내용은 참조 [선언 컨텍스트 및 기본 액세스 수준](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-158">For more information, see [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>  
  
 <span data-ttu-id="dffdd-159">모든 프로시저 외부의 모듈 수준에서 선언 된 변수는 한 *멤버 변수* 또는 *필드*합니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-159">A variable that is declared at module level, outside any procedure, is a *member variable* or *field*.</span></span> <span data-ttu-id="dffdd-160">멤버 변수가 클래스, 구조체 또는 모듈의 전체 범위에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-160">Member variables are in scope throughout their class, structure, or module.</span></span> <span data-ttu-id="dffdd-161">프로시저 수준에서 선언 된 변수는 한 *지역 변수*합니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-161">A variable that is declared at procedure level is a *local variable*.</span></span> <span data-ttu-id="dffdd-162">해당 프로시저 또는 블록 내 에서만 범위에는 지역 변수가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-162">Local variables are in scope only within their procedure or block.</span></span>  
  
 <span data-ttu-id="dffdd-163">다음과 같은 액세스 한정자는 프로시저 외부 변수를 선언 하는 데 사용 됩니다: `Public`, `Protected`, `Friend`, `Protected Friend`, 및 `Private`합니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-163">The following access modifiers are used to declare variables outside a procedure: `Public`, `Protected`, `Friend`, `Protected Friend`, and `Private`.</span></span> <span data-ttu-id="dffdd-164">자세한 내용은 참조 [Visual Basic의 액세스 수준을](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-164">For more information, see [Access Levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 <span data-ttu-id="dffdd-165">`Dim` 키워드는 선택 사항 및 다음 한정자를 지정 하는 경우 일반적으로 생략: `Public`, `Protected`, `Friend`, `Protected Friend`, `Private`, `Shared`, `Shadows`, `Static`, `ReadOnly`, 또는 `WithEvents`합니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-165">The `Dim` keyword is optional and usually omitted if you specify any of the following modifiers: `Public`, `Protected`, `Friend`, `Protected Friend`, `Private`, `Shared`, `Shadows`, `Static`, `ReadOnly`, or `WithEvents`.</span></span>  
  
```vb  
Public maximumAllowed As Double  
Protected Friend currentUserName As String  
Private salary As Decimal  
Static runningTotal As Integer  
```  
  
 <span data-ttu-id="dffdd-166">경우 `Option Explicit` 는 컴파일러를 사용 하 여 모든 변수에 대 한 선언이 필요 on (기본값).</span><span class="sxs-lookup"><span data-stu-id="dffdd-166">If `Option Explicit` is on (the default), the compiler requires a declaration for every variable you use.</span></span> <span data-ttu-id="dffdd-167">자세한 내용은 참조 [Option Explicit 문](../../../visual-basic/language-reference/statements/option-explicit-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-167">For more information, see [Option Explicit Statement](../../../visual-basic/language-reference/statements/option-explicit-statement.md).</span></span>  
  
## <a name="specifying-an-initial-value"></a><span data-ttu-id="dffdd-168">초기 값을 지정</span><span class="sxs-lookup"><span data-stu-id="dffdd-168">Specifying an Initial Value</span></span>  
 <span data-ttu-id="dffdd-169">생성 될 때 값을 변수에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-169">You can assign a value to a variable when it is created.</span></span> <span data-ttu-id="dffdd-170">값 형식에 대해 사용 하는 *이니셜라이저* 변수에 할당 하는 식을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-170">For a value type, you use an *initializer* to supply an expression to be assigned to the variable.</span></span> <span data-ttu-id="dffdd-171">컴파일 타임에 계산 될 수 있는 상수 식은 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-171">The expression must evaluate to a constant that can be calculated at compile time.</span></span>  
  
```vb  
Dim quantity As Integer = 10  
Dim message As String = "Just started"  
```  
  
 <span data-ttu-id="dffdd-172">이니셜라이저를 지정 하 고 데이터 형식에 지정 하지 않은 경우는 `As` 절 *형식 유추* 이니셜라이저의 데이터 형식을 유추 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-172">If an initializer is specified and a data type is not specified in an `As` clause, *type inference* is used to infer the data type from the initializer.</span></span> <span data-ttu-id="dffdd-173">다음 예제에서 모두 `num1` 및 `num2` 는 정수로 강력한 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-173">In the following example, both `num1` and `num2` are strongly typed as integers.</span></span> <span data-ttu-id="dffdd-174">두 번째 선언에서 3 값에서 형식을 유추 하는 형식 유추 합니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-174">In the second declaration, type inference infers the type from the value 3.</span></span>  
  
```vb  
' Use explicit typing.  
Dim num1 As Integer = 3  
  
' Use local type inference.  
Dim num2 = 3  
```  
  
 <span data-ttu-id="dffdd-175">형식 유추는 프로시저 수준에서 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-175">Type inference applies at the procedure level.</span></span> <span data-ttu-id="dffdd-176">클래스, 구조체, 모듈 또는 인터페이스의 프로시저 외부에 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-176">It does not apply outside a procedure in a class, structure, module, or interface.</span></span> <span data-ttu-id="dffdd-177">형식 유추 하는 방법에 대 한 자세한 내용은 참조 [Option Infer 문](../../../visual-basic/language-reference/statements/option-infer-statement.md) 및 [로컬 형식 유추](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-177">For more information about type inference, see [Option Infer Statement](../../../visual-basic/language-reference/statements/option-infer-statement.md) and [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span>  
  
 <span data-ttu-id="dffdd-178">데이터 형식 또는 이니셜라이저를 지정 하지 않으면 어떻게 하는 방법에 대 한 정보를 참조 하십시오. [기본 데이터 형식 및 값](../../../visual-basic/language-reference/statements/dim-statement.md#default) 이 항목의 뒷부분에 나오는 합니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-178">For information about what happens when a data type or initializer is not specified, see [Default Data Types and Values](../../../visual-basic/language-reference/statements/dim-statement.md#default) later in this topic.</span></span>  
  
 <span data-ttu-id="dffdd-179">사용할 수는 *개체 이니셜라이저* 를 명명 된 형식과 익명 형식의 인스턴스를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-179">You can use an *object initializer* to declare instances of named and anonymous types.</span></span> <span data-ttu-id="dffdd-180">인스턴스를 만들고 다음 코드는 `Student` 클래스 및 개체 이니셜라이저를 사용 하 여 속성을 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-180">The following code creates an instance of a `Student` class and uses an object initializer to initialize properties.</span></span>  
  
```vb  
Dim student1 As New Student With {.First = "Michael",   
                                  .Last = "Tucker"}  
```  
  
 <span data-ttu-id="dffdd-181">개체 이니셜라이저에 대 한 자세한 내용은 참조 [하는 방법: 개체 이니셜라이저를 사용 하 여 개체 선언](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md), [개체 이니셜라이저: 명명 된 형식과 익명 형식](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md), 및 [익명 형식](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-181">For more information about object initializers, see [How to: Declare an Object by Using an Object Initializer](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md), [Object Initializers: Named and Anonymous Types](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md), and [Anonymous Types](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span>  
  
## <a name="declaring-multiple-variables"></a><span data-ttu-id="dffdd-182">여러 변수를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-182">Declaring Multiple Variables</span></span>  
 <span data-ttu-id="dffdd-183">괄호를 사용 하 여 각각에 대 한, 각 배열 이름 다음에 변수 이름을 지정 하나의 선언문에서 여러 변수를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-183">You can declare several variables in one declaration statement, specifying the variable name for each one, and following each array name with parentheses.</span></span> <span data-ttu-id="dffdd-184">여러 변수는 쉼표로 구분됩니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-184">Multiple variables are separated by commas.</span></span>  
  
```vb  
Dim lastTime, nextTime, allTimes() As Date  
```  
  
 <span data-ttu-id="dffdd-185">하나 이상의 변수를 선언 하는 경우 `As` 절 변수의 해당 그룹에 대 한 이니셜라이저를 제공할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-185">If you declare more than one variable with one `As` clause, you cannot supply an initializer for that group of variables.</span></span>  
  
 <span data-ttu-id="dffdd-186">별도 사용 하 여 다른 데이터 형식을 다른 변수를 지정할 수 있습니다 `As` 선언 하는 각 변수에 대 한 절.</span><span class="sxs-lookup"><span data-stu-id="dffdd-186">You can specify different data types for different variables by using a separate `As` clause for each variable you declare.</span></span> <span data-ttu-id="dffdd-187">각 변수는 첫 번째 지정 된 데이터 형식과 `As` 절 다음에 오는 해당 `variablename` 부분입니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-187">Each variable takes the data type specified in the first `As` clause encountered after its `variablename` part.</span></span>  
  
```vb  
Dim a, b, c As Single, x, y As Double, i As Integer  
' a, b, and c are all Single; x and y are both Double  
```  
  
## <a name="arrays"></a><span data-ttu-id="dffdd-188">배열</span><span class="sxs-lookup"><span data-stu-id="dffdd-188">Arrays</span></span>  
 <span data-ttu-id="dffdd-189">보유 하는 변수를 선언할 수는 *배열*, 여러 값을 보유할 수 있는 합니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-189">You can declare a variable to hold an *array*, which can hold multiple values.</span></span> <span data-ttu-id="dffdd-190">배열을 포함 하는 변수를 지정 하려면에 따라 해당 `variablename` 괄호와 함께 즉시 합니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-190">To specify that a variable holds an array, follow its `variablename` immediately with parentheses.</span></span> <span data-ttu-id="dffdd-191">배열에 대 한 자세한 내용은 참조 [배열](../../../visual-basic/programming-guide/language-features/arrays/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-191">For more information about arrays, see [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>  
  
 <span data-ttu-id="dffdd-192">하 한과 상한을 배열에 있는 각 차원의 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-192">You can specify the lower and upper bound of each dimension of an array.</span></span> <span data-ttu-id="dffdd-193">이렇게 하려면 다음을 포함 한 `boundslist` 괄호 안에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-193">To do this, include a `boundslist` inside the parentheses.</span></span> <span data-ttu-id="dffdd-194">각 차원에 대해는 `boundslist` 상한 및 하 한 필요에 따라 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-194">For each dimension, the `boundslist` specifies the upper bound and optionally the lower bound.</span></span> <span data-ttu-id="dffdd-195">하 한은 항상&0; 있는지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-195">The lower bound is always zero, whether you specify it or not.</span></span> <span data-ttu-id="dffdd-196">각 인덱스는&0;의 상한 값 사이 달라질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-196">Each index can vary from zero through its upper bound value.</span></span>  
  
 <span data-ttu-id="dffdd-197">다음 두 문은 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-197">The following two statements are equivalent.</span></span> <span data-ttu-id="dffdd-198">각 문은 21 배열을 `Integer` 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-198">Each statement declares an array of 21 `Integer` elements.</span></span> <span data-ttu-id="dffdd-199">배열에 액세스할 때 인덱스는 0부터 20 까지의 달라질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-199">When you access the array, the index can vary from 0 through 20.</span></span>  
  
```vb  
Dim totals(20) As Integer  
Dim totals(0 To 20) As Integer  
```  
  
 <span data-ttu-id="dffdd-200">다음 문은 선언 형식의&2; 차원 배열을 `Double`합니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-200">The following statement declares a two-dimensional array of type `Double`.</span></span> <span data-ttu-id="dffdd-201">배열에 각각 6 열 (5 + 1)의 4 행 (3 + 1).</span><span class="sxs-lookup"><span data-stu-id="dffdd-201">The array has 4 rows (3 + 1) of 6 columns (5 + 1) each.</span></span> <span data-ttu-id="dffdd-202">참고 상한을 차원의 길이가 아닌 인덱스에 대 한 가능한 가장 큰 값을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-202">Note that an upper bound represents the highest possible value for the index, not the length of the dimension.</span></span> <span data-ttu-id="dffdd-203">차원 길이가&1;을 더한 상한을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-203">The length of the dimension is the upper bound plus one.</span></span>  
  
```vb  
Dim matrix2(3, 5) As Double  
```  
  
 <span data-ttu-id="dffdd-204">배열 32 차원 1에서 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-204">An array can have from 1 to 32 dimensions.</span></span>  
  
 <span data-ttu-id="dffdd-205">모든 범위를 배열 선언에서 비워 둘 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-205">You can leave all the bounds blank in an array declaration.</span></span> <span data-ttu-id="dffdd-206">이 작업을 수행 하는 경우 배열에을 지정 하면 차원의 수 있지만 초기화 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-206">If you do this, the array has the number of dimensions you specify, but it is uninitialized.</span></span> <span data-ttu-id="dffdd-207">값을가지고 `Nothing` 초기화 하기 전까지 배열 요소의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-207">It has a value of `Nothing` until you initialize at least some of its elements.</span></span> <span data-ttu-id="dffdd-208">`Dim` 문에 차원이 없습니다. 또는 모든 차원에 대해 범위를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-208">The `Dim` statement must specify bounds either for all dimensions or for no dimensions.</span></span>  
  
```vb  
' Declare an array with blank array bounds.  
Dim messages() As String  
' Initialize the array.  
ReDim messages(4)  
```  
  
 <span data-ttu-id="dffdd-209">배열에 둘 이상의 차원, 차원 수를 나타내는 괄호 사이 쉼표를 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-209">If the array has more than one dimension, you must include commas between the parentheses to indicate the number of dimensions.</span></span>  
  
```vb  
Dim oneDimension(), twoDimensions(,), threeDimensions(,,) As Byte  
```  
  
 <span data-ttu-id="dffdd-210">선언할 수는 *길이가&0; 인 배열을* -1로 배열의 차원 중 하나를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-210">You can declare a *zero-length array* by declaring one of the array's dimensions to be -1.</span></span> <span data-ttu-id="dffdd-211">길이가&0; 인 배열을 포함 하는 변수는 값이 없는 `Nothing`합니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-211">A variable that holds a zero-length array does not have the value `Nothing`.</span></span> <span data-ttu-id="dffdd-212">길이가&0; 인 배열이 특정 공용 언어 런타임 함수에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-212">Zero-length arrays are required by certain common language runtime functions.</span></span> <span data-ttu-id="dffdd-213">이러한 배열에 액세스 하려고 하면 런타임 예외가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-213">If you try to access such an array, a runtime exception occurs.</span></span> <span data-ttu-id="dffdd-214">자세한 내용은 참조 [배열](../../../visual-basic/programming-guide/language-features/arrays/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-214">For more information, see [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>  
  
 <span data-ttu-id="dffdd-215">배열 리터럴을 사용 하 여 배열의 값을 초기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-215">You can initialize the values of an array by using an array literal.</span></span> <span data-ttu-id="dffdd-216">이 위해 초기화 값을 중괄호를 묶습니다 (`{}`).</span><span class="sxs-lookup"><span data-stu-id="dffdd-216">To do this, surround the initialization values with braces (`{}`).</span></span>  
  
```vb  
Dim longArray() As Long = {0, 1, 2, 3}  
```  
  
 <span data-ttu-id="dffdd-217">다차원 배열에 대 한 별도 각 차원에 대 한 초기화는 중괄호로 외부 차원에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-217">For multidimensional arrays, the initialization for each separate dimension is enclosed in braces in the outer dimension.</span></span> <span data-ttu-id="dffdd-218">요소는 행 중심 순서로 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-218">The elements are specified in row-major order.</span></span>  
  
```vb  
Dim twoDimensions(,) As Integer = {{0, 1, 2}, {10, 11, 12}}  
```  
  
 <span data-ttu-id="dffdd-219">배열 리터럴에 대 한 자세한 내용은 참조 [배열](../../../visual-basic/programming-guide/language-features/arrays/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-219">For more information about array literals, see [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>  
  
##  <span data-ttu-id="dffdd-220"><a name="default"></a>기본 데이터 형식 및 값</span><span class="sxs-lookup"><span data-stu-id="dffdd-220"><a name="default"></a> Default Data Types and Values</span></span>  
 <span data-ttu-id="dffdd-221">다음 테이블에는 `Dim` 문에서 데이터 형식과 이니셜라이저를 지정하는 다양한 조합의 결과에 대한 설명이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-221">The following table describes the results of various combinations of specifying the data type and initializer in a `Dim` statement.</span></span>  
  
|<span data-ttu-id="dffdd-222">데이터 형식 지정 여부</span><span class="sxs-lookup"><span data-stu-id="dffdd-222">Data type specified?</span></span>|<span data-ttu-id="dffdd-223">이니셜라이저 지정 여부</span><span class="sxs-lookup"><span data-stu-id="dffdd-223">Initializer specified?</span></span>|<span data-ttu-id="dffdd-224">예제</span><span class="sxs-lookup"><span data-stu-id="dffdd-224">Example</span></span>|<span data-ttu-id="dffdd-225">결과</span><span class="sxs-lookup"><span data-stu-id="dffdd-225">Result</span></span>|  
|---|---|---|---|  
|<span data-ttu-id="dffdd-226">아니요</span><span class="sxs-lookup"><span data-stu-id="dffdd-226">No</span></span>|<span data-ttu-id="dffdd-227">아니요</span><span class="sxs-lookup"><span data-stu-id="dffdd-227">No</span></span>|`Dim qty`|<span data-ttu-id="dffdd-228">경우 [Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md) 는 설정 된 변수 off (기본값), `Nothing`합니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-228">If [Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md) is off (the default), the variable is set to `Nothing`.</span></span><br /><br /> <span data-ttu-id="dffdd-229">`Option Strict`가 on이면 컴파일 타임 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-229">If `Option Strict` is on, a compile-time error occurs.</span></span>|  
|<span data-ttu-id="dffdd-230">아니요</span><span class="sxs-lookup"><span data-stu-id="dffdd-230">No</span></span>|<span data-ttu-id="dffdd-231">예</span><span class="sxs-lookup"><span data-stu-id="dffdd-231">Yes</span></span>|`Dim qty = 5`|<span data-ttu-id="dffdd-232">경우 [Option Infer](../../../visual-basic/language-reference/statements/option-infer-statement.md) 가 on (기본값)는 변수 데이터 형식을 이니셜라이저의 합니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-232">If [Option Infer](../../../visual-basic/language-reference/statements/option-infer-statement.md) is on (the default), the variable takes the data type of the initializer.</span></span> <span data-ttu-id="dffdd-233">참조 [지역 형식 유추](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-233">See [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span><br /><br /> <span data-ttu-id="dffdd-234">`Option Infer`가 off이고 `Option Strict`고 off이면 변수가 `Object`의 데이터 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-234">If `Option Infer` is off and `Option Strict` is off, the variable takes the data type of `Object`.</span></span><br /><br /> <span data-ttu-id="dffdd-235">`Option Infer`가 off이고 `Option Strict`는 on이면 컴파일 타임 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-235">If `Option Infer` is off and `Option Strict` is on, a compile-time error occurs.</span></span>|  
|<span data-ttu-id="dffdd-236">예</span><span class="sxs-lookup"><span data-stu-id="dffdd-236">Yes</span></span>|<span data-ttu-id="dffdd-237">아니요</span><span class="sxs-lookup"><span data-stu-id="dffdd-237">No</span></span>|`Dim qty As Integer`|<span data-ttu-id="dffdd-238">변수는 데이터 형식의 기본값으로 초기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-238">The variable is initialized to the default value for the data type.</span></span> <span data-ttu-id="dffdd-239">이 섹션 뒷부분에 나오는 표를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="dffdd-239">See the table later in this section.</span></span>|  
|<span data-ttu-id="dffdd-240">예</span><span class="sxs-lookup"><span data-stu-id="dffdd-240">Yes</span></span>|<span data-ttu-id="dffdd-241">예</span><span class="sxs-lookup"><span data-stu-id="dffdd-241">Yes</span></span>|`Dim qty  As Integer = 5`|<span data-ttu-id="dffdd-242">이니셜라이저의 데이터 형식을 지정한 데이터 형식으로 변환할 수 없으면 컴파일 시간 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-242">If the data type of the initializer is not convertible to the specified data type, a compile-time error occurs.</span></span>|  
  
 <span data-ttu-id="dffdd-243">데이터 형식을 지정 하지만 이니셜라이저를 지정 하지 않는 경우 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 변수 데이터 형식에 대 한 기본 값으로 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-243">If you specify a data type but do not specify an initializer, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] initializes the variable to the default value for its data type.</span></span> <span data-ttu-id="dffdd-244">다음 표에서 기본 초기화 값을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-244">The following table shows the default initialization values.</span></span>  
  
|<span data-ttu-id="dffdd-245">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="dffdd-245">Data type</span></span>|<span data-ttu-id="dffdd-246">기본값</span><span class="sxs-lookup"><span data-stu-id="dffdd-246">Default value</span></span>|  
|---|---|  
|<span data-ttu-id="dffdd-247">모든 숫자 형식 (포함 하 여 `Byte` 및 `SByte`)</span><span class="sxs-lookup"><span data-stu-id="dffdd-247">All numeric types (including `Byte` and `SByte`)</span></span>|<span data-ttu-id="dffdd-248">0</span><span class="sxs-lookup"><span data-stu-id="dffdd-248">0</span></span>|  
|`Char`|<span data-ttu-id="dffdd-249">이진 0</span><span class="sxs-lookup"><span data-stu-id="dffdd-249">Binary 0</span></span>|  
|<span data-ttu-id="dffdd-250">모든 참조 형식 (포함 하 여 `Object`, `String`, 및 모든 배열)</span><span class="sxs-lookup"><span data-stu-id="dffdd-250">All reference types (including `Object`, `String`, and all arrays)</span></span>|`Nothing`|  
|`Boolean`|`False`|  
|`Date`|<span data-ttu-id="dffdd-251">1 년 1 월 1의 오전 12시 (01/01/0001 12시: 00 AM)</span><span class="sxs-lookup"><span data-stu-id="dffdd-251">12:00 AM of January 1 of the year 1 (01/01/0001 12:00:00 AM)</span></span>|  
  
 <span data-ttu-id="dffdd-252">구조체의 각 요소는 마치는 별도 변수인 것 처럼 초기화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-252">Each element of a structure is initialized as if it were a separate variable.</span></span> <span data-ttu-id="dffdd-253">배열의 길이 선언 하지만 해당 요소를 초기화 하지 않는 경우 각 요소는 마치는 별도 변수인 것 처럼 초기화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-253">If you declare the length of an array but do not initialize its elements, each element is initialized as if it were a separate variable.</span></span>  
  
## <a name="static-local-variable-lifetime"></a><span data-ttu-id="dffdd-254">정적 지역 변수 수명</span><span class="sxs-lookup"><span data-stu-id="dffdd-254">Static Local Variable Lifetime</span></span>  
 <span data-ttu-id="dffdd-255">A `Static` 로컬 변수가 수명 선언 된 프로시저의 보다 깁니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-255">A `Static` local variable has a longer lifetime than that of the procedure in which it is declared.</span></span> <span data-ttu-id="dffdd-256">변수의 수명은 인지와 프로시저 선언 된 위치에 따라 달라 집니다 `Shared`합니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-256">The boundaries of the variable's lifetime depend on where the procedure is declared and whether it is `Shared`.</span></span>  
  
|<span data-ttu-id="dffdd-257">프로시저 선언</span><span class="sxs-lookup"><span data-stu-id="dffdd-257">Procedure declaration</span></span>|<span data-ttu-id="dffdd-258">변수 초기화</span><span class="sxs-lookup"><span data-stu-id="dffdd-258">Variable initialized</span></span>|<span data-ttu-id="dffdd-259">기존 변수 중지</span><span class="sxs-lookup"><span data-stu-id="dffdd-259">Variable stops existing</span></span>|  
|---|---|---|  
|<span data-ttu-id="dffdd-260">모듈에서</span><span class="sxs-lookup"><span data-stu-id="dffdd-260">In a module</span></span>|<span data-ttu-id="dffdd-261">처음에 프로시저 호출 될 때</span><span class="sxs-lookup"><span data-stu-id="dffdd-261">The first time the procedure is called</span></span>|<span data-ttu-id="dffdd-262">프로그램 실행을 중지 하는 경우</span><span class="sxs-lookup"><span data-stu-id="dffdd-262">When your program stops execution</span></span>|  
|<span data-ttu-id="dffdd-263">프로시저는 클래스 또는 구조체에는`Shared`</span><span class="sxs-lookup"><span data-stu-id="dffdd-263">In a class or structure, procedure is `Shared`</span></span>|<span data-ttu-id="dffdd-264">처음으로 프로시저를 호출할 특정 인스턴스 또는 클래스 또는 구조체 자체</span><span class="sxs-lookup"><span data-stu-id="dffdd-264">The first time the procedure is called either on a specific instance or on the class or structure itself</span></span>|<span data-ttu-id="dffdd-265">프로그램 실행을 중지 하는 경우</span><span class="sxs-lookup"><span data-stu-id="dffdd-265">When your program stops execution</span></span>|  
|<span data-ttu-id="dffdd-266">클래스 또는 구조체 프로시저 되지 않으므로`Shared`</span><span class="sxs-lookup"><span data-stu-id="dffdd-266">In a class or structure, procedure isn't `Shared`</span></span>|<span data-ttu-id="dffdd-267">특정 인스턴스에서 프로시저가 호출 된 처음으로</span><span class="sxs-lookup"><span data-stu-id="dffdd-267">The first time the procedure is called on a specific instance</span></span>|<span data-ttu-id="dffdd-268">가비지 수집 (GC)에 인스턴스가 해제 되는 경우</span><span class="sxs-lookup"><span data-stu-id="dffdd-268">When the instance is released for garbage collection (GC)</span></span>|  
  
## <a name="attributes-and-modifiers"></a><span data-ttu-id="dffdd-269">특성 및 한정자</span><span class="sxs-lookup"><span data-stu-id="dffdd-269">Attributes and Modifiers</span></span>  
 <span data-ttu-id="dffdd-270">지역 변수가 아닌 멤버 변수에만 특성을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-270">You can apply attributes only to member variables, not to local variables.</span></span> <span data-ttu-id="dffdd-271">특성은 어셈블리의 메타 데이터에 대 한 정보는 의미가 없습니다 지역 변수 같은 임시 저장소에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-271">An attribute contributes information to the assembly's metadata, which is not meaningful for temporary storage such as local variables.</span></span>  
  
 <span data-ttu-id="dffdd-272">모듈 수준에서 사용할 수 없습니다는 `Static` 한정자를 멤버 변수를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-272">At module level, you cannot use the `Static` modifier to declare member variables.</span></span> <span data-ttu-id="dffdd-273">프로시저 수준에서 사용할 수 없습니다 `Shared`, `Shadows`, `ReadOnly`, `WithEvents`, 또는 액세스 한정자를 지역 변수를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-273">At procedure level, you cannot use `Shared`, `Shadows`, `ReadOnly`, `WithEvents`, or any access modifiers to declare local variables.</span></span>  
  
 <span data-ttu-id="dffdd-274">변수를 제공 하 여 액세스할 수 있는 코드를 지정할 수는 `accessmodifier`합니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-274">You can specify what code can access a variable by supplying an `accessmodifier`.</span></span> <span data-ttu-id="dffdd-275">클래스 및 모듈 멤버 변수 (외부 프로시저)는 기본적으로 개인 액세스 및 구조 멤버 변수는 기본적으로 공용 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-275">Class and module member variables (outside any procedure) default to private access, and structure member variables default to public access.</span></span> <span data-ttu-id="dffdd-276">액세스 한정자로 액세스 수준을 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-276">You can adjust their access levels with the access modifiers.</span></span> <span data-ttu-id="dffdd-277">프로시저의 경우) (내 지역 변수에 액세스 한정자를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-277">You cannot use access modifiers on local variables (inside a procedure).</span></span>  
  
 <span data-ttu-id="dffdd-278">지정할 수 있습니다 `WithEvents` 만 멤버 변수 아니라에 프로시저 내의 지역 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-278">You can specify `WithEvents` only on member variables, not on local variables inside a procedure.</span></span> <span data-ttu-id="dffdd-279">지정 하는 경우 `WithEvents`, 변수의 데이터 형식을 특정 클래스 형식에 해제 해야 `Object`합니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-279">If you specify `WithEvents`, the data type of the variable must be a specific class type, not `Object`.</span></span> <span data-ttu-id="dffdd-280">배열을 선언할 수 없습니다 `WithEvents`합니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-280">You cannot declare an array with `WithEvents`.</span></span> <span data-ttu-id="dffdd-281">이벤트에 대 한 자세한 내용은 참조 [이벤트](../../../visual-basic/programming-guide/language-features/events/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-281">For more information about events, see [Events](../../../visual-basic/programming-guide/language-features/events/index.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dffdd-282">코드 클래스 외부에서는 또는 모듈 멤버 변수의 이름을 정해야 해당 클래스, 구조체, 모듈의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-282">Code outside a class, structure, or module must qualify a member variable's name with the name of that class, structure, or module.</span></span> <span data-ttu-id="dffdd-283">해당 프로시저 또는 블록 내에서 지역 변수를 참조할 수 없습니다 프로시저 또는 블록 외부에 있는 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-283">Code outside a procedure or block cannot refer to any local variables within that procedure or block.</span></span>  
  
## <a name="releasing-managed-resources"></a><span data-ttu-id="dffdd-284">관리 되는 리소스를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-284">Releasing Managed Resources</span></span>  
 <span data-ttu-id="dffdd-285">.NET Framework 가비지 수집기가 사용자의 추가 코딩 없이도 관리 되는 리소스를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-285">The .NET Framework garbage collector disposes of managed resources without any extra coding on your part.</span></span> <span data-ttu-id="dffdd-286">그러나 가비지 수집기가 대기 하는 대신 관리 되는 리소스의 처리를 강제로 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-286">However, you can force the disposal of a managed resource instead of waiting for the garbage collector.</span></span>  
  
 <span data-ttu-id="dffdd-287">클래스에는 특히 중요 하 고 부족 한 리소스 (예: 데이터베이스 연결 또는 파일 핸들)을 갖는 경우는 더 이상 사용에서 하는 클래스 인스턴스를 정리 하는 다음 가비지 수집 될 때까지 대기 하지 않을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-287">If a class holds onto a particularly valuable and scarce resource (such as a database connection or file handle), you might not want to wait until the next garbage collection to clean up a class instance that's no longer in use.</span></span> <span data-ttu-id="dffdd-288">클래스를 구현할 수는 <xref:System.IDisposable>가비지 수집을 하기 전에 리소스를 해제 하는 방법을 제공 하는 인터페이스입니다.</xref:System.IDisposable></span><span class="sxs-lookup"><span data-stu-id="dffdd-288">A class may implement the <xref:System.IDisposable> interface to provide a way to release resources before a garbage collection.</span></span> <span data-ttu-id="dffdd-289">해당 인터페이스를 구현 하는 클래스를 노출 한 `Dispose` 강제로 즉시 출시 될 중요 한 리소스를 호출할 수 있는 메서드.</span><span class="sxs-lookup"><span data-stu-id="dffdd-289">A class that implements that interface exposes a `Dispose` method that can be called to force valuable resources to be released immediately.</span></span>  
  
 <span data-ttu-id="dffdd-290">`Using` 리소스 확보, 문 집합을 실행 한 다음 리소스를 삭제 하는 프로세스를 자동화 하는 문입니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-290">The `Using` statement automates the process of acquiring a resource, executing a set of statements, and then disposing of the resource.</span></span> <span data-ttu-id="dffdd-291">그러나 리소스를 구현 해야는 <xref:System.IDisposable>인터페이스.</xref:System.IDisposable></span><span class="sxs-lookup"><span data-stu-id="dffdd-291">However, the resource must implement the <xref:System.IDisposable> interface.</span></span> <span data-ttu-id="dffdd-292">자세한 내용은 참조 [문을 사용 하 여](../../../visual-basic/language-reference/statements/using-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-292">For more information, see [Using Statement](../../../visual-basic/language-reference/statements/using-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="dffdd-293">예제</span><span class="sxs-lookup"><span data-stu-id="dffdd-293">Example</span></span>  
 <span data-ttu-id="dffdd-294">다음 예제에서는 변수를 사용 하 여 선언 된 `Dim` 다양 한 옵션을 사용 하 여 문을 합니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-294">The following example declares variables by using the `Dim` statement with various options.</span></span>  
  
 <span data-ttu-id="dffdd-295">[!code-vb[VbVbalrStatements #&141;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/dim-statement_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="dffdd-295">[!code-vb[VbVbalrStatements#141](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/dim-statement_1.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="dffdd-296">예제</span><span class="sxs-lookup"><span data-stu-id="dffdd-296">Example</span></span>  
 <span data-ttu-id="dffdd-297">다음 예제에서는 1에서 30 사이의 소수를 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-297">The following example lists the prime numbers between 1 and 30.</span></span> <span data-ttu-id="dffdd-298">지역 변수의 범위는 코드 주석에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-298">The scope of local variables is described in code comments.</span></span>  
  
 <span data-ttu-id="dffdd-299">[!code-vb[VbVbalrStatements #&142;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/dim-statement_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="dffdd-299">[!code-vb[VbVbalrStatements#142](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/dim-statement_2.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="dffdd-300">예제</span><span class="sxs-lookup"><span data-stu-id="dffdd-300">Example</span></span>  
 <span data-ttu-id="dffdd-301">다음 예제에서는 `speedValue` 변수는 클래스 수준에서 선언 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-301">In the following example, the `speedValue` variable is declared at the class level.</span></span> <span data-ttu-id="dffdd-302">`Private` 키워드는 변수를 선언 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-302">The `Private` keyword is used to declare the variable.</span></span> <span data-ttu-id="dffdd-303">모든 프로시저에서 변수를 액세스할 수는 `Car` 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="dffdd-303">The variable can be accessed by any procedure in the `Car` class.</span></span>  
  
 <span data-ttu-id="dffdd-304">[!code-vb[VbVbalrStatements #&144;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/dim-statement_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="dffdd-304">[!code-vb[VbVbalrStatements#144](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/dim-statement_3.vb)]</span></span>  
  
 <span data-ttu-id="dffdd-305">[!code-vb[VbVbalrStatements #&145;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/dim-statement_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="dffdd-305">[!code-vb[VbVbalrStatements#145](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/dim-statement_4.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dffdd-306">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dffdd-306">See Also</span></span>  
 <span data-ttu-id="dffdd-307">[Const 문](../../../visual-basic/language-reference/statements/const-statement.md) </span><span class="sxs-lookup"><span data-stu-id="dffdd-307">[Const Statement](../../../visual-basic/language-reference/statements/const-statement.md) </span></span>  
<span data-ttu-id="dffdd-308"> [ReDim 문](../../../visual-basic/language-reference/statements/redim-statement.md) </span><span class="sxs-lookup"><span data-stu-id="dffdd-308"> [ReDim Statement](../../../visual-basic/language-reference/statements/redim-statement.md) </span></span>  
<span data-ttu-id="dffdd-309"> [Option Explicit 문](../../../visual-basic/language-reference/statements/option-explicit-statement.md) </span><span class="sxs-lookup"><span data-stu-id="dffdd-309"> [Option Explicit Statement](../../../visual-basic/language-reference/statements/option-explicit-statement.md) </span></span>  
<span data-ttu-id="dffdd-310"> [Option Infer 문](../../../visual-basic/language-reference/statements/option-infer-statement.md) </span><span class="sxs-lookup"><span data-stu-id="dffdd-310"> [Option Infer Statement](../../../visual-basic/language-reference/statements/option-infer-statement.md) </span></span>  
<span data-ttu-id="dffdd-311"> [Option Strict 문](../../../visual-basic/language-reference/statements/option-strict-statement.md) </span><span class="sxs-lookup"><span data-stu-id="dffdd-311"> [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md) </span></span>  
<span data-ttu-id="dffdd-312"> [프로젝트 디자이너, 컴파일 페이지(Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/compile-page-project-designer-visual-basic) </span><span class="sxs-lookup"><span data-stu-id="dffdd-312"> [Compile Page, Project Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/compile-page-project-designer-visual-basic) </span></span>  
<span data-ttu-id="dffdd-313"> [변수 선언](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md) </span><span class="sxs-lookup"><span data-stu-id="dffdd-313"> [Variable Declaration](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md) </span></span>  
<span data-ttu-id="dffdd-314"> [배열](../../../visual-basic/programming-guide/language-features/arrays/index.md) </span><span class="sxs-lookup"><span data-stu-id="dffdd-314"> [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md) </span></span>  
<span data-ttu-id="dffdd-315"> [개체 이니셜라이저: 명명 된 형식과 익명 형식](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md) </span><span class="sxs-lookup"><span data-stu-id="dffdd-315"> [Object Initializers: Named and Anonymous Types](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md) </span></span>  
<span data-ttu-id="dffdd-316"> [익명 형식](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md) </span><span class="sxs-lookup"><span data-stu-id="dffdd-316"> [Anonymous Types](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md) </span></span>  
<span data-ttu-id="dffdd-317"> [개체 이니셜라이저: 명명 된 형식과 익명 형식](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md) </span><span class="sxs-lookup"><span data-stu-id="dffdd-317"> [Object Initializers: Named and Anonymous Types](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md) </span></span>  
<span data-ttu-id="dffdd-318"> [방법: 개체 이니셜라이저를 사용 하 여 개체 선언](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md) </span><span class="sxs-lookup"><span data-stu-id="dffdd-318"> [How to: Declare an Object by Using an Object Initializer](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md) </span></span>  
<span data-ttu-id="dffdd-319"> [지역 형식 유추](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)</span><span class="sxs-lookup"><span data-stu-id="dffdd-319"> [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)</span></span>

