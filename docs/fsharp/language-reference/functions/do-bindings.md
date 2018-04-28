---
title: do 바인딩(F#)
description: "F # 'do' 바인딩을 하는 방법을 함수나 값을 정의 하지 않고 코드 실행에 대해 알아봅니다."
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 4c63da0c5e2f4130d59f9efa6bc54a55e5fe9fd8
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="do-bindings"></a><span data-ttu-id="86ea0-103">do 바인딩</span><span class="sxs-lookup"><span data-stu-id="86ea0-103">do Bindings</span></span>

<span data-ttu-id="86ea0-104">A `do` 코드를 실행 하는 함수 또는 값을 정의 하지 않고 바인딩이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="86ea0-104">A `do` binding is used to execute code without defining a function or value.</span></span> <span data-ttu-id="86ea0-105">수행 바인딩 수도 있습니다 참조 클래스에 사용 [ `do` 클래스에서](../members/do-bindings-in-classes.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="86ea0-105">Also, do bindings can be used in classes, see [`do` Bindings in Classes](../members/do-bindings-in-classes.md).</span></span>


## <a name="syntax"></a><span data-ttu-id="86ea0-106">구문</span><span class="sxs-lookup"><span data-stu-id="86ea0-106">Syntax</span></span>

```fsharp
[ attributes ]
[ do ]expression
```

## <a name="remarks"></a><span data-ttu-id="86ea0-107">설명</span><span class="sxs-lookup"><span data-stu-id="86ea0-107">Remarks</span></span>
<span data-ttu-id="86ea0-108">사용 하 여 한 `do` 바인딩 함수 또는 값의 정의 의존 하지 않고 코드를 실행 하려는 경우.</span><span class="sxs-lookup"><span data-stu-id="86ea0-108">Use a `do` binding when you want to execute code independently of a function or value definition.</span></span> <span data-ttu-id="86ea0-109">식에는 `do` 바인딩 반환 해야 `unit`합니다.</span><span class="sxs-lookup"><span data-stu-id="86ea0-109">The expression in a `do` binding must return `unit`.</span></span> <span data-ttu-id="86ea0-110">최상위 수준에서 코드 `do` 바인딩 모듈 초기화 될 때 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="86ea0-110">Code in a top-level `do` binding is executed when the module is initialized.</span></span> <span data-ttu-id="86ea0-111">키워드 `do` 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="86ea0-111">The keyword `do` is optional.</span></span>

<span data-ttu-id="86ea0-112">최상위 수준에 특성을 적용할 수 있습니다 `do` 바인딩.</span><span class="sxs-lookup"><span data-stu-id="86ea0-112">Attributes can be applied to a top-level `do` binding.</span></span> <span data-ttu-id="86ea0-113">예를 들어 프로그램에서 COM interop를 사용 하는 경우 적용할는 `STAThread` 를 프로그램 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="86ea0-113">For example, if your program uses COM interop, you might want to apply the `STAThread` attribute to your program.</span></span> <span data-ttu-id="86ea0-114">에 특성을 사용 하 여이 작업을 수행할 수는 `do` 바인딩, 다음 코드에 나와 있는 것 처럼 합니다.</span><span class="sxs-lookup"><span data-stu-id="86ea0-114">You can do this by using an attribute on a `do` binding, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet201.fs)]
    
## <a name="see-also"></a><span data-ttu-id="86ea0-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="86ea0-115">See Also</span></span>
[<span data-ttu-id="86ea0-116">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="86ea0-116">F# Language Reference</span></span>](../index.md)

[<span data-ttu-id="86ea0-117">함수</span><span class="sxs-lookup"><span data-stu-id="86ea0-117">Functions</span></span>](index.md)

