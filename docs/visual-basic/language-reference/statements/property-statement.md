---
title: "Property 문 | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.PropertySet
- vb.Property
- vb.PropertyGet
dev_langs:
- VB
helpviewer_keywords:
- Property statement
- default modifier
- property procedures, Property statements
- Property keyword
ms.assetid: 3155edaf-8ebd-45c6-9cef-11d5d2dc8d38
caps.latest.revision: 41
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
ms.sourcegitcommit: 14abadaf548e228244a1ff7ca72fa3896ef4eb5d
ms.openlocfilehash: dbd779b4b6a1dd167e8581066b0fbe034cd2d8f2
ms.contentlocale: ko-kr
ms.lasthandoff: 05/23/2017

---
# <a name="property-statement"></a><span data-ttu-id="21f81-102">Property Statement</span><span class="sxs-lookup"><span data-stu-id="21f81-102">Property Statement</span></span>
<span data-ttu-id="21f81-103">속성 이름과 속성 값을 저장하고 검색하는 데 사용되는 속성 프로시저를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="21f81-103">Declares the name of a property, and the property procedures used to store and retrieve the value of the property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21f81-104">구문</span><span class="sxs-lookup"><span data-stu-id="21f81-104">Syntax</span></span>  
  
```  
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
  
## <a name="parts"></a><span data-ttu-id="21f81-105">요소</span><span class="sxs-lookup"><span data-stu-id="21f81-105">Parts</span></span>  
  
-   `attributelist`  
  
     <span data-ttu-id="21f81-106">선택적 요소.</span><span class="sxs-lookup"><span data-stu-id="21f81-106">Optional.</span></span> <span data-ttu-id="21f81-107">이 속성에 적용 되는 특성의 목록 또는 `Get` 또는 `Set` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="21f81-107">List of attributes that apply to this property or `Get` or `Set` procedure.</span></span> <span data-ttu-id="21f81-108">참조 [특성 목록](../../../visual-basic/language-reference/statements/attribute-list.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="21f81-108">See [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md).</span></span>  
  
-   `Default`  
  
     <span data-ttu-id="21f81-109">선택적 요소.</span><span class="sxs-lookup"><span data-stu-id="21f81-109">Optional.</span></span> <span data-ttu-id="21f81-110">이 속성은 클래스 또는 구조체에는 정의 대 한 기본 속성을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="21f81-110">Specifies that this property is the default property for the class or structure on which it is defined.</span></span> <span data-ttu-id="21f81-111">기본 속성 매개 변수를 허용 해야 하 고 설정 하 고 속성 이름을 지정 하지 않고 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="21f81-111">Default properties must accept parameters and can be set and retrieved without specifying the property name.</span></span> <span data-ttu-id="21f81-112">속성으로 선언 하는 경우 `Default`를 사용할 수 없습니다 `Private` 속성 또는 속성 프로시저 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="21f81-112">If you declare the property as `Default`, you cannot use `Private` on the property or on either of its property procedures.</span></span>  
  
-   `accessmodifier`  
  
     <span data-ttu-id="21f81-113">선택적 요소는 `Property` 문 및 중 하나에 `Get` 및 `Set` 문.</span><span class="sxs-lookup"><span data-stu-id="21f81-113">Optional on the `Property` statement and on at most one of the `Get` and `Set` statements.</span></span> <span data-ttu-id="21f81-114">다음 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21f81-114">Can be one of the following:</span></span>  
  
    -   [<span data-ttu-id="21f81-115">공용</span><span class="sxs-lookup"><span data-stu-id="21f81-115">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
  
    -   [<span data-ttu-id="21f81-116">보호됨</span><span class="sxs-lookup"><span data-stu-id="21f81-116">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)  
  
    -   [<span data-ttu-id="21f81-117">Friend</span><span class="sxs-lookup"><span data-stu-id="21f81-117">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)  
  
    -   [<span data-ttu-id="21f81-118">전용</span><span class="sxs-lookup"><span data-stu-id="21f81-118">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)  
  
    -   `Protected Friend`  
  
     <span data-ttu-id="21f81-119">참조 [액세스 수준 Visual Basic의](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="21f81-119">See [Access Levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
-   `propertymodifiers`  
  
     <span data-ttu-id="21f81-120">선택적 요소.</span><span class="sxs-lookup"><span data-stu-id="21f81-120">Optional.</span></span> <span data-ttu-id="21f81-121">다음 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21f81-121">Can be one of the following:</span></span>  
  
    -   [<span data-ttu-id="21f81-122">오버로드</span><span class="sxs-lookup"><span data-stu-id="21f81-122">Overloads</span></span>](../../../visual-basic/language-reference/modifiers/overloads.md)  
  
    -   [<span data-ttu-id="21f81-123">재정의</span><span class="sxs-lookup"><span data-stu-id="21f81-123">Overrides</span></span>](../../../visual-basic/language-reference/modifiers/overrides.md)  
  
    -   [<span data-ttu-id="21f81-124">재정의 가능</span><span class="sxs-lookup"><span data-stu-id="21f81-124">Overridable</span></span>](../../../visual-basic/language-reference/modifiers/overridable.md)  
  
    -   [<span data-ttu-id="21f81-125">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="21f81-125">NotOverridable</span></span>](../../../visual-basic/language-reference/modifiers/notoverridable.md)  
  
    -   [<span data-ttu-id="21f81-126">MustOverride</span><span class="sxs-lookup"><span data-stu-id="21f81-126">MustOverride</span></span>](../../../visual-basic/language-reference/modifiers/mustoverride.md)  
  
    -   `MustOverride Overrides`  
  
    -   `NotOverridable Overrides`  
  
-   `Shared`  
  
     <span data-ttu-id="21f81-127">선택적 요소.</span><span class="sxs-lookup"><span data-stu-id="21f81-127">Optional.</span></span> <span data-ttu-id="21f81-128">참조 [공유](../../../visual-basic/language-reference/modifiers/shared.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="21f81-128">See [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span></span>  
  
-   `Shadows`  
  
     <span data-ttu-id="21f81-129">선택적 요소.</span><span class="sxs-lookup"><span data-stu-id="21f81-129">Optional.</span></span> <span data-ttu-id="21f81-130">참조 [그림자](../../../visual-basic/language-reference/modifiers/shadows.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="21f81-130">See [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span></span>  
  
-   `ReadOnly`  
  
     <span data-ttu-id="21f81-131">선택적 요소.</span><span class="sxs-lookup"><span data-stu-id="21f81-131">Optional.</span></span> <span data-ttu-id="21f81-132">참조 [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="21f81-132">See [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
-   `WriteOnly`  
  
     <span data-ttu-id="21f81-133">선택적 요소.</span><span class="sxs-lookup"><span data-stu-id="21f81-133">Optional.</span></span> <span data-ttu-id="21f81-134">참조 [WriteOnly](../../../visual-basic/language-reference/modifiers/writeonly.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="21f81-134">See [WriteOnly](../../../visual-basic/language-reference/modifiers/writeonly.md).</span></span>  
  
-   `Iterator`  
  
     <span data-ttu-id="21f81-135">선택적 요소.</span><span class="sxs-lookup"><span data-stu-id="21f81-135">Optional.</span></span> <span data-ttu-id="21f81-136">참조 [반복기](../../../visual-basic/language-reference/modifiers/iterator.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="21f81-136">See [Iterator](../../../visual-basic/language-reference/modifiers/iterator.md).</span></span>  
  
-   `name`  
  
     <span data-ttu-id="21f81-137">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="21f81-137">Required.</span></span> <span data-ttu-id="21f81-138">속성의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="21f81-138">Name of the property.</span></span> <span data-ttu-id="21f81-139">참조 [선언 된 요소 이름](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="21f81-139">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
-   `parameterlist`  
  
     <span data-ttu-id="21f81-140">선택적 요소.</span><span class="sxs-lookup"><span data-stu-id="21f81-140">Optional.</span></span> <span data-ttu-id="21f81-141">이 속성의 매개 변수 및의 가능한 추가 매개 변수를 나타내는 지역 변수 이름의 목록이 `Set` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="21f81-141">List of local variable names representing the parameters of this property, and possible additional parameters of the `Set` procedure.</span></span> <span data-ttu-id="21f81-142">참조 [매개 변수 목록](../../../visual-basic/language-reference/statements/parameter-list.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="21f81-142">See [Parameter List](../../../visual-basic/language-reference/statements/parameter-list.md).</span></span>  
  
-   `returntype`  
  
     <span data-ttu-id="21f81-143">필요한 경우 `Option``Strict` 는 `On`합니다.</span><span class="sxs-lookup"><span data-stu-id="21f81-143">Required if `Option``Strict` is `On`.</span></span> <span data-ttu-id="21f81-144">이 속성에서 반환 되는 값의 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="21f81-144">Data type of the value returned by this property.</span></span>  
  
-   `Implements`  
  
     <span data-ttu-id="21f81-145">선택적 요소.</span><span class="sxs-lookup"><span data-stu-id="21f81-145">Optional.</span></span> <span data-ttu-id="21f81-146">이 속성의 포함 하는 클래스 또는 구조체에서 구현 되는 인터페이스에 정의 된 하나 이상의 속성을이 속성을 구현 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="21f81-146">Indicates that this property implements one or more properties, each one defined in an interface implemented by this property's containing class or structure.</span></span> <span data-ttu-id="21f81-147">참조 [문을 구현](../../../visual-basic/language-reference/statements/implements-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="21f81-147">See [Implements Statement](../../../visual-basic/language-reference/statements/implements-statement.md).</span></span>  
  
-   `implementslist`  
  
     <span data-ttu-id="21f81-148">`Implements`가 제공된 경우 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="21f81-148">Required if `Implements` is supplied.</span></span> <span data-ttu-id="21f81-149">구현 되는 속성 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="21f81-149">List of properties being implemented.</span></span>  
  
     `implementedproperty [ , implementedproperty ... ]`  
  
     <span data-ttu-id="21f81-150">각 `implementedproperty`에는 다음과 같은 구문과 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21f81-150">Each `implementedproperty` has the following syntax and parts:</span></span>  
  
     `interface.definedname`  
  
    |<span data-ttu-id="21f81-151">파트</span><span class="sxs-lookup"><span data-stu-id="21f81-151">Part</span></span>|<span data-ttu-id="21f81-152">설명</span><span class="sxs-lookup"><span data-stu-id="21f81-152">Description</span></span>|  
    |---|---|  
    |`interface`|<span data-ttu-id="21f81-153">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="21f81-153">Required.</span></span> <span data-ttu-id="21f81-154">이 속성에 의해 구현 되는 인터페이스의 이름의 클래스 또는 구조체를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="21f81-154">Name of an interface implemented by this property's containing class or structure.</span></span>|  
    |`definedname`|<span data-ttu-id="21f81-155">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="21f81-155">Required.</span></span> <span data-ttu-id="21f81-156">이름에 속성이 정의 되어 `interface`합니다.</span><span class="sxs-lookup"><span data-stu-id="21f81-156">Name by which the property is defined in `interface`.</span></span>|  
  
-   `Get`  
  
     <span data-ttu-id="21f81-157">선택적 요소.</span><span class="sxs-lookup"><span data-stu-id="21f81-157">Optional.</span></span> <span data-ttu-id="21f81-158">속성이 표시 되는 경우 필요한 `WriteOnly`합니다.</span><span class="sxs-lookup"><span data-stu-id="21f81-158">Required if the property is marked `WriteOnly`.</span></span> <span data-ttu-id="21f81-159">시작을 `Get` 속성의 값을 반환 하는 데 사용 되는 속성 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="21f81-159">Starts a `Get` property procedure that is used to return the value of the property.</span></span>  
  
-   `statements`  
  
     <span data-ttu-id="21f81-160">선택적 요소.</span><span class="sxs-lookup"><span data-stu-id="21f81-160">Optional.</span></span> <span data-ttu-id="21f81-161">내에서 실행 하는 문 블록을는 `Get` 또는 `Set` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="21f81-161">Block of statements to run within the `Get` or `Set` procedure.</span></span>  
  
-   `End Get`  
  
     <span data-ttu-id="21f81-162">종료는 `Get` 속성 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="21f81-162">Terminates the `Get` property procedure.</span></span>  
  
-   `Set`  
  
     <span data-ttu-id="21f81-163">선택적 요소.</span><span class="sxs-lookup"><span data-stu-id="21f81-163">Optional.</span></span> <span data-ttu-id="21f81-164">속성이 표시 되는 경우 필요한 `ReadOnly`합니다.</span><span class="sxs-lookup"><span data-stu-id="21f81-164">Required if the property is marked `ReadOnly`.</span></span> <span data-ttu-id="21f81-165">시작을 `Set` 속성의 값을 저장 하는 데 사용 되는 속성 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="21f81-165">Starts a `Set` property procedure that is used to store the value of the property.</span></span>  
  
-   `End Set`  
  
     <span data-ttu-id="21f81-166">종료는 `Set` 속성 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="21f81-166">Terminates the `Set` property procedure.</span></span>  
  
-   `End Property`  
  
     <span data-ttu-id="21f81-167">이 속성의 정의 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="21f81-167">Terminates the definition of this property.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="21f81-168">설명</span><span class="sxs-lookup"><span data-stu-id="21f81-168">Remarks</span></span>  
 <span data-ttu-id="21f81-169">`Property` 문 속성의 선언을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="21f81-169">The `Property` statement introduces the declaration of a property.</span></span> <span data-ttu-id="21f81-170">속성을 사용할 수는 `Get` (읽기 전용), 프로시저는 `Set` 프로시저 (쓰기 전용) 또는 두 가지 모두 (읽기-쓰기).</span><span class="sxs-lookup"><span data-stu-id="21f81-170">A property can have a `Get` procedure (read only), a `Set` procedure (write only), or both (read-write).</span></span> <span data-ttu-id="21f81-171">생략할 수는 `Get` 및 `Set` 프로시저는 자동 구현 속성을 사용 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="21f81-171">You can omit the `Get` and `Set` procedure when using an auto-implemented property.</span></span> <span data-ttu-id="21f81-172">자세한 내용은 참조 [자동으로 구현 된 속성](../../../visual-basic/programming-guide/language-features/procedures/auto-implemented-properties.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="21f81-172">For more information, see [Auto-Implemented Properties](../../../visual-basic/programming-guide/language-features/procedures/auto-implemented-properties.md).</span></span>  
  
 <span data-ttu-id="21f81-173">사용할 수 있습니다 `Property` 클래스 수준에만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21f81-173">You can use `Property` only at class level.</span></span> <span data-ttu-id="21f81-174">이 의미는 *선언 컨텍스트* 속성 클래스, 구조체, 모듈 또는 인터페이스를 이어야 하며 소스 파일, 네임 스페이스, 프로시저 또는 차단 될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="21f81-174">This means the *declaration context* for a property must be a class, structure, module, or interface, and cannot be a source file, namespace, procedure, or block.</span></span> <span data-ttu-id="21f81-175">자세한 내용은 참조 [선언 컨텍스트 및 기본 액세스 수준](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="21f81-175">For more information, see [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>  
  
 <span data-ttu-id="21f81-176">기본적으로 속성 공용 액세스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="21f81-176">By default, properties use public access.</span></span> <span data-ttu-id="21f81-177">액세스 한정자는 속성의 액세스 수준을 조정할 수 있습니다는 `Property` 문의 하 고 필요에 따라 조정할 수 더 제한적인 액세스 수준에 해당 속성 프로시저 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="21f81-177">You can adjust a property's access level with an access modifier on the `Property` statement, and you can optionally adjust one of its property procedures to a more restrictive access level.</span></span>  
  
 <span data-ttu-id="21f81-178">Visual Basic에는 매개 변수를 전달 된 `Set` 속성을 할당 하는 동안 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="21f81-178">Visual Basic passes a parameter to the `Set` procedure during property assignments.</span></span> <span data-ttu-id="21f81-179">에 대 한 매개 변수를 제공 하지 않는 경우 `Set`, 라는 암시적 매개 변수를 사용 하는 통합된 개발 환경 (IDE) `value`합니다.</span><span class="sxs-lookup"><span data-stu-id="21f81-179">If you do not supply a parameter for `Set`, the integrated development environment (IDE) uses an implicit parameter named `value`.</span></span> <span data-ttu-id="21f81-180">이 매개 변수 속성에 할당할 값을 보유 합니다.</span><span class="sxs-lookup"><span data-stu-id="21f81-180">This parameter holds the value to be assigned to the property.</span></span> <span data-ttu-id="21f81-181">일반적으로 전용 지역 변수에이 값을 저장 하 고 반환 될 때마다는 `Get` 프로시저를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="21f81-181">You typically store this value in a private local variable and return it whenever the `Get` procedure is called.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="21f81-182">규칙</span><span class="sxs-lookup"><span data-stu-id="21f81-182">Rules</span></span>  
  
-   <span data-ttu-id="21f81-183">**혼합 된 액세스 수준입니다.**</span><span class="sxs-lookup"><span data-stu-id="21f81-183">**Mixed Access Levels.**</span></span> <span data-ttu-id="21f81-184">서로 다른 액세스 수준 중 하나에 대 한 선택적으로 지정할 수 읽기 / 쓰기 속성을 정의 하는 경우는 `Get` 또는 `Set` 절차를 사용 하지만 둘 다.</span><span class="sxs-lookup"><span data-stu-id="21f81-184">If you are defining a read-write property, you can optionally specify a different access level for either the `Get` or the `Set` procedure, but not both.</span></span> <span data-ttu-id="21f81-185">이 작업을 수행 하는 경우 프로시저 액세스 수준이 속성의 액세스 수준 보다 더 제한적 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="21f81-185">If you do this, the procedure access level must be more restrictive than the property's access level.</span></span> <span data-ttu-id="21f81-186">예를 들어 속성이 선언 된 경우 `Friend`, 선언할 수는 `Set` 프로시저 `Private`, 하지 않고 `Public`.</span><span class="sxs-lookup"><span data-stu-id="21f81-186">For example, if the property is declared `Friend`, you can declare the `Set` procedure `Private`, but not `Public`.</span></span>  
  
     <span data-ttu-id="21f81-187">정의 하는 경우는 `ReadOnly` 또는 `WriteOnly` 속성, 단일 속성 프로시저 (`Get` 또는 `Set`각각)은 모든 속성을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="21f81-187">If you are defining a `ReadOnly` or `WriteOnly` property, the single property procedure (`Get` or `Set`, respectively) represents all of the property.</span></span> <span data-ttu-id="21f81-188">속성에 대 한 두 개의 액세스 수준 설정 되므로 이러한 프로시저에 대 한 서로 다른 액세스 수준을 선언할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="21f81-188">You cannot declare a different access level for such a procedure, because that would set two access levels for the property.</span></span>  
  
-   <span data-ttu-id="21f81-189">**반환 형식입니다.**</span><span class="sxs-lookup"><span data-stu-id="21f81-189">**Return Type.**</span></span> <span data-ttu-id="21f81-190">`Property` 문은 반환 하는 값의 데이터 형식을 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21f81-190">The `Property` statement can declare the data type of the value it returns.</span></span> <span data-ttu-id="21f81-191">모든 데이터 형식이 나 열거형, 구조체, 클래스 또는 인터페이스의 이름을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21f81-191">You can specify any data type or the name of an enumeration, structure, class, or interface.</span></span>  
  
     <span data-ttu-id="21f81-192">지정 하지 않으면 `returntype`, 속성은 반환 `Object`합니다.</span><span class="sxs-lookup"><span data-stu-id="21f81-192">If you do not specify `returntype`, the property returns `Object`.</span></span>  
  
-   <span data-ttu-id="21f81-193">**구현입니다.**</span><span class="sxs-lookup"><span data-stu-id="21f81-193">**Implementation.**</span></span> <span data-ttu-id="21f81-194">이 속성을 사용 하는 경우는 `Implements` 키워드를 포함 하는 클래스나 구조체 있어야는 `Implements` 문 바로 다음의 `Class` 또는 `Structure` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="21f81-194">If this property uses the `Implements` keyword, the containing class or structure must have an `Implements` statement immediately following its `Class` or `Structure` statement.</span></span> <span data-ttu-id="21f81-195">`Implements` 각 인터페이스에 지정 된 문에 포함 해야 `implementslist`합니다.</span><span class="sxs-lookup"><span data-stu-id="21f81-195">The `Implements` statement must include each interface specified in `implementslist`.</span></span> <span data-ttu-id="21f81-196">그러나 인터페이스 정의는 이름에서 `Property` (에서 `definedname`)이이 속성의 이름이 같이 필요는 없습니다 (에서 `name`).</span><span class="sxs-lookup"><span data-stu-id="21f81-196">However, the name by which an interface defines the `Property` (in `definedname`) does not have to be the same as the name of this property (in `name`).</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="21f81-197">동작</span><span class="sxs-lookup"><span data-stu-id="21f81-197">Behavior</span></span>  
  
-   <span data-ttu-id="21f81-198">**속성 프로시저에서 반환합니다.**</span><span class="sxs-lookup"><span data-stu-id="21f81-198">**Returning from a Property Procedure.**</span></span> <span data-ttu-id="21f81-199">때는 `Get` 또는 `Set` 프로시저가 호출 코드로 반환 되 면 실행이 문을 호출한 다음 문을 사용 하 여 계속 합니다.</span><span class="sxs-lookup"><span data-stu-id="21f81-199">When the `Get` or `Set` procedure returns to the calling code, execution continues with the statement following the statement that invoked it.</span></span>  
  
     <span data-ttu-id="21f81-200">`Exit Property` 및 `Return` 문은 속성 프로시저를 즉시 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="21f81-200">The `Exit Property` and `Return` statements cause an immediate exit from a property procedure.</span></span> <span data-ttu-id="21f81-201">개수에 관계 없이 `Exit Property` 및 `Return` 문을 프로시저에서 아무 곳 이나 나타날 수 있으며 혼합할 수 `Exit Property` 및 `Return` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="21f81-201">Any number of `Exit Property` and `Return` statements can appear anywhere in the procedure, and you can mix `Exit Property` and `Return` statements.</span></span>  
  
-   <span data-ttu-id="21f81-202">**값을 반환 합니다.**</span><span class="sxs-lookup"><span data-stu-id="21f81-202">**Return Value.**</span></span> <span data-ttu-id="21f81-203">값을 반환 하는 `Get` 프로시저, 속성 이름에 값을 할당 하거나 포함 한 `Return` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="21f81-203">To return a value from a `Get` procedure, you can either assign the value to the property name or include it in a `Return` statement.</span></span> <span data-ttu-id="21f81-204">다음 예제에서는 속성 이름에 반환 값을 할당 `quoteForTheDay` 다음 사용 하 여는 `Exit Property` 문을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="21f81-204">The following example assigns the return value to the property name `quoteForTheDay` and then uses the `Exit Property` statement to return.</span></span>  
  
     <span data-ttu-id="21f81-205">[!code-vb[VbVbalrStatements #&27;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="21f81-205">[!code-vb[VbVbalrStatements#27](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_1.vb)]</span></span>  
  
     <span data-ttu-id="21f81-206">[!code-vb[VbVbalrStatements #&28;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="21f81-206">[!code-vb[VbVbalrStatements#28](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_2.vb)]</span></span>  
  
     <span data-ttu-id="21f81-207">사용 하는 경우 `Exit Property` 값을 할당 하지 않고 `name`, `Get` 프로시저 속성의 데이터 형식에 대 한 기본 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="21f81-207">If you use `Exit Property` without assigning a value to `name`, the `Get` procedure returns the default value for the property's data type.</span></span>  
  
     <span data-ttu-id="21f81-208">`Return` 문을 동시에 할당 된 `Get` 프로시저 반환 값의 절차를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="21f81-208">The `Return` statement at the same time assigns the `Get` procedure return value and exits the procedure.</span></span> <span data-ttu-id="21f81-209">다음 예제에서는이 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="21f81-209">The following example shows this.</span></span>  
  
     <span data-ttu-id="21f81-210">[!code-vb[VbVbalrStatements #&27;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="21f81-210">[!code-vb[VbVbalrStatements#27](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_1.vb)]</span></span>  
  
     <span data-ttu-id="21f81-211">[!code-vb[VbVbalrStatements #&29;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="21f81-211">[!code-vb[VbVbalrStatements#29](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_3.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="21f81-212">예제</span><span class="sxs-lookup"><span data-stu-id="21f81-212">Example</span></span>  
 <span data-ttu-id="21f81-213">다음 예제에서는 클래스에서 속성을 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="21f81-213">The following example declares a property in a class.</span></span>  
  
 <span data-ttu-id="21f81-214">[!code-vb[VbVbalrStatements #&51;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="21f81-214">[!code-vb[VbVbalrStatements#51](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_4.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21f81-215">참고 항목</span><span class="sxs-lookup"><span data-stu-id="21f81-215">See Also</span></span>  
 <span data-ttu-id="21f81-216">[자동 구현 속성](../../../visual-basic/programming-guide/language-features/procedures/auto-implemented-properties.md) </span><span class="sxs-lookup"><span data-stu-id="21f81-216">[Auto-Implemented Properties](../../../visual-basic/programming-guide/language-features/procedures/auto-implemented-properties.md) </span></span>  
<span data-ttu-id="21f81-217"> [개체 및 클래스](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md) </span><span class="sxs-lookup"><span data-stu-id="21f81-217"> [Objects and Classes](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md) </span></span>  
<span data-ttu-id="21f81-218"> [Get 문](../../../visual-basic/language-reference/statements/get-statement.md) </span><span class="sxs-lookup"><span data-stu-id="21f81-218"> [Get Statement](../../../visual-basic/language-reference/statements/get-statement.md) </span></span>  
<span data-ttu-id="21f81-219"> [Set 문](../../../visual-basic/language-reference/statements/set-statement.md) </span><span class="sxs-lookup"><span data-stu-id="21f81-219"> [Set Statement](../../../visual-basic/language-reference/statements/set-statement.md) </span></span>  
<span data-ttu-id="21f81-220"> [매개 변수 목록](../../../visual-basic/language-reference/statements/parameter-list.md) </span><span class="sxs-lookup"><span data-stu-id="21f81-220"> [Parameter List](../../../visual-basic/language-reference/statements/parameter-list.md) </span></span>  
<span data-ttu-id="21f81-221"> [기본](../../../visual-basic/language-reference/modifiers/default.md)</span><span class="sxs-lookup"><span data-stu-id="21f81-221"> [Default](../../../visual-basic/language-reference/modifiers/default.md)</span></span>

