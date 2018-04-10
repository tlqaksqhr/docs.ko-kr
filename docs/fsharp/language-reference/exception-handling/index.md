---
title: 예외 처리(F#)
description: 'F #에서 예외 처리의 기본 사항을 설명 하 고 식과 함수를 처리 하는 예외에 대 한 링크를 찾습니다.'
keywords: visual f#, f#, 함수형 프로그래밍
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: ad475c4a-d94e-47d9-b27b-3ff000b65f8e
ms.openlocfilehash: b61af66e0a70fdf9b86df37418c0284957d1f99e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="exception-handling"></a><span data-ttu-id="04156-104">예외 처리</span><span class="sxs-lookup"><span data-stu-id="04156-104">Exception Handling</span></span>

<span data-ttu-id="04156-105">이 섹션에서는 F# 언어의 예외 처리 지원에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="04156-105">This section contains information about exception handling support in the F# language.</span></span>


## <a name="exception-handling-basics"></a><span data-ttu-id="04156-106">예외 처리 기본 사항</span><span class="sxs-lookup"><span data-stu-id="04156-106">Exception Handling Basics</span></span>
<span data-ttu-id="04156-107">예외 처리는 .NET Framework의 오류 조건을 처리하는 표준 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="04156-107">Exception handling is the standard way of handling error conditions in the .NET Framework.</span></span> <span data-ttu-id="04156-108">따라서 F#을 비롯한 모든 .NET 언어는 이 메커니즘을 지원해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="04156-108">Thus, any .NET language must support this mechanism, including F#.</span></span> <span data-ttu-id="04156-109">*예외*는 오류에 대한 정보를 캡슐화하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="04156-109">An *exception* is an object that encapsulates information about an error.</span></span> <span data-ttu-id="04156-110">오류가 발생하면 예외가 발생하고 정상적인 실행이 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="04156-110">When errors occur, exceptions are raised and regular execution stops.</span></span> <span data-ttu-id="04156-111">대신, 런타임에서 예외에 대한 적절한 처리기를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="04156-111">Instead, the runtime searches for an appropriate handler for the exception.</span></span> <span data-ttu-id="04156-112">검색은 현재 함수에서 시작하고, 일치하는 처리기를 찾을 때까지 호출자의 계층을 통해 스택을 나아갑니다.</span><span class="sxs-lookup"><span data-stu-id="04156-112">The search starts in the current function, and proceeds up the stack through the layers of callers until a matching handler is found.</span></span> <span data-ttu-id="04156-113">그런 다음 처리기가 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="04156-113">Then the handler is executed.</span></span>

<span data-ttu-id="04156-114">또한 스택이 해제될 때, 런타임이 `finally` 블록에서 모든 코드를 실행하여 해제 프로세스 중 개체가 올바르게 정리되도록 보장합니다.</span><span class="sxs-lookup"><span data-stu-id="04156-114">In addition, as the stack is unwound, the runtime executes any code in `finally` blocks, to guarantee that objects are cleaned up correctly during the unwinding process.</span></span>


## <a name="related-topics"></a><span data-ttu-id="04156-115">관련 항목</span><span class="sxs-lookup"><span data-stu-id="04156-115">Related Topics</span></span>

|<span data-ttu-id="04156-116">제목</span><span class="sxs-lookup"><span data-stu-id="04156-116">Title</span></span>|<span data-ttu-id="04156-117">설명</span><span class="sxs-lookup"><span data-stu-id="04156-117">Description</span></span>|
|-----|-----------|
|[<span data-ttu-id="04156-118">예외 형식</span><span class="sxs-lookup"><span data-stu-id="04156-118">Exception Types</span></span>](exception-types.md)|<span data-ttu-id="04156-119">예외 형식을 선언하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="04156-119">Describes how to declare an exception type.</span></span>|
|[<span data-ttu-id="04156-120">예외: `try...with` 식</span><span class="sxs-lookup"><span data-stu-id="04156-120">Exceptions: The `try...with` Expression</span></span>](the-try-with-expression.md)|<span data-ttu-id="04156-121">예외 처리를 지원하는 언어 구문에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="04156-121">Describes the language construct that supports exception handling.</span></span>|
|[<span data-ttu-id="04156-122">예외: `try...finally` 식</span><span class="sxs-lookup"><span data-stu-id="04156-122">Exceptions: The `try...finally` Expression</span></span>](the-try-finally-expression.md)|<span data-ttu-id="04156-123">예외가 throw될 때 스택이 해제되므로 정리 코드를 실행할 수 있는 언어 구문에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="04156-123">Describes the language construct that enables you to execute clean-up code as the stack unwinds when an exception is thrown.</span></span>|
|[<span data-ttu-id="04156-124">예외: `raise` 함수</span><span class="sxs-lookup"><span data-stu-id="04156-124">Exceptions: the `raise` Function</span></span>](the-raise-Function.md)|<span data-ttu-id="04156-125">예외 개체를 throw하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="04156-125">Describes how to throw an exception object.</span></span>|
|[<span data-ttu-id="04156-126">예외: `failwith` 함수</span><span class="sxs-lookup"><span data-stu-id="04156-126">Exceptions: The `failwith` Function</span></span>](the-failwith-function.md)|<span data-ttu-id="04156-127">일반 F# 예외를 생성하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="04156-127">Describes how to generate a general F# exception.</span></span>|
|[<span data-ttu-id="04156-128">예외: `invalidArg` 함수</span><span class="sxs-lookup"><span data-stu-id="04156-128">Exceptions: The `invalidArg` Function</span></span>](the-invalidArg-function.md)|<span data-ttu-id="04156-129">잘못된 인수 예외를 생성하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="04156-129">Describes how to generate an invalid argument exception.</span></span>|
