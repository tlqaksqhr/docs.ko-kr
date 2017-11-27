---
title: "do 바인딩(F#)"
description: "F # 'do' 바인딩을 하는 방법을 함수나 값을 정의 하지 않고 코드 실행에 대해 알아봅니다."
keywords: "visual f#, f#, 함수형 프로그래밍"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 4c1057a3-3aa1-4b64-b46a-25ffe33f0be9
ms.openlocfilehash: f2563d384b67c005c96c2ff487c786476d385e70
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="do-bindings"></a><span data-ttu-id="d837c-104">do 바인딩</span><span class="sxs-lookup"><span data-stu-id="d837c-104">do Bindings</span></span>

<span data-ttu-id="d837c-105">A `do` 코드를 실행 하는 함수 또는 값을 정의 하지 않고 바인딩이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d837c-105">A `do` binding is used to execute code without defining a function or value.</span></span> <span data-ttu-id="d837c-106">수행 바인딩 수도 있습니다 참조 클래스에 사용 [ `do` 클래스에서](../members/do-bindings-in-classes.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d837c-106">Also, do bindings can be used in classes, see [`do` Bindings in Classes](../members/do-bindings-in-classes.md).</span></span>


## <a name="syntax"></a><span data-ttu-id="d837c-107">구문</span><span class="sxs-lookup"><span data-stu-id="d837c-107">Syntax</span></span>

```fsharp
[ attributes ]
[ do ]expression
```

## <a name="remarks"></a><span data-ttu-id="d837c-108">설명</span><span class="sxs-lookup"><span data-stu-id="d837c-108">Remarks</span></span>
<span data-ttu-id="d837c-109">사용 하 여 한 `do` 바인딩 함수 또는 값의 정의 의존 하지 않고 코드를 실행 하려는 경우.</span><span class="sxs-lookup"><span data-stu-id="d837c-109">Use a `do` binding when you want to execute code independently of a function or value definition.</span></span> <span data-ttu-id="d837c-110">식에는 `do` 바인딩 반환 해야 `unit`합니다.</span><span class="sxs-lookup"><span data-stu-id="d837c-110">The expression in a `do` binding must return `unit`.</span></span> <span data-ttu-id="d837c-111">최상위 수준에서 코드 `do` 바인딩 모듈 초기화 될 때 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d837c-111">Code in a top-level `do` binding is executed when the module is initialized.</span></span> <span data-ttu-id="d837c-112">키워드 `do` 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="d837c-112">The keyword `do` is optional.</span></span>

<span data-ttu-id="d837c-113">최상위 수준에 특성을 적용할 수 있습니다 `do` 바인딩.</span><span class="sxs-lookup"><span data-stu-id="d837c-113">Attributes can be applied to a top-level `do` binding.</span></span> <span data-ttu-id="d837c-114">예를 들어 프로그램에서 COM interop를 사용 하는 경우 적용할는 `STAThread` 를 프로그램 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="d837c-114">For example, if your program uses COM interop, you might want to apply the `STAThread` attribute to your program.</span></span> <span data-ttu-id="d837c-115">에 특성을 사용 하 여이 작업을 수행할 수는 `do` 바인딩, 다음 코드에 나와 있는 것 처럼 합니다.</span><span class="sxs-lookup"><span data-stu-id="d837c-115">You can do this by using an attribute on a `do` binding, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet201.fs)]
    
## <a name="see-also"></a><span data-ttu-id="d837c-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d837c-116">See Also</span></span>
[<span data-ttu-id="d837c-117">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="d837c-117">F# Language Reference</span></span>](../index.md)

[<span data-ttu-id="d837c-118">함수</span><span class="sxs-lookup"><span data-stu-id="d837c-118">Functions</span></span>](index.md)

