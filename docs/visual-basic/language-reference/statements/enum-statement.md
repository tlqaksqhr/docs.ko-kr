---
title: Enum 문(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Enum
helpviewer_keywords:
- enumerated constants [Visual Basic]
- Enum statement [Visual Basic]
- Private keyword [Visual Basic], Enum statements
- Public keyword [Visual Basic], in Enum statement
- variables [Visual Basic], enumeration
- constants [Visual Basic], enumerated
ms.assetid: a45e51f1-65ff-48e1-bf32-79130f137377
ms.openlocfilehash: 7cac4d5bde9ec617a1877a0605dc6dbab67ddf7f
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/17/2018
ms.locfileid: "34234018"
---
# <a name="enum-statement-visual-basic"></a><span data-ttu-id="94f76-102">Enum 문(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="94f76-102">Enum Statement (Visual Basic)</span></span>
<span data-ttu-id="94f76-103">열거형을 선언 하 고 해당 멤버의 값을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="94f76-103">Declares an enumeration and defines the values of its members.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94f76-104">구문</span><span class="sxs-lookup"><span data-stu-id="94f76-104">Syntax</span></span>  
  
```  
[ <attributelist> ] [ accessmodifier ]  [ Shadows ]   
Enum enumerationname [ As datatype ]   
   memberlist  
End Enum  
```  
  
## <a name="parts"></a><span data-ttu-id="94f76-105">요소</span><span class="sxs-lookup"><span data-stu-id="94f76-105">Parts</span></span>  
  
-   `attributelist`  
  
     <span data-ttu-id="94f76-106">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="94f76-106">Optional.</span></span> <span data-ttu-id="94f76-107">이 열거형에 적용 되는 특성 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="94f76-107">List of attributes that apply to this enumeration.</span></span> <span data-ttu-id="94f76-108">묶어야는 [특성 목록](../../../visual-basic/language-reference/statements/attribute-list.md) 꺾쇠 괄호에서 ("`<`"및"`>`").</span><span class="sxs-lookup"><span data-stu-id="94f76-108">You must enclose the [attribute list](../../../visual-basic/language-reference/statements/attribute-list.md) in angle brackets ("`<`" and "`>`").</span></span>  
  
     <span data-ttu-id="94f76-109"><xref:System.FlagsAttribute> 열거형의 인스턴스 값이 여러 열거형 멤버를 포함할 수 있으며, 각 멤버는 열거형 값의 비트 필드를 나타내는 특성을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="94f76-109">The <xref:System.FlagsAttribute> attribute indicates that the value of an instance of the enumeration can include multiple enumeration members, and that each member represents a bit field in the enumeration value.</span></span>  
  
-   `accessmodifier`  
  
     <span data-ttu-id="94f76-110">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="94f76-110">Optional.</span></span> <span data-ttu-id="94f76-111">이 열거형에 액세스할 수 있는 코드를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="94f76-111">Specifies what code can access this enumeration.</span></span> <span data-ttu-id="94f76-112">다음 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94f76-112">Can be one of the following:</span></span>  
  
    -   [<span data-ttu-id="94f76-113">공용</span><span class="sxs-lookup"><span data-stu-id="94f76-113">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
  
    -   [<span data-ttu-id="94f76-114">보호됨</span><span class="sxs-lookup"><span data-stu-id="94f76-114">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)  
  
    -   [<span data-ttu-id="94f76-115">Friend</span><span class="sxs-lookup"><span data-stu-id="94f76-115">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)  
  
    -   [<span data-ttu-id="94f76-116">전용</span><span class="sxs-lookup"><span data-stu-id="94f76-116">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)  
  
    - [<span data-ttu-id="94f76-117">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="94f76-117">Protected Friend</span></span>](../../language-reference/modifiers/protected-friend.md)
    
    - [<span data-ttu-id="94f76-118">보호 된 개인</span><span class="sxs-lookup"><span data-stu-id="94f76-118">Private Protected</span></span>](../../language-reference/modifiers/private-protected.md)

-   `Shadows`  
  
     <span data-ttu-id="94f76-119">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="94f76-119">Optional.</span></span> <span data-ttu-id="94f76-120">이 열거형의 동일 하 게 명명 된 프로그래밍 요소 또는 기본 클래스에서 오버 로드 된 요소 집합을 다시 선언 하 고 숨기도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="94f76-120">Specifies that this enumeration redeclares and hides an identically named programming element, or set of overloaded elements, in a base class.</span></span> <span data-ttu-id="94f76-121">지정할 수 있습니다 [그림자](../../../visual-basic/language-reference/modifiers/shadows.md) 열거형 자체에 대해서만, 해당 멤버 중 하나에 없는 합니다.</span><span class="sxs-lookup"><span data-stu-id="94f76-121">You can specify [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md) only on the enumeration itself, not on any of its members.</span></span>  
  
-   `enumerationname`  
  
     <span data-ttu-id="94f76-122">필수.</span><span class="sxs-lookup"><span data-stu-id="94f76-122">Required.</span></span> <span data-ttu-id="94f76-123">열거형의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="94f76-123">Name of the enumeration.</span></span> <span data-ttu-id="94f76-124">올바른 이름에 대 한 정보를 참조 하십시오. [선언 요소 이름](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="94f76-124">For information on valid names, see [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
-   `datatype`  
  
     <span data-ttu-id="94f76-125">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="94f76-125">Optional.</span></span> <span data-ttu-id="94f76-126">열거형 및 모든 해당 멤버의 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="94f76-126">Data type of the enumeration and all its members.</span></span>  
  
-   `memberlist`  
  
     <span data-ttu-id="94f76-127">필수.</span><span class="sxs-lookup"><span data-stu-id="94f76-127">Required.</span></span> <span data-ttu-id="94f76-128">이 문에서 선언 되는 멤버 상수 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="94f76-128">List of member constants being declared in this statement.</span></span> <span data-ttu-id="94f76-129">여러 멤버 개별 소스 코드 줄에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="94f76-129">Multiple members appear on individual source code lines.</span></span>  
  
     <span data-ttu-id="94f76-130">각 `member` 다음 구문과 구성 요소는: `[<attribute list>] member name [ = initializer ]`</span><span class="sxs-lookup"><span data-stu-id="94f76-130">Each `member` has the following syntax and parts: `[<attribute list>] member name [ = initializer ]`</span></span>  
  
    |<span data-ttu-id="94f76-131">파트</span><span class="sxs-lookup"><span data-stu-id="94f76-131">Part</span></span>|<span data-ttu-id="94f76-132">설명</span><span class="sxs-lookup"><span data-stu-id="94f76-132">Description</span></span>|  
    |---|---|  
    |`membername`|<span data-ttu-id="94f76-133">필수.</span><span class="sxs-lookup"><span data-stu-id="94f76-133">Required.</span></span> <span data-ttu-id="94f76-134">이 멤버의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="94f76-134">Name of this member.</span></span>|  
    |`initializer`|<span data-ttu-id="94f76-135">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="94f76-135">Optional.</span></span> <span data-ttu-id="94f76-136">컴파일 타임에 계산 되 고이 멤버에 할당 되는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="94f76-136">Expression that is evaluated at compile time and assigned to this member.</span></span>|  
  
-   <span data-ttu-id="94f76-137">`End` `Enum`</span><span class="sxs-lookup"><span data-stu-id="94f76-137">`End` `Enum`</span></span>  
  
     <span data-ttu-id="94f76-138">`Enum` 블록을 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="94f76-138">Terminates the `Enum` block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="94f76-139">설명</span><span class="sxs-lookup"><span data-stu-id="94f76-139">Remarks</span></span>  
 <span data-ttu-id="94f76-140">서로 논리적으로 관련 된 변경 되지 않는 값 집합이 있는 경우 정의할 수 있습니다 이러한 함께 열거형에서입니다.</span><span class="sxs-lookup"><span data-stu-id="94f76-140">If you have a set of unchanging values that are logically related to each other, you can define them together in an enumeration.</span></span> <span data-ttu-id="94f76-141">이 열거형과 해당 값 보다 쉽게 기억할 수 있는 해당 멤버에 대 한 의미 있는 이름을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="94f76-141">This provides meaningful names for the enumeration and its members, which are easier to remember than their values.</span></span> <span data-ttu-id="94f76-142">다음 코드의 여러 위치에서 열거형 멤버를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94f76-142">You can then use the enumeration members in many places in your code.</span></span>  
  
 <span data-ttu-id="94f76-143">열거형을 사용할 때의 이점은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="94f76-143">The benefits of using enumerations include the following:</span></span>  
  
-   <span data-ttu-id="94f76-144">숫자를 잘못 입력 하 여 발생 하는 오류를 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94f76-144">Reduces errors caused by transposing or mistyping numbers.</span></span>  
  
-   <span data-ttu-id="94f76-145">나중에 값을 변경 하려면 쉽게 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94f76-145">Makes it easy to change values in the future.</span></span>  
  
-   <span data-ttu-id="94f76-146">에서는 확률이 오류를 도입 될 것 이므로 코드를 쉽게 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94f76-146">Makes code easier to read, which means it is less likely that errors will be introduced.</span></span>  
  
-   <span data-ttu-id="94f76-147">다음 버전과 호환성을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="94f76-147">Ensures forward compatibility.</span></span> <span data-ttu-id="94f76-148">열거형을 사용 하면 코드를 나중에 멤버 이름에 해당 하는 값 변경 되 면 실패할 가능성이 적습니다.</span><span class="sxs-lookup"><span data-stu-id="94f76-148">If you use enumerations, your code is less likely to fail if in the future someone changes the values corresponding to the member names.</span></span>  
  
 <span data-ttu-id="94f76-149">열거형에는 이름는 기본 데이터 형식 및 멤버의 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="94f76-149">An enumeration has a name, an underlying data type, and a set of members.</span></span> <span data-ttu-id="94f76-150">각 멤버는 상수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="94f76-150">Each member represents a constant.</span></span>  
  
 <span data-ttu-id="94f76-151">클래스, 구조체, 모듈 또는 인터페이스 수준에서 모든 프로시저 외부에서 선언 하는 열거형은는 *멤버 열거형*합니다.</span><span class="sxs-lookup"><span data-stu-id="94f76-151">An enumeration declared at class, structure, module, or interface level, outside any procedure, is a *member enumeration*.</span></span> <span data-ttu-id="94f76-152">클래스, 구조체, 모듈 또는 이벤트를 선언 하는 인터페이스의 멤버는</span><span class="sxs-lookup"><span data-stu-id="94f76-152">It is a member of the class, structure, module, or interface that declares it.</span></span>  
  
 <span data-ttu-id="94f76-153">멤버 열거형에서 액세스할 수 있습니다 아무 곳 이나 해당 클래스, 구조체, 모듈 또는 인터페이스 내에서.</span><span class="sxs-lookup"><span data-stu-id="94f76-153">Member enumerations can be accessed from anywhere within their class, structure, module, or interface.</span></span> <span data-ttu-id="94f76-154">코드는 클래스 외부 또는 모듈 이름을 한 정해야 멤버 열거형의 해당 클래스, 구조체 또는 모듈의 이름으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="94f76-154">Code outside a class, structure, or module must qualify a member enumeration's name with the name of that class, structure, or module.</span></span> <span data-ttu-id="94f76-155">정규화 된 이름을 추가 하 여 사용할 필요가 방지할 수 있습니다는 [Imports](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) 문을 소스 파일에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94f76-155">You can avoid the need to use fully qualified names by adding an [Imports](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) statement to the source file.</span></span>  
  
 <span data-ttu-id="94f76-156">클래스, 구조체, 모듈 또는 인터페이스를 외부 네임 스페이스 수준에서 선언 되는 열거형은 표시 되는 네임 스페이스의 멤버입니다.</span><span class="sxs-lookup"><span data-stu-id="94f76-156">An enumeration declared at namespace level, outside any class, structure, module, or interface, is a member of the namespace in which it appears.</span></span>  
  
 <span data-ttu-id="94f76-157">*선언 컨텍스트* 열거형 소스 파일, 네임 스페이스, 클래스, 구조체, 모듈 또는 인터페이스를 이어야 하며 프로시저일 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="94f76-157">The *declaration context* for an enumeration must be a source file, namespace, class, structure, module, or interface, and cannot be a procedure.</span></span> <span data-ttu-id="94f76-158">자세한 내용은 [선언 컨텍스트 및 기본 액세스 수준](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="94f76-158">For more information, see [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>  
  
 <span data-ttu-id="94f76-159">특성 적용을 전체적으로 열거형에 속하지만 해당 멤버에 개별적으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="94f76-159">You can apply attributes to an enumeration as a whole, but not to its members individually.</span></span> <span data-ttu-id="94f76-160">특성에는 어셈블리의 메타 데이터에 정보를 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="94f76-160">An attribute contributes information to the assembly's metadata.</span></span>  
  
## <a name="data-type"></a><span data-ttu-id="94f76-161">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="94f76-161">Data Type</span></span>  
 <span data-ttu-id="94f76-162">`Enum` 문은 데이터 형식의 열거형을 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94f76-162">The `Enum` statement can declare the data type of an enumeration.</span></span> <span data-ttu-id="94f76-163">각 멤버에는 열거형의 데이터 형식을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="94f76-163">Each member takes the enumeration's data type.</span></span> <span data-ttu-id="94f76-164">지정할 수 있습니다 `Byte`, `Integer`, `Long`, `SByte`, `Short`, `UInteger`, `ULong`, 또는 `UShort`합니다.</span><span class="sxs-lookup"><span data-stu-id="94f76-164">You can specify `Byte`, `Integer`, `Long`, `SByte`, `Short`, `UInteger`, `ULong`, or `UShort`.</span></span>  
  
 <span data-ttu-id="94f76-165">지정 하지 않으면 `datatype` 열거형에 대 한 각 멤버는 변수의 데이터 형식을 해당 `initializer`합니다.</span><span class="sxs-lookup"><span data-stu-id="94f76-165">If you do not specify `datatype` for the enumeration, each member takes the data type of its `initializer`.</span></span> <span data-ttu-id="94f76-166">모두 지정 하면 `datatype` 및 `initializer`의 데이터 형식이 `initializer` 변환할 수 있어야 `datatype`합니다.</span><span class="sxs-lookup"><span data-stu-id="94f76-166">If you specify both `datatype` and `initializer`, the data type of `initializer` must be convertible to `datatype`.</span></span> <span data-ttu-id="94f76-167">모두 `datatype` 나 `initializer` 가 있는 경우 데이터 형식의 기본값으로 `Integer`합니다.</span><span class="sxs-lookup"><span data-stu-id="94f76-167">If neither `datatype` nor `initializer` is present, the data type defaults to `Integer`.</span></span>  
  
## <a name="initializing-members"></a><span data-ttu-id="94f76-168">멤버 초기화</span><span class="sxs-lookup"><span data-stu-id="94f76-168">Initializing Members</span></span>  
 <span data-ttu-id="94f76-169">`Enum` 문을에서 선택한 멤버의 내용을 초기화할 수 `memberlist`합니다.</span><span class="sxs-lookup"><span data-stu-id="94f76-169">The `Enum` statement can initialize the contents of selected members in `memberlist`.</span></span> <span data-ttu-id="94f76-170">사용 하면 `initializer` 멤버에 할당 하는 식을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94f76-170">You use `initializer` to supply an expression to be assigned to the member.</span></span>  
  
 <span data-ttu-id="94f76-171">지정 하지 않으면 `initializer` 멤버에 대 한 Visual Basic 초기화을 0 (첫 번째 경우 `member` 에 `memberlist`), 또는 바로 앞의 보다 1 큰 값으로 `member`합니다.</span><span class="sxs-lookup"><span data-stu-id="94f76-171">If you do not specify `initializer` for a member, Visual Basic initializes it either to zero (if it is the first `member` in `memberlist`), or to a value greater by one than that of the immediately preceding `member`.</span></span>  
  
 <span data-ttu-id="94f76-172">각각에 지정 된 식은 `initializer` 리터럴, 이미 정의 되어 있는 다른 상수 이미 정의 된이 열거형의 이전 멤버를 포함 하 여 열거형 멤버의 조합이 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94f76-172">The expression supplied in each `initializer` can be any combination of literals, other constants that are already defined, and enumeration members that are already defined, including a previous member of this enumeration.</span></span> <span data-ttu-id="94f76-173">이러한 요소를 결합 하 산술 및 논리 연산자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94f76-173">You can use arithmetic and logical operators to combine such elements.</span></span>  
  
 <span data-ttu-id="94f76-174">변수 또는 함수에서 사용할 수 없습니다 `initializer`합니다.</span><span class="sxs-lookup"><span data-stu-id="94f76-174">You cannot use variables or functions in `initializer`.</span></span> <span data-ttu-id="94f76-175">그러나와 같은 변환 키워드를 사용할 수는 `CByte` 및 `CShort`합니다.</span><span class="sxs-lookup"><span data-stu-id="94f76-175">However, you can use conversion keywords such as `CByte` and `CShort`.</span></span> <span data-ttu-id="94f76-176">사용할 수도 있습니다 `AscW` 상수와 호출 하는 경우 `String` 또는 `Char` 인수를 컴파일 타임에 계산 될 수 있으므로 합니다.</span><span class="sxs-lookup"><span data-stu-id="94f76-176">You can also use `AscW` if you call it with a constant `String` or `Char` argument, since that can be evaluated at compile time.</span></span>  
  
 <span data-ttu-id="94f76-177">열거형 부동 소수점 값을 가질 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="94f76-177">Enumerations cannot have floating-point values.</span></span> <span data-ttu-id="94f76-178">멤버에 부동 소수점 값이 할당 하는 경우 및 `Option Strict` 컴파일러 오류가 발생 한 on으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="94f76-178">If a member is assigned a floating-point value and `Option Strict` is set to on, a compiler error occurs.</span></span> <span data-ttu-id="94f76-179">경우 `Option Strict` 에 자동으로 변환 된 값은 off는 `Enum` 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="94f76-179">If `Option Strict` is off, the value is automatically converted to the `Enum` type.</span></span>  
  
 <span data-ttu-id="94f76-180">기본 데이터 형식에 대 한 허용 범위를 초과 하는 멤버의 값 또는 멤버를 기본 데이터 형식에서 허용 되는 최대값을 초기화 하는 경우 컴파일러가 오류를 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="94f76-180">If the value of a member exceeds the allowable range for the underlying data type, or if you initialize any member to the maximum value allowed by the underlying data type, the compiler reports an error.</span></span>  
  
## <a name="modifiers"></a><span data-ttu-id="94f76-181">한정자</span><span class="sxs-lookup"><span data-stu-id="94f76-181">Modifiers</span></span>  
 <span data-ttu-id="94f76-182">클래스, 구조체, 모듈 및 인터페이스 멤버 열거는 기본적으로 공용 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="94f76-182">Class, structure, module, and interface member enumerations default to public access.</span></span> <span data-ttu-id="94f76-183">액세스 한정자로 액세스 수준을 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94f76-183">You can adjust their access levels with the access modifiers.</span></span> <span data-ttu-id="94f76-184">Namespace 멤버 열거는 기본적으로 friend 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="94f76-184">Namespace member enumerations default to friend access.</span></span> <span data-ttu-id="94f76-185">Public에 속하지만에 private 또는 protected 액세스 수준을 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94f76-185">You can adjust their access levels to public, but not to private or protected.</span></span> <span data-ttu-id="94f76-186">자세한 내용은 참조 [액세스 수준을 Visual Basic의](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="94f76-186">For more information, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 <span data-ttu-id="94f76-187">모든 열거형 멤버는 공용 액세스 있고에 액세스 한정자를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="94f76-187">All enumeration members have public access, and you cannot use any access modifiers on them.</span></span> <span data-ttu-id="94f76-188">그러나 해당 열거형에 좀 더 제한 된 액세스 수준이 있는 경우 지정 된 열거형의 액세스 수준이 우선 합니다.</span><span class="sxs-lookup"><span data-stu-id="94f76-188">However, if the enumeration itself has a more restricted access level, the specified enumeration access level takes precedence.</span></span>  
  
 <span data-ttu-id="94f76-189">기본적으로 모든 열거형 형식이 며 해당 필드는 상수입니다.</span><span class="sxs-lookup"><span data-stu-id="94f76-189">By default, all enumerations are types and their fields are constants.</span></span> <span data-ttu-id="94f76-190">따라서는 `Shared`, `Static`, 및 `ReadOnly` 열거형 또는 해당 멤버를 선언 하는 경우에 키워드를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="94f76-190">Therefore the `Shared`, `Static`, and `ReadOnly` keywords cannot be used when declaring an enumeration or its members.</span></span>  
  
## <a name="assigning-multiple-values"></a><span data-ttu-id="94f76-191">여러 값 할당</span><span class="sxs-lookup"><span data-stu-id="94f76-191">Assigning Multiple Values</span></span>  
 <span data-ttu-id="94f76-192">일반적으로 열거형 상호 배타적인 값을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="94f76-192">Enumerations typically represent mutually exclusive values.</span></span> <span data-ttu-id="94f76-193">포함 하 여는 <xref:System.FlagsAttribute> 특성에 `Enum` 선언 대신 값을 할당할 수 여러 열거형의 인스턴스에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94f76-193">By including the <xref:System.FlagsAttribute> attribute in the `Enum` declaration, you can instead assign multiple values to an instance of the enumeration.</span></span> <span data-ttu-id="94f76-194"><xref:System.FlagsAttribute> 특성 열거형 비트 필드 즉, 플래그 집합으로 처리할 수 있음을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="94f76-194">The <xref:System.FlagsAttribute> attribute specifies that the enumeration be treated as a bit field, that is, a set of flags.</span></span> <span data-ttu-id="94f76-195">이 라고 *비트* 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="94f76-195">These are called *bitwise* enumerations.</span></span>  
  
 <span data-ttu-id="94f76-196">사용 하 여 열거형을 선언할 때는 <xref:System.FlagsAttribute> 특성을 권장 되는 2, 1, 2, 4, 8, 16, 및 등의 거듭제곱을 사용 하 여 값에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="94f76-196">When you declare an enumeration by using the <xref:System.FlagsAttribute> attribute, we recommend that you use powers of 2, that is, 1, 2, 4, 8, 16, and so on, for the values.</span></span> <span data-ttu-id="94f76-197">또한 값이 0 인 멤버의 이름을 "None" 된다는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="94f76-197">We also recommend that "None" be the name of a member whose value is 0.</span></span> <span data-ttu-id="94f76-198">추가 지침에 대 한 참조 <xref:System.FlagsAttribute> 및 <xref:System.Enum>합니다.</span><span class="sxs-lookup"><span data-stu-id="94f76-198">For additional guidelines, see <xref:System.FlagsAttribute> and <xref:System.Enum>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="94f76-199">예제</span><span class="sxs-lookup"><span data-stu-id="94f76-199">Example</span></span>  
 <span data-ttu-id="94f76-200">사용 하는 방법을 보여 주는 다음 예제는 `Enum` 문.</span><span class="sxs-lookup"><span data-stu-id="94f76-200">The following example shows how to use the `Enum` statement.</span></span> <span data-ttu-id="94f76-201">멤버 라고는 `EggSizeEnum.Medium`, 아니라 `Medium`합니다.</span><span class="sxs-lookup"><span data-stu-id="94f76-201">Note that the member is referred to as `EggSizeEnum.Medium`, and not as `Medium`.</span></span>  
  
 [!code-vb[VbEnumsTask#41](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="94f76-202">예제</span><span class="sxs-lookup"><span data-stu-id="94f76-202">Example</span></span>  
 <span data-ttu-id="94f76-203">다음 예제에서 메서드는 외부에서 `Egg` 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="94f76-203">The method in the following example is outside the `Egg` class.</span></span> <span data-ttu-id="94f76-204">따라서 `EggSizeEnum` 으로 정규화 `Egg.EggSizeEnum`합니다.</span><span class="sxs-lookup"><span data-stu-id="94f76-204">Therefore, `EggSizeEnum` is fully qualified as `Egg.EggSizeEnum`.</span></span>  
  
 [!code-vb[VbEnumsTask#42](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_2.vb)]  
  
## <a name="example"></a><span data-ttu-id="94f76-205">예제</span><span class="sxs-lookup"><span data-stu-id="94f76-205">Example</span></span>  
 <span data-ttu-id="94f76-206">다음 예제에서는 `Enum` 명명 된 상수 값을 관련된 된 집합을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="94f76-206">The following example uses the `Enum` statement to define a related set of named constant values.</span></span> <span data-ttu-id="94f76-207">이 경우 값은 색 데이터베이스에 대 한 데이터 입력 폼을 설계할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94f76-207">In this case, the values are colors you might choose to design data entry forms for a database.</span></span>  
  
 [!code-vb[VbEnumsTask#30](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_3.vb)]  
  
## <a name="example"></a><span data-ttu-id="94f76-208">예제</span><span class="sxs-lookup"><span data-stu-id="94f76-208">Example</span></span>  
 <span data-ttu-id="94f76-209">다음 예에서는 양수 및 음수를 포함 하는 값을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="94f76-209">The following example shows values that include both positive and negative numbers.</span></span>  
  
 [!code-vb[VbEnumsTask#31](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_4.vb)]  
  
## <a name="example"></a><span data-ttu-id="94f76-210">예제</span><span class="sxs-lookup"><span data-stu-id="94f76-210">Example</span></span>  
 <span data-ttu-id="94f76-211">다음 예제에서는 `As` 절을 사용 하 여 지정 하는 `datatype` 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="94f76-211">In the following example, an `As` clause is used to specify the `datatype` of an enumeration.</span></span>  
  
 [!code-vb[VbEnumsTask#6](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_5.vb)]  
  
## <a name="example"></a><span data-ttu-id="94f76-212">예제</span><span class="sxs-lookup"><span data-stu-id="94f76-212">Example</span></span>  
 <span data-ttu-id="94f76-213">다음 예제에서는 비트 열거형을 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="94f76-213">The following example shows how to use a bitwise enumeration.</span></span> <span data-ttu-id="94f76-214">여러 값의 비트 열거형 인스턴스에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94f76-214">Multiple values can be assigned to an instance of a bitwise enumeration.</span></span> <span data-ttu-id="94f76-215">`Enum` 선언 포함 되어는 <xref:System.FlagsAttribute> 특성 열거형 플래그 집합으로 처리할 수 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="94f76-215">The `Enum` declaration includes the <xref:System.FlagsAttribute> attribute, which indicates that the enumeration can be treated as a set of flags.</span></span>  
  
 [!code-vb[VbEnumsTask#61](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_6.vb)]  
  
## <a name="example"></a><span data-ttu-id="94f76-216">예제</span><span class="sxs-lookup"><span data-stu-id="94f76-216">Example</span></span>  
 <span data-ttu-id="94f76-217">다음 예제에서는 열거형을 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="94f76-217">The following example iterates through an enumeration.</span></span> <span data-ttu-id="94f76-218">사용 하 여는 <xref:System.Enum.GetNames%2A> 열거형의 멤버 이름의 배열을 검색 하는 메서드 및 <xref:System.Enum.GetValues%2A> 멤버 값의 배열을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="94f76-218">It uses the <xref:System.Enum.GetNames%2A> method to retrieve an array of member names from the enumeration, and <xref:System.Enum.GetValues%2A> to retrieve an array of member values.</span></span>  
  
 [!code-vb[VbEnumsTask#51](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_7.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="94f76-219">참고 항목</span><span class="sxs-lookup"><span data-stu-id="94f76-219">See Also</span></span>  
 <xref:System.Enum>  
 <xref:Microsoft.VisualBasic.Strings.AscW%2A>  
 [<span data-ttu-id="94f76-220">Const 문</span><span class="sxs-lookup"><span data-stu-id="94f76-220">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
 [<span data-ttu-id="94f76-221">Dim 문</span><span class="sxs-lookup"><span data-stu-id="94f76-221">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
 [<span data-ttu-id="94f76-222">암시적 변환과 명시적 변환</span><span class="sxs-lookup"><span data-stu-id="94f76-222">Implicit and Explicit Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 [<span data-ttu-id="94f76-223">형식 변환 함수</span><span class="sxs-lookup"><span data-stu-id="94f76-223">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="94f76-224">상수 및 열거형</span><span class="sxs-lookup"><span data-stu-id="94f76-224">Constants and Enumerations</span></span>](../../../visual-basic/language-reference/constants-and-enumerations.md)
