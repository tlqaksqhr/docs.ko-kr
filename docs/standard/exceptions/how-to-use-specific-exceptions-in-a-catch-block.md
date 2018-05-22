---
title: '방법: Catch 블록에 특정 예외 사용'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- exceptions, try/catch blocks
- try/catch blocks
- catch blocks
ms.assetid: 12af9ff3-8587-4f31-90cf-6c2244e0fdae
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 424db46c879974a9859637f9a2a5dfcd4494a3c5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-use-specific-exceptions-in-a-catch-block"></a><span data-ttu-id="8f3b8-102">catch 블록에 특정 예외를 사용하는 방법</span><span class="sxs-lookup"><span data-stu-id="8f3b8-102">How to use specific exceptions in a catch block</span></span>

<span data-ttu-id="8f3b8-103">일반적으로 기본 `catch` 문을 사용하는 대신 특정 형식의 예외를 catch하는 것이 좋은 프로그래밍 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="8f3b8-103">In general, it's good programming practice to catch a specific type of exception rather than use a basic `catch` statement.</span></span>

<span data-ttu-id="8f3b8-104">예외가 발생하면 스택 위로 전달되며 각 catch 블록에 예외를 처리할 수 있는 기회가 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f3b8-104">When an exception occurs, it is passed up the stack and each catch block is given the opportunity to handle it.</span></span> <span data-ttu-id="8f3b8-105">catch 문의 순서가 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="8f3b8-105">The order of catch statements is important.</span></span> <span data-ttu-id="8f3b8-106">특정 예외를 대상으로 하는 catch 블록은 일반 예외 catch 블록 앞에 배치합니다. 그러지 않으면 컴파일러에서 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f3b8-106">Put catch blocks targeted to specific exceptions before a general exception catch block or the compiler might issue an error.</span></span> <span data-ttu-id="8f3b8-107">예외 형식을 catch 블록에 지정된 예외 이름과 비교하여 적절한 catch 블록을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="8f3b8-107">The proper catch block is determined by matching the type of the exception to the name of the exception specified in the catch block.</span></span> <span data-ttu-id="8f3b8-108">특정 catch 블록이 없는 경우 일반 catch 블록(있는 경우)에서 예외를 catch합니다.</span><span class="sxs-lookup"><span data-stu-id="8f3b8-108">If there is no specific catch block, the exception is caught by a general catch block, if one exists.</span></span>

<span data-ttu-id="8f3b8-109">다음 코드 예제에서는 `try`/`catch` 블록을 사용하여 <xref:System.InvalidCastException>을 catch합니다.</span><span class="sxs-lookup"><span data-stu-id="8f3b8-109">The following code example uses a `try`/`catch` block to catch an <xref:System.InvalidCastException>.</span></span> <span data-ttu-id="8f3b8-110">샘플에서는 직원 수준이라는 하나의 속성(`Emlevel`)이 있는 `Employee` 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8f3b8-110">The sample creates a class called `Employee` with a single property, employee level (`Emlevel`).</span></span> <span data-ttu-id="8f3b8-111">`PromoteEmployee` 메서드는 개체를 사용하고 직원 수준을 증가시킵니다.</span><span class="sxs-lookup"><span data-stu-id="8f3b8-111">A method, `PromoteEmployee`, takes an object and increments the employee level.</span></span> <span data-ttu-id="8f3b8-112"><xref:System.DateTime> 인스턴스가 `PromoteEmployee` 메서드로 전달될 때 <xref:System.InvalidCastException>이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="8f3b8-112">An <xref:System.InvalidCastException> occurs when a <xref:System.DateTime> instance is passed to the `PromoteEmployee` method.</span></span>

[!code-cpp[CatchException#2](../../../samples/snippets/cpp/VS_Snippets_CLR/CatchException/CPP/catchexception1.cpp#2)]
[!code-csharp[CatchException#2](../../../samples/snippets/csharp/VS_Snippets_CLR/CatchException/CS/catchexception1.cs#2)]
[!code-vb[CatchException#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CatchException/VB/catchexception1.vb#2)] 

## <a name="see-also"></a><span data-ttu-id="8f3b8-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8f3b8-113">See Also</span></span>  
[<span data-ttu-id="8f3b8-114">예외</span><span class="sxs-lookup"><span data-stu-id="8f3b8-114">Exceptions</span></span>](index.md)
