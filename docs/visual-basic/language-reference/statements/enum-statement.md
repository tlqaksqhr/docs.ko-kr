---
title: "Enum 문 (Visual Basic) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Enum
dev_langs:
- VB
helpviewer_keywords:
- enumerated constants
- Enum statement
- Private keyword, Enum statements
- Public keyword, in Enum statement
- variables [Visual Basic], enumeration
- constants, enumerated
ms.assetid: a45e51f1-65ff-48e1-bf32-79130f137377
caps.latest.revision: 44
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
ms.openlocfilehash: ff075349756bd4c568833d049b50b3c3721d1b08
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="enum-statement-visual-basic"></a><span data-ttu-id="65ca5-102">Enum 문(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="65ca5-102">Enum Statement (Visual Basic)</span></span>
<span data-ttu-id="65ca5-103">열거형을 선언하고 열거형의 멤버 값을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="65ca5-103">Declares an enumeration and defines the values of its members.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65ca5-104">구문</span><span class="sxs-lookup"><span data-stu-id="65ca5-104">Syntax</span></span>  
  
```  
[ <attributelist> ] [ accessmodifier ]  [ Shadows ]   
Enum enumerationname [ As datatype ]   
   memberlist  
End Enum  
```  
  
## <a name="parts"></a><span data-ttu-id="65ca5-105">요소</span><span class="sxs-lookup"><span data-stu-id="65ca5-105">Parts</span></span>  
  
-   `attributelist`  
  
     <span data-ttu-id="65ca5-106">선택적 요소.</span><span class="sxs-lookup"><span data-stu-id="65ca5-106">Optional.</span></span> <span data-ttu-id="65ca5-107">이 열거형에 적용 되는 특성의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="65ca5-107">List of attributes that apply to this enumeration.</span></span> <span data-ttu-id="65ca5-108">묶어야는 [특성 목록](../../../visual-basic/language-reference/statements/attribute-list.md) 꺾쇠 괄호에서 ("`<`"및"`>`").</span><span class="sxs-lookup"><span data-stu-id="65ca5-108">You must enclose the [attribute list](../../../visual-basic/language-reference/statements/attribute-list.md) in angle brackets ("`<`" and "`>`").</span></span>  
  
     <span data-ttu-id="65ca5-109"><xref:System.FlagsAttribute>열거형의 인스턴스 값이 여러 열거형 멤버를 포함할 수 있으며 각 멤버는 열거형 값의 비트 필드를 나타내는 특성을 나타냅니다.</xref:System.FlagsAttribute></span><span class="sxs-lookup"><span data-stu-id="65ca5-109">The <xref:System.FlagsAttribute> attribute indicates that the value of an instance of the enumeration can include multiple enumeration members, and that each member represents a bit field in the enumeration value.</span></span>  
  
-   `accessmodifier`  
  
     <span data-ttu-id="65ca5-110">선택적 요소.</span><span class="sxs-lookup"><span data-stu-id="65ca5-110">Optional.</span></span> <span data-ttu-id="65ca5-111">이 열거형에 액세스할 수 있는 코드를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="65ca5-111">Specifies what code can access this enumeration.</span></span> <span data-ttu-id="65ca5-112">다음 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65ca5-112">Can be one of the following:</span></span>  
  
    -   [<span data-ttu-id="65ca5-113">공용</span><span class="sxs-lookup"><span data-stu-id="65ca5-113">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
  
    -   [<span data-ttu-id="65ca5-114">보호됨</span><span class="sxs-lookup"><span data-stu-id="65ca5-114">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)  
  
    -   [<span data-ttu-id="65ca5-115">Friend</span><span class="sxs-lookup"><span data-stu-id="65ca5-115">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)  
  
    -   [<span data-ttu-id="65ca5-116">전용</span><span class="sxs-lookup"><span data-stu-id="65ca5-116">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)  
  
     <span data-ttu-id="65ca5-117">지정할 수 있습니다 `Protected``Friend` 열거형의 클래스나 파생된 클래스에서 동일한 어셈블리 내의 코드에서 액세스할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="65ca5-117">You can specify `Protected``Friend` to allow access from code within the enumeration's class, a derived class, or the same assembly.</span></span>  
  
-   `Shadows`  
  
     <span data-ttu-id="65ca5-118">선택적 요소.</span><span class="sxs-lookup"><span data-stu-id="65ca5-118">Optional.</span></span> <span data-ttu-id="65ca5-119">이 열거형은 같은 이름의 프로그래밍 요소 또는 기본 클래스의 오버 로드 된 요소 집합 다시 선언 하 고 숨기도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="65ca5-119">Specifies that this enumeration redeclares and hides an identically named programming element, or set of overloaded elements, in a base class.</span></span> <span data-ttu-id="65ca5-120">지정할 수 있습니다 [그림자](../../../visual-basic/language-reference/modifiers/shadows.md) 열거형의 멤버 아니라 열거형 자체에 합니다.</span><span class="sxs-lookup"><span data-stu-id="65ca5-120">You can specify [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md) only on the enumeration itself, not on any of its members.</span></span>  
  
-   `enumerationname`  
  
     <span data-ttu-id="65ca5-121">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="65ca5-121">Required.</span></span> <span data-ttu-id="65ca5-122">열거형의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="65ca5-122">Name of the enumeration.</span></span> <span data-ttu-id="65ca5-123">유효한 이름에 대 한 자세한 내용은 참조 [선언 요소 이름](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="65ca5-123">For information on valid names, see [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
-   `datatype`  
  
     <span data-ttu-id="65ca5-124">선택적 요소.</span><span class="sxs-lookup"><span data-stu-id="65ca5-124">Optional.</span></span> <span data-ttu-id="65ca5-125">열거형 및 모든 해당 멤버의 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="65ca5-125">Data type of the enumeration and all its members.</span></span>  
  
-   `memberlist`  
  
     <span data-ttu-id="65ca5-126">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="65ca5-126">Required.</span></span> <span data-ttu-id="65ca5-127">이 문에서 선언 되는 멤버 상수 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="65ca5-127">List of member constants being declared in this statement.</span></span> <span data-ttu-id="65ca5-128">여러 멤버 개별 소스 코드 줄에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="65ca5-128">Multiple members appear on individual source code lines.</span></span>  
  
     <span data-ttu-id="65ca5-129">각 `member` 다음 구문과 구성 요소는:`[<attribute list>] member name [ = initializer ]`</span><span class="sxs-lookup"><span data-stu-id="65ca5-129">Each `member` has the following syntax and parts: `[<attribute list>] member name [ = initializer ]`</span></span>  
  
    |<span data-ttu-id="65ca5-130">파트</span><span class="sxs-lookup"><span data-stu-id="65ca5-130">Part</span></span>|<span data-ttu-id="65ca5-131">설명</span><span class="sxs-lookup"><span data-stu-id="65ca5-131">Description</span></span>|  
    |---|---|  
    |`membername`|<span data-ttu-id="65ca5-132">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="65ca5-132">Required.</span></span> <span data-ttu-id="65ca5-133">이 멤버의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="65ca5-133">Name of this member.</span></span>|  
    |`initializer`|<span data-ttu-id="65ca5-134">선택적 요소.</span><span class="sxs-lookup"><span data-stu-id="65ca5-134">Optional.</span></span> <span data-ttu-id="65ca5-135">컴파일 타임에 계산 되 고이 멤버에 할당 되는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="65ca5-135">Expression that is evaluated at compile time and assigned to this member.</span></span>|  
  
-   <span data-ttu-id="65ca5-136">`End` `Enum`</span><span class="sxs-lookup"><span data-stu-id="65ca5-136">`End` `Enum`</span></span>  
  
     <span data-ttu-id="65ca5-137">`Enum` 블록을 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="65ca5-137">Terminates the `Enum` block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="65ca5-138">설명</span><span class="sxs-lookup"><span data-stu-id="65ca5-138">Remarks</span></span>  
 <span data-ttu-id="65ca5-139">논리적으로 서로 관련 된 변경 되지 않는 값의 집합에 있으면 정의할 수 있습니다 이러한 함께 열거형에서.</span><span class="sxs-lookup"><span data-stu-id="65ca5-139">If you have a set of unchanging values that are logically related to each other, you can define them together in an enumeration.</span></span> <span data-ttu-id="65ca5-140">이 열거형과 해당 값 보다 쉽게 기억할 수 있는 해당 멤버에 대 한 의미 있는 이름을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="65ca5-140">This provides meaningful names for the enumeration and its members, which are easier to remember than their values.</span></span> <span data-ttu-id="65ca5-141">다음 코드의 여러 위치에서 열거형 멤버를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65ca5-141">You can then use the enumeration members in many places in your code.</span></span>  
  
 <span data-ttu-id="65ca5-142">열거형을 사용할 때의 이점은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="65ca5-142">The benefits of using enumerations include the following:</span></span>  
  
-   <span data-ttu-id="65ca5-143">숫자를 잘못 입력 하 여 발생 하는 오류를 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65ca5-143">Reduces errors caused by transposing or mistyping numbers.</span></span>  
  
-   <span data-ttu-id="65ca5-144">나중에 값을 변경 하려면 쉽게 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65ca5-144">Makes it easy to change values in the future.</span></span>  
  
-   <span data-ttu-id="65ca5-145">에서는 거의 오류를 도입 될 것으로 코드를 쉽게 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65ca5-145">Makes code easier to read, which means it is less likely that errors will be introduced.</span></span>  
  
-   <span data-ttu-id="65ca5-146">다음 버전과 호환성을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="65ca5-146">Ensures forward compatibility.</span></span> <span data-ttu-id="65ca5-147">열거형을 사용 하는 경우이 코드는 나중에 멤버 이름에 해당 하는 값 변경 되 면 실패할 가능성이 적습니다.</span><span class="sxs-lookup"><span data-stu-id="65ca5-147">If you use enumerations, your code is less likely to fail if in the future someone changes the values corresponding to the member names.</span></span>  
  
 <span data-ttu-id="65ca5-148">열거형에는 이름, 내부 데이터 형식 및 멤버 집합을 합니다.</span><span class="sxs-lookup"><span data-stu-id="65ca5-148">An enumeration has a name, an underlying data type, and a set of members.</span></span> <span data-ttu-id="65ca5-149">각 멤버는 상수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="65ca5-149">Each member represents a constant.</span></span>  
  
 <span data-ttu-id="65ca5-150">클래스, 구조체, 모듈 또는 다른 프로시저 외부 인터페이스 수준에서 선언 하는 열거형은는 *멤버 열거형*합니다.</span><span class="sxs-lookup"><span data-stu-id="65ca5-150">An enumeration declared at class, structure, module, or interface level, outside any procedure, is a *member enumeration*.</span></span> <span data-ttu-id="65ca5-151">클래스, 구조체, 모듈 또는 변수를 선언 하는 인터페이스의 멤버 임</span><span class="sxs-lookup"><span data-stu-id="65ca5-151">It is a member of the class, structure, module, or interface that declares it.</span></span>  
  
 <span data-ttu-id="65ca5-152">멤버 열거형 어디 액세스할 수에서 해당 클래스, 구조체, 모듈 또는 인터페이스 내에서.</span><span class="sxs-lookup"><span data-stu-id="65ca5-152">Member enumerations can be accessed from anywhere within their class, structure, module, or interface.</span></span> <span data-ttu-id="65ca5-153">코드는 클래스 외부 또는 모듈 멤버 열거형의 이름을 정해야 해당 클래스, 구조체, 모듈의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="65ca5-153">Code outside a class, structure, or module must qualify a member enumeration's name with the name of that class, structure, or module.</span></span> <span data-ttu-id="65ca5-154">정규화 된 이름을 추가 하 여 사용의 필요성을 방지할 수는 [Imports](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) 문을 소스 파일에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65ca5-154">You can avoid the need to use fully qualified names by adding an [Imports](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) statement to the source file.</span></span>  
  
 <span data-ttu-id="65ca5-155">클래스, 구조체, 모듈 또는 인터페이스를 외부 네임 스페이스 수준에서 선언 되는 열거형은 표시 되는 네임 스페이스의 멤버입니다.</span><span class="sxs-lookup"><span data-stu-id="65ca5-155">An enumeration declared at namespace level, outside any class, structure, module, or interface, is a member of the namespace in which it appears.</span></span>  
  
 <span data-ttu-id="65ca5-156">*선언 컨텍스트* 열거형 소스 파일, 네임 스페이스, 클래스, 구조체, 모듈 또는 인터페이스를 이어야 하며 프로시저일 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="65ca5-156">The *declaration context* for an enumeration must be a source file, namespace, class, structure, module, or interface, and cannot be a procedure.</span></span> <span data-ttu-id="65ca5-157">자세한 내용은 참조 [선언 컨텍스트 및 기본 액세스 수준](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="65ca5-157">For more information, see [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>  
  
 <span data-ttu-id="65ca5-158">특성 적용을 전체적으로 열거형에 있지만 해당 멤버에 개별적으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="65ca5-158">You can apply attributes to an enumeration as a whole, but not to its members individually.</span></span> <span data-ttu-id="65ca5-159">어셈블리의 메타 데이터에 정보를 적용 하는 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="65ca5-159">An attribute contributes information to the assembly's metadata.</span></span>  
  
## <a name="data-type"></a><span data-ttu-id="65ca5-160">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="65ca5-160">Data Type</span></span>  
 <span data-ttu-id="65ca5-161">`Enum` 문은 데이터 형식의 열거형을 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65ca5-161">The `Enum` statement can declare the data type of an enumeration.</span></span> <span data-ttu-id="65ca5-162">각 멤버에는 열거형의 데이터 형식을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="65ca5-162">Each member takes the enumeration's data type.</span></span> <span data-ttu-id="65ca5-163">You can specify `Byte`, `Integer`, `Long`, `SByte`, `Short`, `UInteger`, `ULong`, or `UShort`.</span><span class="sxs-lookup"><span data-stu-id="65ca5-163">You can specify `Byte`, `Integer`, `Long`, `SByte`, `Short`, `UInteger`, `ULong`, or `UShort`.</span></span>  
  
 <span data-ttu-id="65ca5-164">지정 하지 않으면 `datatype` 열거형에 대 한 각 멤버는 형식의 데이터는 해당 `initializer`합니다.</span><span class="sxs-lookup"><span data-stu-id="65ca5-164">If you do not specify `datatype` for the enumeration, each member takes the data type of its `initializer`.</span></span> <span data-ttu-id="65ca5-165">모두 지정 하면 `datatype` 및 `initializer`의 데이터 형식이 `initializer` 변환할 수 있어야 `datatype`합니다.</span><span class="sxs-lookup"><span data-stu-id="65ca5-165">If you specify both `datatype` and `initializer`, the data type of `initializer` must be convertible to `datatype`.</span></span> <span data-ttu-id="65ca5-166">모두 `datatype` 나 `initializer` 가 있으면 데이터 형식의 기본값으로 `Integer`합니다.</span><span class="sxs-lookup"><span data-stu-id="65ca5-166">If neither `datatype` nor `initializer` is present, the data type defaults to `Integer`.</span></span>  
  
## <a name="initializing-members"></a><span data-ttu-id="65ca5-167">멤버 초기화</span><span class="sxs-lookup"><span data-stu-id="65ca5-167">Initializing Members</span></span>  
 <span data-ttu-id="65ca5-168">`Enum` 문을에서 선택한 멤버의 콘텐츠를 초기화할 수 `memberlist`합니다.</span><span class="sxs-lookup"><span data-stu-id="65ca5-168">The `Enum` statement can initialize the contents of selected members in `memberlist`.</span></span> <span data-ttu-id="65ca5-169">사용 하면 `initializer` 멤버에 할당 하는 식을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="65ca5-169">You use `initializer` to supply an expression to be assigned to the member.</span></span>  
  
 <span data-ttu-id="65ca5-170">지정 하지 않으면 `initializer` 멤버에 대 한 Visual Basic 초기화을&0; (첫 번째 경우 `member` 에서 `memberlist`), 또는 바로 앞에 보다 하나 큰 값으로 `member`합니다.</span><span class="sxs-lookup"><span data-stu-id="65ca5-170">If you do not specify `initializer` for a member, Visual Basic initializes it either to zero (if it is the first `member` in `memberlist`), or to a value greater by one than that of the immediately preceding `member`.</span></span>  
  
 <span data-ttu-id="65ca5-171">각 지정 된 식은 `initializer` 리터럴, 이미 정의 되어 있는 다른 상수 이미 정의 되어 있는,이 열거형의 이전 멤버를 포함 하 여 열거형 멤버의 조합일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65ca5-171">The expression supplied in each `initializer` can be any combination of literals, other constants that are already defined, and enumeration members that are already defined, including a previous member of this enumeration.</span></span> <span data-ttu-id="65ca5-172">이러한 요소를 결합 하 여 산술 및 논리 연산자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65ca5-172">You can use arithmetic and logical operators to combine such elements.</span></span>  
  
 <span data-ttu-id="65ca5-173">변수 또는 함수에서 사용할 수 없습니다 `initializer`합니다.</span><span class="sxs-lookup"><span data-stu-id="65ca5-173">You cannot use variables or functions in `initializer`.</span></span> <span data-ttu-id="65ca5-174">그러나와 같은 변환 키워드를 사용할 수는 `CByte` 및 `CShort`합니다.</span><span class="sxs-lookup"><span data-stu-id="65ca5-174">However, you can use conversion keywords such as `CByte` and `CShort`.</span></span> <span data-ttu-id="65ca5-175">사용할 수도 있습니다 `AscW` 상수와 호출 하는 경우 `String` 또는 `Char` 인수를 컴파일 타임에 계산 될 수 있으므로 합니다.</span><span class="sxs-lookup"><span data-stu-id="65ca5-175">You can also use `AscW` if you call it with a constant `String` or `Char` argument, since that can be evaluated at compile time.</span></span>  
  
 <span data-ttu-id="65ca5-176">열거형 부동 소수점 값을 가질 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="65ca5-176">Enumerations cannot have floating-point values.</span></span> <span data-ttu-id="65ca5-177">멤버는 부동 소수점 값에 할당 된 경우 및 `Option Strict` 컴파일러 오류가 발생 하는 on으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="65ca5-177">If a member is assigned a floating-point value and `Option Strict` is set to on, a compiler error occurs.</span></span> <span data-ttu-id="65ca5-178">경우 `Option Strict` 가 해제를 자동으로 변환 된 값은 `Enum` 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="65ca5-178">If `Option Strict` is off, the value is automatically converted to the `Enum` type.</span></span>  
  
 <span data-ttu-id="65ca5-179">기본 데이터 형식에 대 한 허용 범위를 초과 하는 멤버의 값 또는 멤버를 기본 데이터 형식에서 허용 되는 최대값을 초기화 하는 경우 컴파일러는 오류를 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="65ca5-179">If the value of a member exceeds the allowable range for the underlying data type, or if you initialize any member to the maximum value allowed by the underlying data type, the compiler reports an error.</span></span>  
  
## <a name="modifiers"></a><span data-ttu-id="65ca5-180">한정자</span><span class="sxs-lookup"><span data-stu-id="65ca5-180">Modifiers</span></span>  
 <span data-ttu-id="65ca5-181">클래스, 구조체, 모듈 및 인터페이스 멤버 열거형은 기본적으로 공용 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="65ca5-181">Class, structure, module, and interface member enumerations default to public access.</span></span> <span data-ttu-id="65ca5-182">액세스 한정자로 액세스 수준을 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65ca5-182">You can adjust their access levels with the access modifiers.</span></span> <span data-ttu-id="65ca5-183">Namespace 멤버 열거는 기본적으로 friend 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="65ca5-183">Namespace member enumerations default to friend access.</span></span> <span data-ttu-id="65ca5-184">공용, 아니라 private 또는 protected 액세스 수준을 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65ca5-184">You can adjust their access levels to public, but not to private or protected.</span></span> <span data-ttu-id="65ca5-185">자세한 내용은 참조 [Visual Basic의 액세스 수준을](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="65ca5-185">For more information, see [Access Levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 <span data-ttu-id="65ca5-186">모든 열거형 멤버는 공용 액세스 있고 등에 액세스 한정자를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="65ca5-186">All enumeration members have public access, and you cannot use any access modifiers on them.</span></span> <span data-ttu-id="65ca5-187">그러나 경우 열거형 자체 보다 제한 된 액세스 수준이 지정 된 열거형의 액세스 수준이 우선 합니다.</span><span class="sxs-lookup"><span data-stu-id="65ca5-187">However, if the enumeration itself has a more restricted access level, the specified enumeration access level takes precedence.</span></span>  
  
 <span data-ttu-id="65ca5-188">기본적으로 모든 열거형 형식이 며 해당 필드는 상수입니다.</span><span class="sxs-lookup"><span data-stu-id="65ca5-188">By default, all enumerations are types and their fields are constants.</span></span> <span data-ttu-id="65ca5-189">따라서는 `Shared`, `Static`, 및 `ReadOnly` 열거형 또는 해당 멤버를 선언 하는 경우에 키워드를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="65ca5-189">Therefore the `Shared`, `Static`, and `ReadOnly` keywords cannot be used when declaring an enumeration or its members.</span></span>  
  
## <a name="assigning-multiple-values"></a><span data-ttu-id="65ca5-190">여러 값을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="65ca5-190">Assigning Multiple Values</span></span>  
 <span data-ttu-id="65ca5-191">열거형은 일반적으로 상호 배타적인 값을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="65ca5-191">Enumerations typically represent mutually exclusive values.</span></span> <span data-ttu-id="65ca5-192">포함 하 여는 <xref:System.FlagsAttribute>특성에 `Enum` 선언 대신 값을 할당할 수 여러 열거형의 인스턴스로.</xref:System.FlagsAttribute></span><span class="sxs-lookup"><span data-stu-id="65ca5-192">By including the <xref:System.FlagsAttribute> attribute in the `Enum` declaration, you can instead assign multiple values to an instance of the enumeration.</span></span> <span data-ttu-id="65ca5-193"><xref:System.FlagsAttribute>특성 열거형 비트 필드 즉, 플래그 집합으로 처리 하도록 지정 합니다.</xref:System.FlagsAttribute></span><span class="sxs-lookup"><span data-stu-id="65ca5-193">The <xref:System.FlagsAttribute> attribute specifies that the enumeration be treated as a bit field, that is, a set of flags.</span></span> <span data-ttu-id="65ca5-194">이 라고 *비트* 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="65ca5-194">These are called *bitwise* enumerations.</span></span>  
  
 <span data-ttu-id="65ca5-195">사용 하 여 열거형을 선언할 때는 <xref:System.FlagsAttribute>특성 좋습니다 값에 있는 2, 1, 2, 4, 8, 16, 및 등의 거듭제곱이 사용 합니다.</xref:System.FlagsAttribute></span><span class="sxs-lookup"><span data-stu-id="65ca5-195">When you declare an enumeration by using the <xref:System.FlagsAttribute> attribute, we recommend that you use powers of 2, that is, 1, 2, 4, 8, 16, and so on, for the values.</span></span> <span data-ttu-id="65ca5-196">값이 0 인 멤버의 이름을 "None" 되도록 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="65ca5-196">We also recommend that "None" be the name of a member whose value is 0.</span></span> <span data-ttu-id="65ca5-197">추가 지침 <xref:System.FlagsAttribute>및 <xref:System.Enum>.</xref:System.Enum> </xref:System.FlagsAttribute> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="65ca5-197">For additional guidelines, see <xref:System.FlagsAttribute> and <xref:System.Enum>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="65ca5-198">예제</span><span class="sxs-lookup"><span data-stu-id="65ca5-198">Example</span></span>  
 <span data-ttu-id="65ca5-199">다음 예제를 사용 하는 방법을 보여 줍니다는 `Enum` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="65ca5-199">The following example shows how to use the `Enum` statement.</span></span> <span data-ttu-id="65ca5-200">멤버 라고는 `EggSizeEnum.Medium`, 아니라 `Medium`합니다.</span><span class="sxs-lookup"><span data-stu-id="65ca5-200">Note that the member is referred to as `EggSizeEnum.Medium`, and not as `Medium`.</span></span>  
  
 <span data-ttu-id="65ca5-201">[!code-vb[VbEnumsTask #&41;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="65ca5-201">[!code-vb[VbEnumsTask#41](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_1.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="65ca5-202">예제</span><span class="sxs-lookup"><span data-stu-id="65ca5-202">Example</span></span>  
 <span data-ttu-id="65ca5-203">다음 예제에서 메서드는 외부는 `Egg` 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="65ca5-203">The method in the following example is outside the `Egg` class.</span></span> <span data-ttu-id="65ca5-204">따라서 `EggSizeEnum` 으로 정규화 된 `Egg.EggSizeEnum`합니다.</span><span class="sxs-lookup"><span data-stu-id="65ca5-204">Therefore, `EggSizeEnum` is fully qualified as `Egg.EggSizeEnum`.</span></span>  
  
 <span data-ttu-id="65ca5-205">[!code-vb[VbEnumsTask #&42;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="65ca5-205">[!code-vb[VbEnumsTask#42](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_2.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="65ca5-206">예제</span><span class="sxs-lookup"><span data-stu-id="65ca5-206">Example</span></span>  
 <span data-ttu-id="65ca5-207">다음 예제에서는 `Enum` 명명 된 상수 값을 관련된 집합을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="65ca5-207">The following example uses the `Enum` statement to define a related set of named constant values.</span></span> <span data-ttu-id="65ca5-208">이 경우 값은 색 데이터베이스에 대 한 데이터 입력 폼을 설계할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65ca5-208">In this case, the values are colors you might choose to design data entry forms for a database.</span></span>  
  
 <span data-ttu-id="65ca5-209">[!code-vb[VbEnumsTask #&30;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="65ca5-209">[!code-vb[VbEnumsTask#30](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_3.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="65ca5-210">예제</span><span class="sxs-lookup"><span data-stu-id="65ca5-210">Example</span></span>  
 <span data-ttu-id="65ca5-211">다음 예에서는 양수 및 음수를 포함 하는 값을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="65ca5-211">The following example shows values that include both positive and negative numbers.</span></span>  
  
 <span data-ttu-id="65ca5-212">[!code-vb[VbEnumsTask #&31;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="65ca5-212">[!code-vb[VbEnumsTask#31](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_4.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="65ca5-213">예제</span><span class="sxs-lookup"><span data-stu-id="65ca5-213">Example</span></span>  
 <span data-ttu-id="65ca5-214">다음 예제에서는 `As` 절 지정을 사용 하는 `datatype` 열거형의 합니다.</span><span class="sxs-lookup"><span data-stu-id="65ca5-214">In the following example, an `As` clause is used to specify the `datatype` of an enumeration.</span></span>  
  
 <span data-ttu-id="65ca5-215">[!code-vb[VbEnumsTask #&6;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="65ca5-215">[!code-vb[VbEnumsTask#6](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_5.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="65ca5-216">예제</span><span class="sxs-lookup"><span data-stu-id="65ca5-216">Example</span></span>  
 <span data-ttu-id="65ca5-217">다음 예제에서는 열거형을 비트를 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="65ca5-217">The following example shows how to use a bitwise enumeration.</span></span> <span data-ttu-id="65ca5-218">여러 값의 비트 열거형 인스턴스에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65ca5-218">Multiple values can be assigned to an instance of a bitwise enumeration.</span></span> <span data-ttu-id="65ca5-219">`Enum` 선언는 <xref:System.FlagsAttribute>열거형 플래그 집합으로 처리할 수 있음을 나타내는 특성입니다.</xref:System.FlagsAttribute></span><span class="sxs-lookup"><span data-stu-id="65ca5-219">The `Enum` declaration includes the <xref:System.FlagsAttribute> attribute, which indicates that the enumeration can be treated as a set of flags.</span></span>  
  
 <span data-ttu-id="65ca5-220">[!code-vb[VbEnumsTask #&61;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="65ca5-220">[!code-vb[VbEnumsTask#61](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_6.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="65ca5-221">예제</span><span class="sxs-lookup"><span data-stu-id="65ca5-221">Example</span></span>  
 <span data-ttu-id="65ca5-222">다음 예제에서는 열거형을 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="65ca5-222">The following example iterates through an enumeration.</span></span> <span data-ttu-id="65ca5-223">사용 하 여는 <xref:System.Enum.GetNames%2A>열거형의 멤버 이름의 배열을 검색 하는 메서드 및 <xref:System.Enum.GetValues%2A>멤버 값의 배열을 검색 하.</xref:System.Enum.GetValues%2A> </xref:System.Enum.GetNames%2A></span><span class="sxs-lookup"><span data-stu-id="65ca5-223">It uses the <xref:System.Enum.GetNames%2A> method to retrieve an array of member names from the enumeration, and <xref:System.Enum.GetValues%2A> to retrieve an array of member values.</span></span>  
  
 <span data-ttu-id="65ca5-224">[!code-vb[VbEnumsTask #&51;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_7.vb)]</span><span class="sxs-lookup"><span data-stu-id="65ca5-224">[!code-vb[VbEnumsTask#51](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_7.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65ca5-225">참고 항목</span><span class="sxs-lookup"><span data-stu-id="65ca5-225">See Also</span></span>  
 <span data-ttu-id="65ca5-226"><xref:System.Enum></xref:System.Enum></span><span class="sxs-lookup"><span data-stu-id="65ca5-226"><xref:System.Enum></span></span>   
 <span data-ttu-id="65ca5-227"><xref:Microsoft.VisualBasic.Strings.AscW%2A></xref:Microsoft.VisualBasic.Strings.AscW%2A></span><span class="sxs-lookup"><span data-stu-id="65ca5-227"><xref:Microsoft.VisualBasic.Strings.AscW%2A></span></span>   
<span data-ttu-id="65ca5-228"> [Const 문](../../../visual-basic/language-reference/statements/const-statement.md) </span><span class="sxs-lookup"><span data-stu-id="65ca5-228"> [Const Statement](../../../visual-basic/language-reference/statements/const-statement.md) </span></span>  
<span data-ttu-id="65ca5-229"> [Dim 문](../../../visual-basic/language-reference/statements/dim-statement.md) </span><span class="sxs-lookup"><span data-stu-id="65ca5-229"> [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md) </span></span>  
<span data-ttu-id="65ca5-230"> [암시적 변환과 명시적 변환](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="65ca5-230"> [Implicit and Explicit Conversions](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md) </span></span>  
<span data-ttu-id="65ca5-231"> [형식 변환 함수](../../../visual-basic/language-reference/functions/type-conversion-functions.md) </span><span class="sxs-lookup"><span data-stu-id="65ca5-231"> [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md) </span></span>  
<span data-ttu-id="65ca5-232"> [상수 및 열거형](../../../visual-basic/language-reference/constants-and-enumerations.md)</span><span class="sxs-lookup"><span data-stu-id="65ca5-232"> [Constants and Enumerations](../../../visual-basic/language-reference/constants-and-enumerations.md)</span></span>
