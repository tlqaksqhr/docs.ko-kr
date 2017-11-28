---
title: "인덱싱된 속성(F#)"
description: "F # 인덱싱된 속성을 속성 정렬 된 데이터에 대 한 배열 유사 액세스를 제공 하는 방법을 알아봅니다."
keywords: "visual f#, f#, 함수형 프로그래밍"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: f1266b8b-e2e3-4f49-9332-65c6d34dc0f3
ms.openlocfilehash: 78a09a70621e82f073346471e68ec826359641d6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="indexed-properties"></a><span data-ttu-id="5c696-104">인덱싱된 속성</span><span class="sxs-lookup"><span data-stu-id="5c696-104">Indexed Properties</span></span>

<span data-ttu-id="5c696-105">*인덱싱된 속성* 속성에 대 한 배열 유사 액세스를 제공 하는 데이터를 정렬 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c696-105">*Indexed properties* are properties that provide array-like access to ordered data.</span></span>


## <a name="syntax"></a><span data-ttu-id="5c696-106">구문</span><span class="sxs-lookup"><span data-stu-id="5c696-106">Syntax</span></span>

```fsharp
// Indexed property that has both get and set defined.
member self-identifier.PropertyName
    with get(index-variable) =
        get-function-body
    and set index-variablesvalue-variables =
        set-function-body

// Indexed property that has get only.
member self-identifier.PropertyName(index-variable) =
    get-function-body

// Alternative syntax for indexed property with get only
member self-identifier.PropertyName
    with get(index-variables) =
        get-function-body

// Indexed property that has set only.
member self-identifier.PropertyName
    with set index-variablesvalue-variables = 
        set-function-body
```

## <a name="remarks"></a><span data-ttu-id="5c696-107">설명</span><span class="sxs-lookup"><span data-stu-id="5c696-107">Remarks</span></span>
<span data-ttu-id="5c696-108">이전 구문에는 세 가지 형식 모두에 포함 된 인덱싱된 속성을 정의 하는 방법을 보여 줍니다는 `get` 및 `set` 메서드를가 `get` 메서드만 수도 있고 한 `set` 메서드만 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c696-108">The three forms of the previous syntax show how to define indexed properties that have both a `get` and a `set` method, have a `get` method only, or have a `set` method only.</span></span> <span data-ttu-id="5c696-109">만 get 및 set만 표시 된 구문에 대 한 표시 된 구문은 모두 결합 하 고 get과 set 갖고 있는 속성을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c696-109">You can also combine both the syntax shown for get only and the syntax shown for set only, and produce a property that has both get and set.</span></span> <span data-ttu-id="5c696-110">이 마지막 형식을 get에 서로 다른 접근성 한정자 및 특성을 배치 하 고 방법을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c696-110">This latter form allows you to put different accessibility modifiers and attributes on the get and set methods.</span></span>

<span data-ttu-id="5c696-111">경우는 *PropertyName* 은 `Item`, 컴파일러는 인덱싱된 기본 속성으로 속성을 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c696-111">When the *PropertyName* is `Item`, the compiler treats the property as a default indexed property.</span></span> <span data-ttu-id="5c696-112">A *인덱싱된 기본 속성* 개체 인스턴스에서 배열 유사 구문을 사용 하 여 액세스할 수 있는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="5c696-112">A *default indexed property* is a property that you can access by using array-like syntax on the object instance.</span></span> <span data-ttu-id="5c696-113">예를 들어 경우 `obj` 구문을이 속성을 정의 하는 형식의 개체인 `obj.[index]` 속성에 액세스 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c696-113">For example, if `obj` is an object of the type that defines this property, the syntax `obj.[index]` is used to access the property.</span></span>

<span data-ttu-id="5c696-114">인덱싱된 속성은 속성 및 괄호로 인덱스의 이름을 제공 하기 위해 기본값이 아닌에 액세스 하기 위한 구문입니다.</span><span class="sxs-lookup"><span data-stu-id="5c696-114">The syntax for accessing a nondefault indexed property is to provide the name of the property and the index in parentheses.</span></span> <span data-ttu-id="5c696-115">예를 들어 속성 `Ordinal`, 작성 `obj.Ordinal(index)` 에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c696-115">For example, if the property is `Ordinal`, you write `obj.Ordinal(index)` to access it.</span></span>

<span data-ttu-id="5c696-116">형식을 사용 하는에 관계 없이 항상 사용 해야 변환된에 대 한 형식을 `set` 인덱싱된 속성에는 메서드.</span><span class="sxs-lookup"><span data-stu-id="5c696-116">Regardless of which form you use, you should always use the curried form for the `set` method on an indexed property.</span></span> <span data-ttu-id="5c696-117">커리 된 함수에 대 한 정보를 참조 하십시오. [함수](../functions/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5c696-117">For information about curried functions, see [Functions](../functions/index.md).</span></span>

## <a name="example"></a><span data-ttu-id="5c696-118">예제</span><span class="sxs-lookup"><span data-stu-id="5c696-118">Example</span></span>

<span data-ttu-id="5c696-119">다음 코드 예제에서는 정 및 기본 및 get 및 set 메서드는 기본이 아닌 인덱싱된 속성의 사용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5c696-119">The following code example illustrates the definition and use of default and non-default indexed properties that have get and set methods.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3301.fs)]

## <a name="output"></a><span data-ttu-id="5c696-120">출력</span><span class="sxs-lookup"><span data-stu-id="5c696-120">Output</span></span>

```
ONE two three four five six seven eight nine ten
ONE first two second three third four fourth five fifth six 6th
seven seventh eight eighth nine ninth ten tenth
```

## <a name="indexed-properties-with-multiple-index-variables"></a><span data-ttu-id="5c696-121">여러 인덱스 변수를 사용 하 여 인덱싱된 속성</span><span class="sxs-lookup"><span data-stu-id="5c696-121">Indexed Properties with Multiple Index Variables</span></span>
<span data-ttu-id="5c696-122">인덱싱된 속성에는 인덱스 변수는 여러 개 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c696-122">Indexed properties can have more than one index variable.</span></span> <span data-ttu-id="5c696-123">이 경우 변수는 속성을 사용 하면 쉼표로 구분 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c696-123">In that case, the variables are separated by commas when the property is used.</span></span> <span data-ttu-id="5c696-124">이러한 속성의 set 메서드에는 첫 번째는 키가 포함 된 튜플이 및 중 두 번째 설정 되는 값은 두 커리 된 인수가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c696-124">The set method in such a property must have two curried arguments, the first of which is a tuple containing the keys, and the second of which is the value being set.</span></span>

<span data-ttu-id="5c696-125">다음 코드는 여러 개의 인덱스 변수로 인덱싱된 속성의 사용법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="5c696-125">The following code demonstrates the use of an indexed property with multiple index variables.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3302.fs)]
    
## <a name="see-also"></a><span data-ttu-id="5c696-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5c696-126">See Also</span></span>
[<span data-ttu-id="5c696-127">멤버</span><span class="sxs-lookup"><span data-stu-id="5c696-127">Members</span></span>](index.md)
