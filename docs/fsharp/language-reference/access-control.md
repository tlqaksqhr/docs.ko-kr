---
title: Access Control(F#)
description: '형식, 메서드 및 F # 프로그래밍 언어의 함수 같은 프로그래밍 요소에 대 한 액세스를 제어 하는 방법에 알아봅니다.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: fee5f719904b61c3082d56f73448defdea39f472
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="access-control"></a><span data-ttu-id="7905f-103">Access Control</span><span class="sxs-lookup"><span data-stu-id="7905f-103">Access Control</span></span>

<span data-ttu-id="7905f-104">*액세스 제어* 클라이언트 유형, 메서드 및 함수 등의 특정 프로그램 요소를 사용할 수 있는 선언 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="7905f-104">*Access control* refers to declaring which clients can use certain program elements, such as types, methods, and functions.</span></span>


## <a name="basics-of-access-control"></a><span data-ttu-id="7905f-105">액세스 제어 기본 사항</span><span class="sxs-lookup"><span data-stu-id="7905f-105">Basics of Access Control</span></span>
<span data-ttu-id="7905f-106">F #에서 액세스 제어 지정자 `public`, `internal`, 및 `private` 모듈, 형식, 메서드, 값 정의 함수, 속성 및 명시적 필드에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7905f-106">In F#, the access control specifiers `public`, `internal`, and `private` can be applied to modules, types, methods, value definitions, functions, properties, and explicit fields.</span></span>


- <span data-ttu-id="7905f-107">`public` 모든 호출자가 엔터티를 액세스할 수 있는지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7905f-107">`public` indicates that the entity can be accessed by all callers.</span></span>

- <span data-ttu-id="7905f-108">`internal` 엔터티는 동일한 어셈블리 에서만에서 액세스할 수 있는지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7905f-108">`internal` indicates that the entity can be accessed only from the same assembly.</span></span>

- <span data-ttu-id="7905f-109">`private` 엔터티는 바깥쪽 형식 또는 모듈 에서만 액세스할 수 있는지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7905f-109">`private` indicates that the entity can be accessed only from the enclosing type or module.</span></span>


>[!NOTE] 
<span data-ttu-id="7905f-110">액세스 지정자 `protected` 지원 않는 언어로 작성 된 형식을 사용 하는 경우 허용 되는 F #에서 사용 되지 않습니다 `protected` 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="7905f-110">The access specifier `protected` is not used in F#, although it is acceptable if you are using types authored in languages that do support `protected` access.</span></span> <span data-ttu-id="7905f-111">따라서 보호 된 메서드를 재정의 하는 경우 메서드에 계속 클래스 및 해당 하위 요소 내 에서만 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7905f-111">Therefore, if you override a protected method, your method remains accessible only within the class and its descendents.</span></span>

<span data-ttu-id="7905f-112">지정자는 경우를 제외 하 고 엔터티 이름 앞에 옵니다 일반적으로 `mutable` 또는 `inline` 지정자만 사용 되는 액세스 제어 지정자 뒤에 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="7905f-112">In general, the specifier is put in front of the name of the entity, except when a `mutable` or `inline` specifier is used, which appear after the access control specifier.</span></span>

<span data-ttu-id="7905f-113">액세스 지정 자가 없는 사용 하는 경우 기본값은 `public`를 제외 하 고 `let` 항상 이며는 형식에 바인딩 `private` 형식으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="7905f-113">If no access specifier is used, the default is `public`, except for `let` bindings in a type, which are always `private` to the type.</span></span>

<span data-ttu-id="7905f-114">F #의 시그니처는 F # 프로그램 요소에 대 한 액세스를 제어 하기 위한 다른 메커니즘을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="7905f-114">Signatures in F# provide another mechanism for controlling access to F# program elements.</span></span> <span data-ttu-id="7905f-115">시그니처가는 액세스 제어에 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7905f-115">Signatures are not required for access control.</span></span> <span data-ttu-id="7905f-116">자세한 내용은 [시그니처](signatures.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7905f-116">For more information, see [Signatures](signatures.md).</span></span>


## <a name="rules-for-access-control"></a><span data-ttu-id="7905f-117">액세스 제어에 대 한 규칙</span><span class="sxs-lookup"><span data-stu-id="7905f-117">Rules for Access Control</span></span>
<span data-ttu-id="7905f-118">액세스 제어는 다음 규칙이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7905f-118">Access control is subject to the following rules:</span></span>


- <span data-ttu-id="7905f-119">상속 선언 (즉, 사용 `inherit` 클래스에 대 한 기본 클래스를 지정 하려면), 선언 (즉, 지정 하는 클래스 인터페이스를 구현), 인터페이스 및 추상 멤버에는 항상 바깥쪽 형식과 같은 동일한 수준의 액세스 권한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7905f-119">Inheritance declarations (that is, the use of `inherit` to specify a base class for a class), interface declarations (that is, specifying that a class implements an interface), and abstract members always have the same accessibility as the enclosing type.</span></span> <span data-ttu-id="7905f-120">따라서 이러한 구문에 대 한 액세스 제어 지정자를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7905f-120">Therefore, an access control specifier cannot be used on these constructs.</span></span>

- <span data-ttu-id="7905f-121">구별된 된 공용 구조체의 개별 사례 공용 구조체 형식에서 별도 액세스 제어 한정자를 가질 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7905f-121">Individual cases in a discriminated union cannot have their own access control modifiers separate from the union type.</span></span>

- <span data-ttu-id="7905f-122">레코드 종류의 개별 필드는 별도 레코드 종류의 액세스 제어 한정자를 가질 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7905f-122">Individual fields of a record type cannot have their own access control modifiers separate from the record type.</span></span>


## <a name="example"></a><span data-ttu-id="7905f-123">예제</span><span class="sxs-lookup"><span data-stu-id="7905f-123">Example</span></span>
<span data-ttu-id="7905f-124">다음 코드에서는 액세스 제어 지정자를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7905f-124">The following code illustrates the use of access control specifiers.</span></span> <span data-ttu-id="7905f-125">프로젝트에 두 개의 파일이 `Module1.fs` 및 `Module2.fs`합니다.</span><span class="sxs-lookup"><span data-stu-id="7905f-125">There are two files in the project, `Module1.fs` and `Module2.fs`.</span></span> <span data-ttu-id="7905f-126">각 파일은 암시적으로 모듈.</span><span class="sxs-lookup"><span data-stu-id="7905f-126">Each file is implicitly a module.</span></span> <span data-ttu-id="7905f-127">따라서 두 개의 모듈은 `Module1` 및 `Module2`합니다.</span><span class="sxs-lookup"><span data-stu-id="7905f-127">Therefore, there are two modules, `Module1` and `Module2`.</span></span> <span data-ttu-id="7905f-128">에 개인 형식 및 내부 형식에 정의 되어 `Module1`합니다.</span><span class="sxs-lookup"><span data-stu-id="7905f-128">A private type and an internal type are defined in `Module1`.</span></span> <span data-ttu-id="7905f-129">전용 형식에서 액세스할 수 없는 `Module2`, 뿐 아니라 내부 형식이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7905f-129">The private type cannot be accessed from `Module2`, but the internal type can.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/access-control/snippet1.fs)]
    
<span data-ttu-id="7905f-130">다음 코드에 만든 형식의 접근성 테스트 `Module1.fs`합니다.</span><span class="sxs-lookup"><span data-stu-id="7905f-130">The following code tests the accessibility of the types created in `Module1.fs`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/access-control/snippet2.fs)]
    
## <a name="see-also"></a><span data-ttu-id="7905f-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7905f-131">See Also</span></span>
[<span data-ttu-id="7905f-132">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="7905f-132">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="7905f-133">시그니처</span><span class="sxs-lookup"><span data-stu-id="7905f-133">Signatures</span></span>](signatures.md)
