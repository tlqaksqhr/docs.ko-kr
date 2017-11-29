---
title: Access Control(F#)
description: "형식, 메서드 및 F # 프로그래밍 언어의 함수 같은 프로그래밍 요소에 대 한 액세스를 제어 하는 방법에 알아봅니다."
keywords: "visual f#, f#, 함수형 프로그래밍"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 955b06fe-d1cd-431d-8db6-93e83b697453
ms.openlocfilehash: a02e20a585a0456577901f2762a0eeb0e3ecd2f0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="access-control"></a><span data-ttu-id="92b01-104">Access Control</span><span class="sxs-lookup"><span data-stu-id="92b01-104">Access Control</span></span>

<span data-ttu-id="92b01-105">*액세스 제어* 클라이언트 유형, 메서드 및 함수 등의 특정 프로그램 요소를 사용할 수 있는 선언 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="92b01-105">*Access control* refers to declaring which clients can use certain program elements, such as types, methods, and functions.</span></span>


## <a name="basics-of-access-control"></a><span data-ttu-id="92b01-106">액세스 제어 기본 사항</span><span class="sxs-lookup"><span data-stu-id="92b01-106">Basics of Access Control</span></span>
<span data-ttu-id="92b01-107">F #에서 액세스 제어 지정자 `public`, `internal`, 및 `private` 모듈, 형식, 메서드, 값 정의 함수, 속성 및 명시적 필드에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92b01-107">In F#, the access control specifiers `public`, `internal`, and `private` can be applied to modules, types, methods, value definitions, functions, properties, and explicit fields.</span></span>


- <span data-ttu-id="92b01-108">`public`모든 호출자가 엔터티를 액세스할 수 있는지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="92b01-108">`public` indicates that the entity can be accessed by all callers.</span></span>

- <span data-ttu-id="92b01-109">`internal`엔터티는 동일한 어셈블리 에서만에서 액세스할 수 있는지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="92b01-109">`internal` indicates that the entity can be accessed only from the same assembly.</span></span>

- <span data-ttu-id="92b01-110">`private`엔터티는 바깥쪽 형식 또는 모듈 에서만 액세스할 수 있는지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="92b01-110">`private` indicates that the entity can be accessed only from the enclosing type or module.</span></span>


>[!NOTE] 
<span data-ttu-id="92b01-111">액세스 지정자 `protected` 지원 않는 언어로 작성 된 형식을 사용 하는 경우 허용 되는 F #에서 사용 되지 않습니다 `protected` 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="92b01-111">The access specifier `protected` is not used in F#, although it is acceptable if you are using types authored in languages that do support `protected` access.</span></span> <span data-ttu-id="92b01-112">따라서 보호 된 메서드를 재정의 하는 경우 메서드에 계속 클래스 및 해당 하위 요소 내 에서만 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92b01-112">Therefore, if you override a protected method, your method remains accessible only within the class and its descendents.</span></span>

<span data-ttu-id="92b01-113">지정자는 경우를 제외 하 고 엔터티 이름 앞에 옵니다 일반적으로 `mutable` 또는 `inline` 지정자만 사용 되는 액세스 제어 지정자 뒤에 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="92b01-113">In general, the specifier is put in front of the name of the entity, except when a `mutable` or `inline` specifier is used, which appear after the access control specifier.</span></span>

<span data-ttu-id="92b01-114">액세스 지정 자가 없는 사용 하는 경우 기본값은 `public`를 제외 하 고 `let` 항상 이며는 형식에 바인딩 `private` 형식으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="92b01-114">If no access specifier is used, the default is `public`, except for `let` bindings in a type, which are always `private` to the type.</span></span>

<span data-ttu-id="92b01-115">F #의 시그니처는 F # 프로그램 요소에 대 한 액세스를 제어 하기 위한 다른 메커니즘을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="92b01-115">Signatures in F# provide another mechanism for controlling access to F# program elements.</span></span> <span data-ttu-id="92b01-116">시그니처가는 액세스 제어에 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="92b01-116">Signatures are not required for access control.</span></span> <span data-ttu-id="92b01-117">자세한 내용은 [시그니처](signatures.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="92b01-117">For more information, see [Signatures](signatures.md).</span></span>


## <a name="rules-for-access-control"></a><span data-ttu-id="92b01-118">액세스 제어에 대 한 규칙</span><span class="sxs-lookup"><span data-stu-id="92b01-118">Rules for Access Control</span></span>
<span data-ttu-id="92b01-119">액세스 제어는 다음 규칙이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="92b01-119">Access control is subject to the following rules:</span></span>


- <span data-ttu-id="92b01-120">상속 선언 (즉, 사용 `inherit` 클래스에 대 한 기본 클래스를 지정 하려면), 선언 (즉, 지정 하는 클래스 인터페이스를 구현), 인터페이스 및 추상 멤버에는 항상 바깥쪽 형식과 같은 동일한 수준의 액세스 권한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92b01-120">Inheritance declarations (that is, the use of `inherit` to specify a base class for a class), interface declarations (that is, specifying that a class implements an interface), and abstract members always have the same accessibility as the enclosing type.</span></span> <span data-ttu-id="92b01-121">따라서 이러한 구문에 대 한 액세스 제어 지정자를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="92b01-121">Therefore, an access control specifier cannot be used on these constructs.</span></span>

- <span data-ttu-id="92b01-122">구별된 된 공용 구조체의 개별 사례 공용 구조체 형식에서 별도 액세스 제어 한정자를 가질 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="92b01-122">Individual cases in a discriminated union cannot have their own access control modifiers separate from the union type.</span></span>

- <span data-ttu-id="92b01-123">레코드 종류의 개별 필드는 별도 레코드 종류의 액세스 제어 한정자를 가질 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="92b01-123">Individual fields of a record type cannot have their own access control modifiers separate from the record type.</span></span>


## <a name="example"></a><span data-ttu-id="92b01-124">예제</span><span class="sxs-lookup"><span data-stu-id="92b01-124">Example</span></span>
<span data-ttu-id="92b01-125">다음 코드에서는 액세스 제어 지정자를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="92b01-125">The following code illustrates the use of access control specifiers.</span></span> <span data-ttu-id="92b01-126">프로젝트에 두 개의 파일이 `Module1.fs` 및 `Module2.fs`합니다.</span><span class="sxs-lookup"><span data-stu-id="92b01-126">There are two files in the project, `Module1.fs` and `Module2.fs`.</span></span> <span data-ttu-id="92b01-127">각 파일은 암시적으로 모듈.</span><span class="sxs-lookup"><span data-stu-id="92b01-127">Each file is implicitly a module.</span></span> <span data-ttu-id="92b01-128">따라서 두 개의 모듈은 `Module1` 및 `Module2`합니다.</span><span class="sxs-lookup"><span data-stu-id="92b01-128">Therefore, there are two modules, `Module1` and `Module2`.</span></span> <span data-ttu-id="92b01-129">에 개인 형식 및 내부 형식에 정의 되어 `Module1`합니다.</span><span class="sxs-lookup"><span data-stu-id="92b01-129">A private type and an internal type are defined in `Module1`.</span></span> <span data-ttu-id="92b01-130">전용 형식에서 액세스할 수 없는 `Module2`, 뿐 아니라 내부 형식이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92b01-130">The private type cannot be accessed from `Module2`, but the internal type can.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/access-control/snippet1.fs)]
    
<span data-ttu-id="92b01-131">다음 코드에 만든 형식의 접근성 테스트 `Module1.fs`합니다.</span><span class="sxs-lookup"><span data-stu-id="92b01-131">The following code tests the accessibility of the types created in `Module1.fs`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/access-control/snippet2.fs)]
    
## <a name="see-also"></a><span data-ttu-id="92b01-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="92b01-132">See Also</span></span>
[<span data-ttu-id="92b01-133">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="92b01-133">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="92b01-134">시그니처</span><span class="sxs-lookup"><span data-stu-id="92b01-134">Signatures</span></span>](signatures.md)
