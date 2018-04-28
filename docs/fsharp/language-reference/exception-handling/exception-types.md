---
title: 예외 형식(F#)
description: '정의 및 F # 예외 형식을 사용 하는 방법을 알아봅니다.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 6aaa5cd1b94f829b98d5aed5dcf6e30472a8b751
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="exception-types"></a><span data-ttu-id="9e3b3-103">예외 형식</span><span class="sxs-lookup"><span data-stu-id="9e3b3-103">Exception Types</span></span>

<span data-ttu-id="9e3b3-104">두 종류의 F #에서 예외:.NET 예외 형식 및 F # 예외 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="9e3b3-104">There are two categories of exceptions in F#: .NET exception types and F# exception types.</span></span> <span data-ttu-id="9e3b3-105">이 항목에서는 정의 하 고 F # 예외 형식을 사용 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e3b3-105">This topic describes how to define and use F# exception types.</span></span>


## <a name="syntax"></a><span data-ttu-id="9e3b3-106">구문</span><span class="sxs-lookup"><span data-stu-id="9e3b3-106">Syntax</span></span>

```fsharp
exception exception-type of argument-type
```

## <a name="remarks"></a><span data-ttu-id="9e3b3-107">설명</span><span class="sxs-lookup"><span data-stu-id="9e3b3-107">Remarks</span></span>
<span data-ttu-id="9e3b3-108">위 구문에서 *예외 형식을* 새 F # 예외 유형, 이름 및 *인수 형식* 이 유형의 예외를 발생 시킬 때 제공할 수 있는 인수 형식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9e3b3-108">In the previous syntax, *exception-type* is the name of a new F# exception type, and *argument-type* represents the type of an argument that can be supplied when you raise an exception of this type.</span></span> <span data-ttu-id="9e3b3-109">에 대 한 튜플을 유형을 사용 하 여 여러 인수를 지정할 수 있습니다 *인수 형식*합니다.</span><span class="sxs-lookup"><span data-stu-id="9e3b3-109">You can specify multiple arguments by using a tuple type for *argument-type*.</span></span>

<span data-ttu-id="9e3b3-110">F # 예외에 대 한 일반적인 정의 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9e3b3-110">A typical definition for an F# exception resembles the following.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5501.fs)]

<span data-ttu-id="9e3b3-111">사용 하 여 이러한 유형의 예외를 생성할 수 있습니다는 `raise` 다음과 같이 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e3b3-111">You can generate an exception of this type by using the `raise` function, as follows.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5502.fs)]

<span data-ttu-id="9e3b3-112">F # 예외 형식에 있는 필터에서 직접 사용할 수 있습니다는 `try...with` 다음 예제와 같이 식입니다.</span><span class="sxs-lookup"><span data-stu-id="9e3b3-112">You can use an F# exception type directly in the filters in a `try...with` expression, as shown in the following example.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5503.fs)]

<span data-ttu-id="9e3b3-113">정의 된 예외 형식을 `exception` F #에 키워드는에서 상속 되는 새 형식을 `System.Exception`합니다.</span><span class="sxs-lookup"><span data-stu-id="9e3b3-113">The exception type that you define with the `exception` keyword in F# is a new type that inherits from `System.Exception`.</span></span>


## <a name="see-also"></a><span data-ttu-id="9e3b3-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9e3b3-114">See Also</span></span>
[<span data-ttu-id="9e3b3-115">예외 처리</span><span class="sxs-lookup"><span data-stu-id="9e3b3-115">Exception Handling</span></span>](index.md)

[<span data-ttu-id="9e3b3-116">예외: `raise` 함수</span><span class="sxs-lookup"><span data-stu-id="9e3b3-116">Exceptions: the `raise` Function</span></span>](the-raise-function.md)

[<span data-ttu-id="9e3b3-117">예외 계층</span><span class="sxs-lookup"><span data-stu-id="9e3b3-117">Exception Hierarchy</span></span>](https://msdn.microsoft.com/library/z4c5tckx.aspx)
