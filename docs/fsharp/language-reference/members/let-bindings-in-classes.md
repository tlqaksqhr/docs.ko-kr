---
title: 클래스의 let 바인딩(F#)
description: "클래스 정의에서 'let' 바인딩을 사용 하 여 private 필드 및 F # 클래스에 대 한 전용 함수를 정의 하는 방법을 알아봅니다."
ms.date: 05/16/2016
ms.openlocfilehash: 1c17fe0edec14c28c9bdde86d0a2acb7c886cdf7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33564549"
---
# <a name="let-bindings-in-classes"></a><span data-ttu-id="22462-103">클래스의 let 바인딩</span><span class="sxs-lookup"><span data-stu-id="22462-103">let Bindings in Classes</span></span>

<span data-ttu-id="22462-104">Private 필드 및 F # 클래스에 대 한 전용 함수를 사용 하 여 정의할 수 있습니다 `let` 클래스 정의에 바인딩.</span><span class="sxs-lookup"><span data-stu-id="22462-104">You can define private fields and private functions for F# classes by using `let` bindings in the class definition.</span></span>


## <a name="syntax"></a><span data-ttu-id="22462-105">구문</span><span class="sxs-lookup"><span data-stu-id="22462-105">Syntax</span></span>

```fsharp
// Field.
[static] let [ mutable ] binding1 [ and ... binding-n ]

// Function.
[static] let [ rec ] binding1 [ and ... binding-n ]
```

## <a name="remarks"></a><span data-ttu-id="22462-106">설명</span><span class="sxs-lookup"><span data-stu-id="22462-106">Remarks</span></span>
<span data-ttu-id="22462-107">위 구문 자 클래스 상속 및 제목을 선언 뒤, 다른 모든 멤버 정의 앞에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="22462-107">The previous syntax appears after the class heading and inheritance declarations but before any member definitions.</span></span> <span data-ttu-id="22462-108">구문은 `let` 클래스에 제한 된 범위가 클래스, 하지만 클래스에 정의 된 이름은 외부에서 바인딩.</span><span class="sxs-lookup"><span data-stu-id="22462-108">The syntax is like that of `let` bindings outside of classes, but the names defined in a class have a scope that is limited to the class.</span></span> <span data-ttu-id="22462-109">A `let` 바인딩을 전용 필드 또는 데이터를 노출 하려면 함수를 통해 또는 함수는 속성 또는 멤버 메서드를 공개적으로 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="22462-109">A `let` binding creates a private field or function; to expose data or functions publicly, declare a property or a member method.</span></span>

<span data-ttu-id="22462-110">A `let` 바인딩에 없는 정적 인스턴스 라고 `let` 바인딩.</span><span class="sxs-lookup"><span data-stu-id="22462-110">A `let` binding that is not static is called an instance `let` binding.</span></span> <span data-ttu-id="22462-111">인스턴스 `let` 바인딩은 개체가 만들어질 때 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="22462-111">Instance `let` bindings execute when objects are created.</span></span> <span data-ttu-id="22462-112">정적 `let` 바인딩 형식을 처음으로 사용 하기 전에 실행 되는 클래스에 대 한 정적 이니셜라이저의 일부인 합니다.</span><span class="sxs-lookup"><span data-stu-id="22462-112">Static `let` bindings are part of the static initializer for the class, which is guaranteed to execute before the type is first used.</span></span>

<span data-ttu-id="22462-113">인스턴스 내에서 코드 `let` 바인딩에서는 기본 생성자의 매개 변수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22462-113">The code within instance `let` bindings can use the primary constructor's parameters.</span></span>

<span data-ttu-id="22462-114">특성 및 액세스 가능성 한정자에 허용 되지 않는 `let` 클래스에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="22462-114">Attributes and accessibility modifiers are not permitted on `let` bindings in classes.</span></span>

<span data-ttu-id="22462-115">다음 코드 예제에서는 여러 유형의 설명 `let` 클래스에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="22462-115">The following code examples illustrate several types of `let` bindings in classes.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3001.fs)]

<span data-ttu-id="22462-116">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="22462-116">The output is as follows.</span></span>

```
10 52 1 204
```

## <a name="alternative-ways-to-create-fields"></a><span data-ttu-id="22462-117">필드를 만드는 다른 방법</span><span class="sxs-lookup"><span data-stu-id="22462-117">Alternative Ways to Create Fields</span></span>
<span data-ttu-id="22462-118">사용할 수도 있습니다는 `val` 키워드 전용 필드를 만들려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="22462-118">You can also use the `val` keyword to create a private field.</span></span> <span data-ttu-id="22462-119">사용 하는 경우는 `val` 키워드를 필드 값이 주어 지는 개체를 만들었지만 대신 기본 값으로 초기화 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="22462-119">When using the `val` keyword, the field is not given a value when the object is created, but instead is initialized with a default value.</span></span> <span data-ttu-id="22462-120">자세한 내용은 참조 [명시적 필드: val 키워드](explicit-fields-the-val-keyword.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="22462-120">For more information, see [Explicit Fields: The val Keyword](explicit-fields-the-val-keyword.md).</span></span>

<span data-ttu-id="22462-121">멤버 정의 사용 하는 키워드를 추가 하 여 클래스에서 private 필드를 정의할 수도 있습니다 `private` 을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="22462-121">You can also define private fields in a class by using a member definition and adding the keyword `private` to the definition.</span></span> <span data-ttu-id="22462-122">이 코드를 다시 작성 하지 않고 멤버의 액세스 가능성을 변경 하려는 경우에 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22462-122">This can be useful if you expect to change the accessibility of a member without rewriting your code.</span></span> <span data-ttu-id="22462-123">자세한 내용은 [액세스 제어](../access-control.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="22462-123">For more information, see [Access Control](../access-control.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="22462-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="22462-124">See Also</span></span>
[<span data-ttu-id="22462-125">멤버</span><span class="sxs-lookup"><span data-stu-id="22462-125">Members</span></span>](index.md)

[<span data-ttu-id="22462-126">클래스의 `do` 바인딩</span><span class="sxs-lookup"><span data-stu-id="22462-126">`do` Bindings in Classes</span></span>](do-bindings-in-classes.md)

[<span data-ttu-id="22462-127">`let` 바인딩</span><span class="sxs-lookup"><span data-stu-id="22462-127">`let` Bindings</span></span>](../functions/let-bindings.md)
