---
title: "예외 형식(F#)"
description: "정의 및 F # 예외 형식을 사용 하는 방법을 알아봅니다."
keywords: "visual f#, f#, 함수형 프로그래밍"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: e850205a-b8da-459e-8f6d-cb3510f8f173
ms.openlocfilehash: a0864218841396c0ebdf26c7585e0e5bb778f83e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="exception-types"></a><span data-ttu-id="b8370-104">예외 형식</span><span class="sxs-lookup"><span data-stu-id="b8370-104">Exception Types</span></span>

<span data-ttu-id="b8370-105">두 종류의 F #에서 예외:.NET 예외 형식 및 F # 예외 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="b8370-105">There are two categories of exceptions in F#: .NET exception types and F# exception types.</span></span> <span data-ttu-id="b8370-106">이 항목에서는 정의 하 고 F # 예외 형식을 사용 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8370-106">This topic describes how to define and use F# exception types.</span></span>


## <a name="syntax"></a><span data-ttu-id="b8370-107">구문</span><span class="sxs-lookup"><span data-stu-id="b8370-107">Syntax</span></span>

```fsharp
exception exception-type of argument-type
```

## <a name="remarks"></a><span data-ttu-id="b8370-108">설명</span><span class="sxs-lookup"><span data-stu-id="b8370-108">Remarks</span></span>
<span data-ttu-id="b8370-109">위 구문에서 *예외 형식을* 새 F # 예외 유형, 이름 및 *인수 형식* 이 유형의 예외를 발생 시킬 때 제공할 수 있는 인수 형식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b8370-109">In the previous syntax, *exception-type* is the name of a new F# exception type, and *argument-type* represents the type of an argument that can be supplied when you raise an exception of this type.</span></span> <span data-ttu-id="b8370-110">에 대 한 튜플을 유형을 사용 하 여 여러 인수를 지정할 수 있습니다 *인수 형식*합니다.</span><span class="sxs-lookup"><span data-stu-id="b8370-110">You can specify multiple arguments by using a tuple type for *argument-type*.</span></span>

<span data-ttu-id="b8370-111">F # 예외에 대 한 일반적인 정의 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b8370-111">A typical definition for an F# exception resembles the following.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5501.fs)]

<span data-ttu-id="b8370-112">사용 하 여 이러한 유형의 예외를 생성할 수 있습니다는 `raise` 다음과 같이 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8370-112">You can generate an exception of this type by using the `raise` function, as follows.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5502.fs)]

<span data-ttu-id="b8370-113">F # 예외 형식에 있는 필터에서 직접 사용할 수 있습니다는 `try...with` 다음 예제와 같이 식입니다.</span><span class="sxs-lookup"><span data-stu-id="b8370-113">You can use an F# exception type directly in the filters in a `try...with` expression, as shown in the following example.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5503.fs)]

<span data-ttu-id="b8370-114">정의 된 예외 형식을 `exception` F #에 키워드는에서 상속 되는 새 형식을 `System.Exception`합니다.</span><span class="sxs-lookup"><span data-stu-id="b8370-114">The exception type that you define with the `exception` keyword in F# is a new type that inherits from `System.Exception`.</span></span>


## <a name="see-also"></a><span data-ttu-id="b8370-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b8370-115">See Also</span></span>
[<span data-ttu-id="b8370-116">예외 처리</span><span class="sxs-lookup"><span data-stu-id="b8370-116">Exception Handling</span></span>](index.md)

[<span data-ttu-id="b8370-117">예외: `raise` 함수</span><span class="sxs-lookup"><span data-stu-id="b8370-117">Exceptions: the `raise` Function</span></span>](the-raise-function.md)

[<span data-ttu-id="b8370-118">예외 계층</span><span class="sxs-lookup"><span data-stu-id="b8370-118">Exception Hierarchy</span></span>](https://msdn.microsoft.com/library/z4c5tckx.aspx)
