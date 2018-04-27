---
title: Property Statement
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.PropertySet
- vb.Property
- vb.PropertyGet
helpviewer_keywords:
- Property statement [Visual Basic]
- default modifier
- property procedures [Visual Basic], Property statements
- Property keyword [Visual Basic]
ms.assetid: 3155edaf-8ebd-45c6-9cef-11d5d2dc8d38
caps.latest.revision: 41
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 558b62dd8c676532355ef12134ad8cb803b70796
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2018
---
# <a name="property-statement"></a><span data-ttu-id="4dd81-102">Property Statement</span><span class="sxs-lookup"><span data-stu-id="4dd81-102">Property Statement</span></span>
<span data-ttu-id="4dd81-103">속성을 저장 하 고 속성의 값을 검색 하는 데 사용 하는 속성 프로시저의 이름을 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="4dd81-103">Declares the name of a property, and the property procedures used to store and retrieve the value of the property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4dd81-104">구문</span><span class="sxs-lookup"><span data-stu-id="4dd81-104">Syntax</span></span>  
  
```vb  
[ <attributelist> ] [ Default ] [ accessmodifier ]   
[ propertymodifiers ] [ Shared ] [ Shadows ] [ ReadOnly | WriteOnly ] [ Iterator ]  
Property name ( [ parameterlist ] ) [ As returntype ] [ Implements implementslist ]  
    [ <attributelist> ] [ accessmodifier ] Get  
        [ statements ]  
    End Get  
    [ <attributelist> ] [ accessmodifier ] Set ( ByVal value As returntype [, parameterlist ] )  
        [ statements ]  
    End Set  
End Property  
- or -  
[ <attributelist> ] [ Default ] [ accessmodifier ]   
[ propertymodifiers ] [ Shared ] [ Shadows ] [ ReadOnly | WriteOnly ]   
Property name ( [ parameterlist ] ) [ As returntype ] [ Implements implementslist ]  
```  
  
## <a name="parts"></a><span data-ttu-id="4dd81-105">요소</span><span class="sxs-lookup"><span data-stu-id="4dd81-105">Parts</span></span>  
  
-   `attributelist`  
  
     <span data-ttu-id="4dd81-106">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="4dd81-106">Optional.</span></span> <span data-ttu-id="4dd81-107">이 속성에 적용 되는 특성의 목록 또는 `Get` 또는 `Set` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="4dd81-107">List of attributes that apply to this property or `Get` or `Set` procedure.</span></span> <span data-ttu-id="4dd81-108">참조 [특성 목록](../../../visual-basic/language-reference/statements/attribute-list.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4dd81-108">See [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md).</span></span>  
  
-   `Default`  
  
     <span data-ttu-id="4dd81-109">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="4dd81-109">Optional.</span></span> <span data-ttu-id="4dd81-110">이 속성은 클래스 또는 구조체에는 정의 대 한 기본 속성을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4dd81-110">Specifies that this property is the default property for the class or structure on which it is defined.</span></span> <span data-ttu-id="4dd81-111">기본 속성 매개 변수를 허용 해야 설정 되었고 속성 이름을 지정 하지 않고 검색 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4dd81-111">Default properties must accept parameters and can be set and retrieved without specifying the property name.</span></span> <span data-ttu-id="4dd81-112">속성으로 선언 하는 경우 `Default`를 사용할 수 없습니다 `Private` 속성 또는 해당 속성 프로시저 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="4dd81-112">If you declare the property as `Default`, you cannot use `Private` on the property or on either of its property procedures.</span></span>  
  
-   `accessmodifier`  
  
     <span data-ttu-id="4dd81-113">선택적 요소는 `Property` 문 중 최대 하나에 `Get` 및 `Set` 문.</span><span class="sxs-lookup"><span data-stu-id="4dd81-113">Optional on the `Property` statement and on at most one of the `Get` and `Set` statements.</span></span> <span data-ttu-id="4dd81-114">다음 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4dd81-114">Can be one of the following:</span></span>  
  
    -   [<span data-ttu-id="4dd81-115">공용</span><span class="sxs-lookup"><span data-stu-id="4dd81-115">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
  
    -   [<span data-ttu-id="4dd81-116">보호됨</span><span class="sxs-lookup"><span data-stu-id="4dd81-116">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)  
  
    -   [<span data-ttu-id="4dd81-117">Friend</span><span class="sxs-lookup"><span data-stu-id="4dd81-117">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)  
  
    -   [<span data-ttu-id="4dd81-118">전용</span><span class="sxs-lookup"><span data-stu-id="4dd81-118">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)  
  
    -   `Protected Friend`  
  
     <span data-ttu-id="4dd81-119">참조 [액세스 수준을 Visual Basic의](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4dd81-119">See [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
-   `propertymodifiers`  
  
     <span data-ttu-id="4dd81-120">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="4dd81-120">Optional.</span></span> <span data-ttu-id="4dd81-121">다음 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4dd81-121">Can be one of the following:</span></span>  
  
    -   [<span data-ttu-id="4dd81-122">오버로드</span><span class="sxs-lookup"><span data-stu-id="4dd81-122">Overloads</span></span>](../../../visual-basic/language-reference/modifiers/overloads.md)  
  
    -   [<span data-ttu-id="4dd81-123">재정의</span><span class="sxs-lookup"><span data-stu-id="4dd81-123">Overrides</span></span>](../../../visual-basic/language-reference/modifiers/overrides.md)  
  
    -   [<span data-ttu-id="4dd81-124">재정의 가능</span><span class="sxs-lookup"><span data-stu-id="4dd81-124">Overridable</span></span>](../../../visual-basic/language-reference/modifiers/overridable.md)  
  
    -   [<span data-ttu-id="4dd81-125">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="4dd81-125">NotOverridable</span></span>](../../../visual-basic/language-reference/modifiers/notoverridable.md)  
  
    -   [<span data-ttu-id="4dd81-126">MustOverride</span><span class="sxs-lookup"><span data-stu-id="4dd81-126">MustOverride</span></span>](../../../visual-basic/language-reference/modifiers/mustoverride.md)  
  
    -   `MustOverride Overrides`  
  
    -   `NotOverridable Overrides`  
  
-   `Shared`  
  
     <span data-ttu-id="4dd81-127">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="4dd81-127">Optional.</span></span> <span data-ttu-id="4dd81-128">참조 [공유](../../../visual-basic/language-reference/modifiers/shared.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4dd81-128">See [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span></span>  
  
-   `Shadows`  
  
     <span data-ttu-id="4dd81-129">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="4dd81-129">Optional.</span></span> <span data-ttu-id="4dd81-130">참조 [그림자](../../../visual-basic/language-reference/modifiers/shadows.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4dd81-130">See [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span></span>  
  
-   `ReadOnly`  
  
     <span data-ttu-id="4dd81-131">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="4dd81-131">Optional.</span></span> <span data-ttu-id="4dd81-132">참조 [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4dd81-132">See [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
-   `WriteOnly`  
  
     <span data-ttu-id="4dd81-133">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="4dd81-133">Optional.</span></span> <span data-ttu-id="4dd81-134">참조 [WriteOnly](../../../visual-basic/language-reference/modifiers/writeonly.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4dd81-134">See [WriteOnly](../../../visual-basic/language-reference/modifiers/writeonly.md).</span></span>  
  
-   `Iterator`  
  
     <span data-ttu-id="4dd81-135">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="4dd81-135">Optional.</span></span> <span data-ttu-id="4dd81-136">참조 [반복기](../../../visual-basic/language-reference/modifiers/iterator.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4dd81-136">See [Iterator](../../../visual-basic/language-reference/modifiers/iterator.md).</span></span>  
  
-   `name`  
  
     <span data-ttu-id="4dd81-137">필수.</span><span class="sxs-lookup"><span data-stu-id="4dd81-137">Required.</span></span> <span data-ttu-id="4dd81-138">속성의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="4dd81-138">Name of the property.</span></span> <span data-ttu-id="4dd81-139">참조 [선언 된 요소 이름](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4dd81-139">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
-   `parameterlist`  
  
     <span data-ttu-id="4dd81-140">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="4dd81-140">Optional.</span></span> <span data-ttu-id="4dd81-141">이 속성의 매개 변수 및의 가능한 추가 매개 변수를 나타내는 지역 변수 이름의 목록이 `Set` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="4dd81-141">List of local variable names representing the parameters of this property, and possible additional parameters of the `Set` procedure.</span></span> <span data-ttu-id="4dd81-142">참조 [매개 변수 목록](../../../visual-basic/language-reference/statements/parameter-list.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4dd81-142">See [Parameter List](../../../visual-basic/language-reference/statements/parameter-list.md).</span></span>  
  
-   `returntype`  
  
     <span data-ttu-id="4dd81-143">필요한 경우 `Option``Strict` 은 `On`합니다.</span><span class="sxs-lookup"><span data-stu-id="4dd81-143">Required if `Option``Strict` is `On`.</span></span> <span data-ttu-id="4dd81-144">이 속성에서 반환 되는 값의 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="4dd81-144">Data type of the value returned by this property.</span></span>  
  
-   `Implements`  
  
     <span data-ttu-id="4dd81-145">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="4dd81-145">Optional.</span></span> <span data-ttu-id="4dd81-146">이 속성의 포함 하는 클래스 또는 구조체에서 구현 되는 인터페이스에 정의 된 하나 이상의 속성을이 속성을 구현 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4dd81-146">Indicates that this property implements one or more properties, each one defined in an interface implemented by this property's containing class or structure.</span></span> <span data-ttu-id="4dd81-147">참조 [문을 구현](../../../visual-basic/language-reference/statements/implements-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4dd81-147">See [Implements Statement](../../../visual-basic/language-reference/statements/implements-statement.md).</span></span>  
  
-   `implementslist`  
  
     <span data-ttu-id="4dd81-148">`Implements`가 제공된 경우 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="4dd81-148">Required if `Implements` is supplied.</span></span> <span data-ttu-id="4dd81-149">구현 되는 속성 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="4dd81-149">List of properties being implemented.</span></span>  
  
     `implementedproperty [ , implementedproperty ... ]`  
  
     <span data-ttu-id="4dd81-150">각 `implementedproperty`에는 다음과 같은 구문과 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4dd81-150">Each `implementedproperty` has the following syntax and parts:</span></span>  
  
     `interface.definedname`  
  
    |<span data-ttu-id="4dd81-151">파트</span><span class="sxs-lookup"><span data-stu-id="4dd81-151">Part</span></span>|<span data-ttu-id="4dd81-152">설명</span><span class="sxs-lookup"><span data-stu-id="4dd81-152">Description</span></span>|  
    |---|---|  
    |`interface`|<span data-ttu-id="4dd81-153">필수.</span><span class="sxs-lookup"><span data-stu-id="4dd81-153">Required.</span></span> <span data-ttu-id="4dd81-154">이 속성에 의해 구현 되는 인터페이스의 이름의 클래스 또는 구조체를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="4dd81-154">Name of an interface implemented by this property's containing class or structure.</span></span>|  
    |`definedname`|<span data-ttu-id="4dd81-155">필수.</span><span class="sxs-lookup"><span data-stu-id="4dd81-155">Required.</span></span> <span data-ttu-id="4dd81-156">이름에 속성이 정의 된 `interface`합니다.</span><span class="sxs-lookup"><span data-stu-id="4dd81-156">Name by which the property is defined in `interface`.</span></span>|  
  
-   `Get`  
  
     <span data-ttu-id="4dd81-157">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="4dd81-157">Optional.</span></span> <span data-ttu-id="4dd81-158">속성이 표시 하는 경우 필요한 `WriteOnly`합니다.</span><span class="sxs-lookup"><span data-stu-id="4dd81-158">Required if the property is marked `WriteOnly`.</span></span> <span data-ttu-id="4dd81-159">시작 된 `Get` 속성의 값을 반환 하는 데 사용 되는 속성 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="4dd81-159">Starts a `Get` property procedure that is used to return the value of the property.</span></span>  
  
-   `statements`  
  
     <span data-ttu-id="4dd81-160">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="4dd81-160">Optional.</span></span> <span data-ttu-id="4dd81-161">내에서 실행할 문 블록을는 `Get` 또는 `Set` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="4dd81-161">Block of statements to run within the `Get` or `Set` procedure.</span></span>  
  
-   `End Get`  
  
     <span data-ttu-id="4dd81-162">종료는 `Get` 속성 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="4dd81-162">Terminates the `Get` property procedure.</span></span>  
  
-   `Set`  
  
     <span data-ttu-id="4dd81-163">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="4dd81-163">Optional.</span></span> <span data-ttu-id="4dd81-164">속성이 표시 하는 경우 필요한 `ReadOnly`합니다.</span><span class="sxs-lookup"><span data-stu-id="4dd81-164">Required if the property is marked `ReadOnly`.</span></span> <span data-ttu-id="4dd81-165">시작 된 `Set` 속성의 값을 저장 하는 데 사용 되는 속성 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="4dd81-165">Starts a `Set` property procedure that is used to store the value of the property.</span></span>  
  
-   `End Set`  
  
     <span data-ttu-id="4dd81-166">종료는 `Set` 속성 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="4dd81-166">Terminates the `Set` property procedure.</span></span>  
  
-   `End Property`  
  
     <span data-ttu-id="4dd81-167">이 속성의 정의 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="4dd81-167">Terminates the definition of this property.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4dd81-168">설명</span><span class="sxs-lookup"><span data-stu-id="4dd81-168">Remarks</span></span>  
 <span data-ttu-id="4dd81-169">`Property` 문을 속성의 선언을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4dd81-169">The `Property` statement introduces the declaration of a property.</span></span> <span data-ttu-id="4dd81-170">속성을 사용할 수는 `Get` (읽기 전용), 프로시저는 `Set` 프로시저 (쓰기 전용) 또는 두 가지 모두 (읽기-쓰기).</span><span class="sxs-lookup"><span data-stu-id="4dd81-170">A property can have a `Get` procedure (read only), a `Set` procedure (write only), or both (read-write).</span></span> <span data-ttu-id="4dd81-171">생략할 수 있습니다는 `Get` 및 `Set` 자동 구현 속성을 사용할 때 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="4dd81-171">You can omit the `Get` and `Set` procedure when using an auto-implemented property.</span></span> <span data-ttu-id="4dd81-172">자세한 내용은 [자동으로 구현된 속성](../../../visual-basic/programming-guide/language-features/procedures/auto-implemented-properties.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4dd81-172">For more information, see [Auto-Implemented Properties](../../../visual-basic/programming-guide/language-features/procedures/auto-implemented-properties.md).</span></span>  
  
 <span data-ttu-id="4dd81-173">사용할 수 있습니다 `Property` 클래스 수준에만 합니다.</span><span class="sxs-lookup"><span data-stu-id="4dd81-173">You can use `Property` only at class level.</span></span> <span data-ttu-id="4dd81-174">즉,는 *선언 컨텍스트* 속성 클래스, 구조체, 모듈 또는 인터페이스를 이어야 하며 소스 파일, 네임 스페이스, 프로시저 또는 블록 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4dd81-174">This means the *declaration context* for a property must be a class, structure, module, or interface, and cannot be a source file, namespace, procedure, or block.</span></span> <span data-ttu-id="4dd81-175">자세한 내용은 [선언 컨텍스트 및 기본 액세스 수준](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4dd81-175">For more information, see [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>  
  
 <span data-ttu-id="4dd81-176">기본적으로 속성 공용 액세스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4dd81-176">By default, properties use public access.</span></span> <span data-ttu-id="4dd81-177">액세스 한정자로 속성의 액세스 수준을 조정할 수 있습니다는 `Property` 문과 있습니다 수 필요에 따라 조정 더 제한적인 액세스 수준에 해당 속성 프로시저 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="4dd81-177">You can adjust a property's access level with an access modifier on the `Property` statement, and you can optionally adjust one of its property procedures to a more restrictive access level.</span></span>  
  
 <span data-ttu-id="4dd81-178">Visual Basic에는 매개 변수를 전달는 `Set` 속성을 할당 하는 동안 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="4dd81-178">Visual Basic passes a parameter to the `Set` procedure during property assignments.</span></span> <span data-ttu-id="4dd81-179">에 대 한 매개 변수를 제공 하지 않는 경우 `Set`, 라는 암시적 매개 변수를 사용 하는 통합된 개발 환경 (IDE) `value`합니다.</span><span class="sxs-lookup"><span data-stu-id="4dd81-179">If you do not supply a parameter for `Set`, the integrated development environment (IDE) uses an implicit parameter named `value`.</span></span> <span data-ttu-id="4dd81-180">이 매개 변수 속성에 할당할 값을 보유 합니다.</span><span class="sxs-lookup"><span data-stu-id="4dd81-180">This parameter holds the value to be assigned to the property.</span></span> <span data-ttu-id="4dd81-181">일반적으로 전용 지역 변수에이 값을 저장 하 고 반환 될 때마다는 `Get` 프로시저를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="4dd81-181">You typically store this value in a private local variable and return it whenever the `Get` procedure is called.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="4dd81-182">규칙</span><span class="sxs-lookup"><span data-stu-id="4dd81-182">Rules</span></span>  
  
-   <span data-ttu-id="4dd81-183">**액세스 수준이 혼합된 합니다.**</span><span class="sxs-lookup"><span data-stu-id="4dd81-183">**Mixed Access Levels.**</span></span> <span data-ttu-id="4dd81-184">에 대 한 다른 액세스 수준을 선택적으로 지정할 수 읽기 / 쓰기 속성을 정의 하는 경우는 `Get` 또는 `Set` 프로시저 다르다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4dd81-184">If you are defining a read-write property, you can optionally specify a different access level for either the `Get` or the `Set` procedure, but not both.</span></span> <span data-ttu-id="4dd81-185">이 작업을 수행 하는 경우 프로시저 액세스 수준을 속성의 액세스 수준 보다 제한적 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4dd81-185">If you do this, the procedure access level must be more restrictive than the property's access level.</span></span> <span data-ttu-id="4dd81-186">예를 들어, 속성 선언 된 경우 `Friend`를 선언할 수 있습니다는 `Set` 프로시저 `Private`, 아닌 `Public`합니다.</span><span class="sxs-lookup"><span data-stu-id="4dd81-186">For example, if the property is declared `Friend`, you can declare the `Set` procedure `Private`, but not `Public`.</span></span>  
  
     <span data-ttu-id="4dd81-187">정의 하는 경우는 `ReadOnly` 또는 `WriteOnly` 속성, 단일 속성 프로시저 (`Get` 또는 `Set`각각) 모든 속성을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4dd81-187">If you are defining a `ReadOnly` or `WriteOnly` property, the single property procedure (`Get` or `Set`, respectively) represents all of the property.</span></span> <span data-ttu-id="4dd81-188">속성에 대 한 두 개의 액세스 수준을 설정 되므로 이러한 프로시저에 대 한 다른 액세스 수준을 선언할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4dd81-188">You cannot declare a different access level for such a procedure, because that would set two access levels for the property.</span></span>  
  
-   <span data-ttu-id="4dd81-189">**반환 형식입니다.**</span><span class="sxs-lookup"><span data-stu-id="4dd81-189">**Return Type.**</span></span> <span data-ttu-id="4dd81-190">`Property` 문은 반환 하는 값의 데이터 형식을 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4dd81-190">The `Property` statement can declare the data type of the value it returns.</span></span> <span data-ttu-id="4dd81-191">모든 데이터 형식이 나 열거형, 구조체, 클래스 또는 인터페이스의 이름을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4dd81-191">You can specify any data type or the name of an enumeration, structure, class, or interface.</span></span>  
  
     <span data-ttu-id="4dd81-192">지정 하지 않으면 `returntype`, 속성은 반환 `Object`합니다.</span><span class="sxs-lookup"><span data-stu-id="4dd81-192">If you do not specify `returntype`, the property returns `Object`.</span></span>  
  
-   <span data-ttu-id="4dd81-193">**구현입니다.**</span><span class="sxs-lookup"><span data-stu-id="4dd81-193">**Implementation.**</span></span> <span data-ttu-id="4dd81-194">이 속성을 사용 하는 경우는 `Implements` 키워드를 포함 하는 클래스나 구조체 있어야는 `Implements` 문 바로 다음의 `Class` 또는 `Structure` 문.</span><span class="sxs-lookup"><span data-stu-id="4dd81-194">If this property uses the `Implements` keyword, the containing class or structure must have an `Implements` statement immediately following its `Class` or `Structure` statement.</span></span> <span data-ttu-id="4dd81-195">`Implements` 각 인터페이스에 지정 된 문에 포함 해야 `implementslist`합니다.</span><span class="sxs-lookup"><span data-stu-id="4dd81-195">The `Implements` statement must include each interface specified in `implementslist`.</span></span> <span data-ttu-id="4dd81-196">그러나 이름을 인터페이스를 정의 하는 `Property` (에 `definedname`)이이 속성의 이름을와 동일할 필요가 없습니다 (에서 `name`).</span><span class="sxs-lookup"><span data-stu-id="4dd81-196">However, the name by which an interface defines the `Property` (in `definedname`) does not have to be the same as the name of this property (in `name`).</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="4dd81-197">동작</span><span class="sxs-lookup"><span data-stu-id="4dd81-197">Behavior</span></span>  
  
-   <span data-ttu-id="4dd81-198">**속성 프로시저에서 반환 합니다.**</span><span class="sxs-lookup"><span data-stu-id="4dd81-198">**Returning from a Property Procedure.**</span></span> <span data-ttu-id="4dd81-199">경우는 `Get` 또는 `Set` 문을 호출한 다음 문이 실행 계속 프로시저가 호출 코드에 반환 되 면 합니다.</span><span class="sxs-lookup"><span data-stu-id="4dd81-199">When the `Get` or `Set` procedure returns to the calling code, execution continues with the statement following the statement that invoked it.</span></span>  
  
     <span data-ttu-id="4dd81-200">`Exit Property` 및 `Return` 문은 속성 프로시저를 즉시 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="4dd81-200">The `Exit Property` and `Return` statements cause an immediate exit from a property procedure.</span></span> <span data-ttu-id="4dd81-201">개수에 관계 없이 `Exit Property` 및 `Return` 문은 프로시저에서 아무 곳 이나 나타날 수 있으며 함께 사용할 수 있습니다 `Exit Property` 및 `Return` 문.</span><span class="sxs-lookup"><span data-stu-id="4dd81-201">Any number of `Exit Property` and `Return` statements can appear anywhere in the procedure, and you can mix `Exit Property` and `Return` statements.</span></span>  
  
-   <span data-ttu-id="4dd81-202">**값을 반환 합니다.**</span><span class="sxs-lookup"><span data-stu-id="4dd81-202">**Return Value.**</span></span> <span data-ttu-id="4dd81-203">값을 반환 하는 `Get` 프로시저, 속성 이름에 값을 할당 하거나 포함 한 `Return` 문.</span><span class="sxs-lookup"><span data-stu-id="4dd81-203">To return a value from a `Get` procedure, you can either assign the value to the property name or include it in a `Return` statement.</span></span> <span data-ttu-id="4dd81-204">다음 예제에서는 속성 이름에 반환 값을 할당 `quoteForTheDay` 다음 사용 하 여는 `Exit Property` 문 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4dd81-204">The following example assigns the return value to the property name `quoteForTheDay` and then uses the `Exit Property` statement to return.</span></span>  
  
     [!code-vb[VbVbalrStatements#27](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_1.vb)]  
  
     [!code-vb[VbVbalrStatements#28](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_2.vb)]  
  
     <span data-ttu-id="4dd81-205">사용 하는 경우 `Exit Property` 값을 할당 하지 않고 `name`, `Get` 프로시저가 속성의 데이터 형식에 대 한 기본값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4dd81-205">If you use `Exit Property` without assigning a value to `name`, the `Get` procedure returns the default value for the property's data type.</span></span>  
  
     <span data-ttu-id="4dd81-206">`Return` 문을 동시에 할당 된 `Get` 프로시저 반환 값의 절차를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="4dd81-206">The `Return` statement at the same time assigns the `Get` procedure return value and exits the procedure.</span></span> <span data-ttu-id="4dd81-207">다음 예제에서는이 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4dd81-207">The following example shows this.</span></span>  
  
     [!code-vb[VbVbalrStatements#27](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_1.vb)]  
  
     [!code-vb[VbVbalrStatements#29](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_3.vb)]  
  
## <a name="example"></a><span data-ttu-id="4dd81-208">예제</span><span class="sxs-lookup"><span data-stu-id="4dd81-208">Example</span></span>  
 <span data-ttu-id="4dd81-209">다음 예제에서는 클래스에서 속성을 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="4dd81-209">The following example declares a property in a class.</span></span>  
  
 [!code-vb[VbVbalrStatements#51](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_4.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="4dd81-210">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4dd81-210">See Also</span></span>  
 [<span data-ttu-id="4dd81-211">자동으로 구현된 속성</span><span class="sxs-lookup"><span data-stu-id="4dd81-211">Auto-Implemented Properties</span></span>](../../../visual-basic/programming-guide/language-features/procedures/auto-implemented-properties.md)  
 [<span data-ttu-id="4dd81-212">개체 및 클래스</span><span class="sxs-lookup"><span data-stu-id="4dd81-212">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)  
 [<span data-ttu-id="4dd81-213">Get 문</span><span class="sxs-lookup"><span data-stu-id="4dd81-213">Get Statement</span></span>](../../../visual-basic/language-reference/statements/get-statement.md)  
 [<span data-ttu-id="4dd81-214">Set 문</span><span class="sxs-lookup"><span data-stu-id="4dd81-214">Set Statement</span></span>](../../../visual-basic/language-reference/statements/set-statement.md)  
 [<span data-ttu-id="4dd81-215">매개 변수 목록</span><span class="sxs-lookup"><span data-stu-id="4dd81-215">Parameter List</span></span>](../../../visual-basic/language-reference/statements/parameter-list.md)  
 [<span data-ttu-id="4dd81-216">기본</span><span class="sxs-lookup"><span data-stu-id="4dd81-216">Default</span></span>](../../../visual-basic/language-reference/modifiers/default.md)
