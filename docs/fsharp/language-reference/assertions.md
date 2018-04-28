---
title: 어설션(F#)
description: "F # 프로그래밍 언어에서 식 테스트에 대 한 디버깅 기능으로 'assert' 식을 사용 하는 방법에 알아봅니다."
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 195b4a34977a63d92559003b5cd0bb89490a1e7a
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="assertions"></a><span data-ttu-id="a2ced-103">어설션</span><span class="sxs-lookup"><span data-stu-id="a2ced-103">Assertions</span></span>

<span data-ttu-id="a2ced-104">`assert` 식은 식을 테스트 하는 데 사용할 수 있는 디버깅 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2ced-104">The `assert` expression is a debugging feature that you can use to test an expression.</span></span> <span data-ttu-id="a2ced-105">디버그 모드에서 실패 시 어설션에서 시스템 오류 대화 상자를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="a2ced-105">Upon failure in Debug mode, an assertion generates a system error dialog box.</span></span>

## <a name="syntax"></a><span data-ttu-id="a2ced-106">구문</span><span class="sxs-lookup"><span data-stu-id="a2ced-106">Syntax</span></span>

```fsharp
assert condition
```

## <a name="remarks"></a><span data-ttu-id="a2ced-107">설명</span><span class="sxs-lookup"><span data-stu-id="a2ced-107">Remarks</span></span>

<span data-ttu-id="a2ced-108">`assert` 식에는 형식이 `bool -> unit`합니다.</span><span class="sxs-lookup"><span data-stu-id="a2ced-108">The `assert` expression has type `bool -> unit`.</span></span>

<span data-ttu-id="a2ced-109">위 구문에서 *조건* 테스트할 하는 부울 식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a2ced-109">In the previous syntax, *condition* represents a Boolean expression that is to be tested.</span></span> <span data-ttu-id="a2ced-110">식이 계산 되는 경우 `true`, 실행이 계속 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a2ced-110">If the expression evaluates to `true`, execution continues unaffected.</span></span> <span data-ttu-id="a2ced-111">로 평가 되 면 `false`, 시스템 오류 대화 상자가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="a2ced-111">If it evaluates to `false`, a system error dialog box is generated.</span></span> <span data-ttu-id="a2ced-112">오류 대화 상자에 문자열을 포함 하는 캡션을 **어설션 오류**합니다.</span><span class="sxs-lookup"><span data-stu-id="a2ced-112">The error dialog box has a caption that contains the string **Assertion Failed**.</span></span> <span data-ttu-id="a2ced-113">대화 상자에 어설션 오류가 발생 한을 나타내는 스택 추적을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2ced-113">The dialog box contains a stack trace that indicates where the assertion failure occurred.</span></span>

<span data-ttu-id="a2ced-114">디버그 모드에서 컴파일할 때에 사용할 수는 어설션 검사 즉, 경우 상수 `DEBUG` 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2ced-114">Assertion checking is enabled only when you compile in Debug mode; that is, if the constant `DEBUG` is defined.</span></span> <span data-ttu-id="a2ced-115">기본적으로 프로젝트 시스템에서의 `DEBUG` 상수 릴리스 구성에 없습니다. 디버그 구성에서 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2ced-115">In the project system, by default, the `DEBUG` constant is defined in the Debug configuration but not in the Release configuration.</span></span>

<span data-ttu-id="a2ced-116">F # 예외 처리를 사용 하 여 어설션 실패 오류를 낼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a2ced-116">The assertion failure error cannot be caught by using F# exception handling.</span></span>

>[!NOTE]
<span data-ttu-id="a2ced-117">`assert` 함수는 <xref:System.Diagnostics.Debug.Assert*?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="a2ced-117">The `assert` function resolves to <xref:System.Diagnostics.Debug.Assert*?displayProperty=nameWithType>.</span></span>

## <a name="example"></a><span data-ttu-id="a2ced-118">예제</span><span class="sxs-lookup"><span data-stu-id="a2ced-118">Example</span></span>

<span data-ttu-id="a2ced-119">다음 코드 예제에서는 `assert` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="a2ced-119">The following code example illustrates the use of the `assert` expression.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5401.fs)]
    
## <a name="see-also"></a><span data-ttu-id="a2ced-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a2ced-120">See Also</span></span>

[<span data-ttu-id="a2ced-121">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="a2ced-121">F# Language Reference</span></span>](index.md)
