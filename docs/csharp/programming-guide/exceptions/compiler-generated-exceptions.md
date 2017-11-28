---
title: "컴파일러 생성 예외(C# 프로그래밍 가이드)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords: exceptions [C#], compiler-generated
ms.assetid: 53b52f97-b366-4ed7-b05b-9eb78096b7f9
caps.latest.revision: "13"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: d1417e42f588978d5fc1beca4ad55463502ee219
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="compiler-generated-exceptions-c-programming-guide"></a><span data-ttu-id="d3429-102">컴파일러 생성 예외(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="d3429-102">Compiler-Generated Exceptions (C# Programming Guide)</span></span>
<span data-ttu-id="d3429-103">기본 작업이 실패하면 .NET Framework의 CLR(공용 언어 런타임)에 의해 자동으로 일부 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3429-103">Some exceptions are thrown automatically by the .NET Framework's common language runtime (CLR) when basic operations fail.</span></span> <span data-ttu-id="d3429-104">이러한 예외와 관련 오류 조건이 다음 표에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3429-104">These exceptions and their error conditions are listed in the following table.</span></span>  
  
|<span data-ttu-id="d3429-105">예외</span><span class="sxs-lookup"><span data-stu-id="d3429-105">Exception</span></span>|<span data-ttu-id="d3429-106">설명</span><span class="sxs-lookup"><span data-stu-id="d3429-106">Description</span></span>|  
|---------------|-----------------|  
|<xref:System.ArithmeticException>|<span data-ttu-id="d3429-107"><xref:System.DivideByZeroException>, <xref:System.OverflowException> 등의 산술 연산 중에 발생하는 예외에 대한 기본 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="d3429-107">A base class for exceptions that occur during arithmetic operations, such as <xref:System.DivideByZeroException> and <xref:System.OverflowException>.</span></span>|  
|<xref:System.ArrayTypeMismatchException>|<span data-ttu-id="d3429-108">제공된 요소의 실제 형식이 배열의 실제 형식과 호환되지 않아 배열이 요소를 저장할 수 없는 경우 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3429-108">Thrown when an array cannot store a given element because the actual type of the element is incompatible with the actual type of the array.</span></span>|  
|<xref:System.DivideByZeroException>|<span data-ttu-id="d3429-109">정수 값을 0으로 나누려고 시도할 경우 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3429-109">Thrown when an attempt is made to divide an integral value by zero.</span></span>|  
|<xref:System.IndexOutOfRangeException>|<span data-ttu-id="d3429-110">인덱스가 0보다 작거나 배열 경계를 벗어날 때 배열을 인덱싱하려고 시도할 경우 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3429-110">Thrown when an attempt is made to index an array when the index is less than zero or outside the bounds of the array.</span></span>|  
|<xref:System.InvalidCastException>|<span data-ttu-id="d3429-111">기본 형식에서 인터페이스 또는 파생 형식으로의 명시적 변환이 런타임에 실패할 경우 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3429-111">Thrown when an explicit conversion from a base type to an interface or to a derived type fails at runtime.</span></span>|  
|<xref:System.NullReferenceException>|<span data-ttu-id="d3429-112">값이 [null](../../../csharp/language-reference/keywords/null.md)인 개체를 참조하려고 시도할 경우 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3429-112">Thrown when you attempt to reference an object whose value is [null](../../../csharp/language-reference/keywords/null.md).</span></span>|  
|<xref:System.OutOfMemoryException>|<span data-ttu-id="d3429-113">[new](../../../csharp/language-reference/keywords/new-operator.md) 연산자를 사용한 메모리 할당 시도가 실패할 경우 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3429-113">Thrown when an attempt to allocate memory using the [new](../../../csharp/language-reference/keywords/new-operator.md) operator fails.</span></span> <span data-ttu-id="d3429-114">이 예외는 공용 언어 런타임에 사용할 수 있는 메모리가 모두 사용되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d3429-114">This indicates that the memory available to the common language runtime has been exhausted.</span></span>|  
|<xref:System.OverflowException>|<span data-ttu-id="d3429-115">`checked` 컨텍스트의 산술 연산이 오버플로될 경우 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3429-115">Thrown when an arithmetic operation in a `checked` context overflows.</span></span>|  
|<xref:System.StackOverflowException>|<span data-ttu-id="d3429-116">보류 중인 메서드 호출이 너무 많아 실행 스택이 모두 사용될 경우 throw됩니다. 대개 매우 깊은 재귀나 무한 재귀를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d3429-116">Thrown when the execution stack is exhausted by having too many pending method calls; usually indicates a very deep or infinite recursion.</span></span>|  
|<xref:System.TypeInitializationException>|<span data-ttu-id="d3429-117">정적 생성자가 예외를 throw하고 이 예외를 catch할 수 있는 호환되는 `catch` 절이 없는 경우 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3429-117">Thrown when a static constructor throws an exception and no compatible `catch` clause exists to catch it.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d3429-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d3429-118">See Also</span></span>  
 [<span data-ttu-id="d3429-119">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="d3429-119">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="d3429-120">예외 및 예외 처리</span><span class="sxs-lookup"><span data-stu-id="d3429-120">Exceptions and Exception Handling</span></span>](../../../csharp/programming-guide/exceptions/index.md)  
 [<span data-ttu-id="d3429-121">예외 처리</span><span class="sxs-lookup"><span data-stu-id="d3429-121">Exception Handling</span></span>](../../../csharp/programming-guide/exceptions/exception-handling.md)  
 [<span data-ttu-id="d3429-122">try-catch</span><span class="sxs-lookup"><span data-stu-id="d3429-122">try-catch</span></span>](../../../csharp/language-reference/keywords/try-catch.md)  
 [<span data-ttu-id="d3429-123">try-finally</span><span class="sxs-lookup"><span data-stu-id="d3429-123">try-finally</span></span>](../../../csharp/language-reference/keywords/try-finally.md)  
 [<span data-ttu-id="d3429-124">try-catch-finally</span><span class="sxs-lookup"><span data-stu-id="d3429-124">try-catch-finally</span></span>](../../../csharp/language-reference/keywords/try-catch-finally.md)
