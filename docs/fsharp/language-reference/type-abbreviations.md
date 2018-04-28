---
title: 형식 약어(F#)
description: '형식에 이름을 보다 의미 있는 코드를 보다 쉽게 읽을 수 있도록 F # 형식 약어에 알아봅니다.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: bf17ee9795947fdc11fe958f09d52f5730b95bf8
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="type-abbreviations"></a><span data-ttu-id="4df22-103">형식 약어</span><span class="sxs-lookup"><span data-stu-id="4df22-103">Type Abbreviations</span></span>

<span data-ttu-id="4df22-104">A *형식 약어* 별칭 또는 유형에 대 한 대체 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="4df22-104">A *type abbreviation* is an alias or alternate name for a type.</span></span>

## <a name="syntax"></a><span data-ttu-id="4df22-105">구문</span><span class="sxs-lookup"><span data-stu-id="4df22-105">Syntax</span></span>

```fsharp
type type-abbreviation = type-name
```

## <a name="remarks"></a><span data-ttu-id="4df22-106">설명</span><span class="sxs-lookup"><span data-stu-id="4df22-106">Remarks</span></span>
<span data-ttu-id="4df22-107">코드를 보다 쉽게 읽을 수 있도록 형식을 더 의미 있는 이름을 부여 하려면 형식 약어를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4df22-107">You can use type abbreviations to give a type a more meaningful name, in order to make code easier to read.</span></span> <span data-ttu-id="4df22-108">작성 하는 경우 다루기 되는 형식에 대 한 사용 하기 쉬운 이름을 만들 수도 사용할 수 있습니다. 또한 쉽게 형식을 사용 하는 모든 코드를 변경 하지 않고 내부 형식을 변경할 수 있도록 형식 약어를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4df22-108">You can also use them to create an easy to use name for a type that is otherwise cumbersome to write out. Additionally, you can use type abbreviations to make it easier to change an underlying type without changing all the code that uses the type.</span></span> <span data-ttu-id="4df22-109">다음은 단순 형식 약어입니다.</span><span class="sxs-lookup"><span data-stu-id="4df22-109">The following is a simple type abbreviation.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2301.fs)]

<span data-ttu-id="4df22-110">형식 약어에는 다음 코드 에서처럼 일반 매개 변수를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4df22-110">Type abbreviations can include generic parameters, as in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2302.fs)]

<span data-ttu-id="4df22-111">이전 코드에서 `Transform` 동일한 형식의 단일 값을 반환 하 고 모든 형식의 단일 인수를 사용 하는 함수를 나타내는 형식 약어입니다.</span><span class="sxs-lookup"><span data-stu-id="4df22-111">In the previous code, `Transform` is a type abbreviation that represents a function that takes a single argument of any type and that returns a single value of that same type.</span></span>

<span data-ttu-id="4df22-112">.NET Framework MSIL 코드에서 형식 약어 유지 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4df22-112">Type abbreviations are not preserved in the .NET Framework MSIL code.</span></span> <span data-ttu-id="4df22-113">따라서 다른.NET Framework 언어에서 F # 어셈블리를 사용 하면 형식 약어에 대 한 내부 형식 이름을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4df22-113">Therefore, when you use an F# assembly from another .NET Framework language, you must use the underlying type name for a type abbreviation.</span></span>

<span data-ttu-id="4df22-114">측정 단위에 형식 약어를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4df22-114">Type abbreviations can also be used on units of measure.</span></span> <span data-ttu-id="4df22-115">자세한 내용은 참조 [측정 단위를](units-of-measure.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4df22-115">For more information, see [Units of Measure](units-of-measure.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="4df22-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4df22-116">See Also</span></span>
[<span data-ttu-id="4df22-117">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="4df22-117">F# Language Reference</span></span>](index.md)

