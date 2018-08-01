---
title: 예외 Throw
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- exceptions, throwing
- explicitly throwing exceptions
- throwing exceptions, design guidelines
ms.assetid: 5388e02b-52f5-460e-a2b5-eeafe60eeebe
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7a493e6591d90ce05a652e48807f63fa90764a91
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33573723"
---
# <a name="exception-throwing"></a><span data-ttu-id="d3fe9-102">예외 Throw</span><span class="sxs-lookup"><span data-stu-id="d3fe9-102">Exception Throwing</span></span>
<span data-ttu-id="d3fe9-103">이 섹션에서 설명 하는 예외 throw 지침 실행이 실패의 의미를 정의 하는 것 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fe9-103">Exception-throwing guidelines described in this section require a good definition of the meaning of execution failure.</span></span> <span data-ttu-id="d3fe9-104">구성원을 수행할 수 없는 될 때마다 실행 오류가 발생 (어떤 멤버 이름을 의미 함)를 수행 하도록 설계 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fe9-104">Execution failure occurs whenever a member cannot do what it was designed to do (what the member name implies).</span></span> <span data-ttu-id="d3fe9-105">예를 들어 경우는 `OpenFile` 메서드 호출자에 게 열려 있는 파일 핸들을 반환할 수 없습니다, 실행 실패로 간주 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fe9-105">For example, if the `OpenFile` method cannot return an opened file handle to the caller, it would be considered an execution failure.</span></span>  
  
 <span data-ttu-id="d3fe9-106">대부분의 개발자 나누기와 같은 사용 오류에 대 한 예외를 사용 하 여 0 또는 null 참조 하 여 익숙하지 되 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3fe9-106">Most developers have become comfortable with using exceptions for usage errors such as division by zero or null references.</span></span> <span data-ttu-id="d3fe9-107">프레임 워크에서 예외는 실행 오류를 비롯 한 모든 오류 조건에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3fe9-107">In the Framework, exceptions are used for all error conditions, including execution errors.</span></span>  
  
 <span data-ttu-id="d3fe9-108">**X DO NOT** 오류 코드를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fe9-108">**X DO NOT** return error codes.</span></span>  
  
 <span data-ttu-id="d3fe9-109">예외는 프레임 워크에서 오류를 보고 하는 기본 수단입니다.</span><span class="sxs-lookup"><span data-stu-id="d3fe9-109">Exceptions are the primary means of reporting errors in frameworks.</span></span>  
  
 <span data-ttu-id="d3fe9-110">**✓ DO** 예외를 throw 하 여 실행 실패를 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fe9-110">**✓ DO** report execution failures by throwing exceptions.</span></span>  
  
 <span data-ttu-id="d3fe9-111">**✓ CONSIDER** 호출 하 여 프로세스를 종료 `System.Environment.FailFast` (.NET Framework 2.0 기능) 코드 분석기에서 안전 하 게 더 이상 실행 하지 않은 상황이 발생 하는 경우 예외를 throw 하는 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fe9-111">**✓ CONSIDER** terminating the process by calling `System.Environment.FailFast` (.NET Framework 2.0 feature) instead of throwing an exception if your code encounters a situation where it is unsafe for further execution.</span></span>  
  
 <span data-ttu-id="d3fe9-112">**X DO NOT** 가능 하면 정상적인 제어 흐름에 대 한 예외를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fe9-112">**X DO NOT** use exceptions for the normal flow of control, if possible.</span></span>  
  
 <span data-ttu-id="d3fe9-113">시스템 오류 및 잠재적 경합 상태를 사용 하 여 작업을 제외 하 고 사용자가 예외를 throw 하지 않는 코드를 작성할 수 있도록 프레임 워크 디자이너 Api를 디자인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fe9-113">Except for system failures and operations with potential race conditions, framework designers should design APIs so users can write code that does not throw exceptions.</span></span> <span data-ttu-id="d3fe9-114">예를 들어 사용자가 예외를 throw 하지 않는 코드를 작성할 수 있도록 멤버를 호출 하기 전에 사전 조건을 확인 하는 방법을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3fe9-114">For example, you can provide a way to check preconditions before calling a member so users can write code that does not throw exceptions.</span></span>  
  
 <span data-ttu-id="d3fe9-115">다른 멤버의 사전 조건을 확인 하는 데 사용 되는 멤버 라고 테스터 및 실제로 작업을 수행 하는 멤버는 doer가 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3fe9-115">The member used to check preconditions of another member is often referred to as a tester, and the member that actually does the work is called a doer.</span></span>  
  
 <span data-ttu-id="d3fe9-116">다음과 같은 경우 Tester-doer 패턴에서 성능 오버 헤드를 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3fe9-116">There are cases when the Tester-Doer Pattern can have an unacceptable performance overhead.</span></span> <span data-ttu-id="d3fe9-117">이러한 경우 소위 시도 구문 분석 패턴 고려할지 (참조 [예외 및 성능](../../../docs/standard/design-guidelines/exceptions-and-performance.md) 에 대 한 자세한 내용은).</span><span class="sxs-lookup"><span data-stu-id="d3fe9-117">In such cases, the so-called Try-Parse Pattern should be considered (see [Exceptions and Performance](../../../docs/standard/design-guidelines/exceptions-and-performance.md) for more information).</span></span>  
  
 <span data-ttu-id="d3fe9-118">**✓ CONSIDER** 성능에 미치는 영향 예외를 throw 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fe9-118">**✓ CONSIDER** the performance implications of throwing exceptions.</span></span> <span data-ttu-id="d3fe9-119">Throw 비율 초당 100 보다 큰가 눈에 띄게 대부분의 응용 프로그램의 성능에 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3fe9-119">Throw rates above 100 per second are likely to noticeably impact the performance of most applications.</span></span>  
  
 <span data-ttu-id="d3fe9-120">**✓ DO** 문서 멤버의 위반으로 인해 공개적으로 호출할 수 멤버에 의해 throw 되는 모든 예외 (아니라 시스템 오류) 계약 및 계약의 일부로 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fe9-120">**✓ DO** document all exceptions thrown by publicly callable members because of a violation of the member contract (rather than a system failure) and treat them as part of your contract.</span></span>  
  
 <span data-ttu-id="d3fe9-121">계약의 일부인 예외 다음으로 한 버전에서 변경 하지 않아야 (즉, 예외 형식을 변경 하지 않아야 및 새 예외 추가할 수 없습니다).</span><span class="sxs-lookup"><span data-stu-id="d3fe9-121">Exceptions that are a part of the contract should not change from one version to the next (i.e., exception type should not change, and new exceptions should not be added).</span></span>  
  
 <span data-ttu-id="d3fe9-122">**X DO NOT** throw 하거나 수 있는 public 멤버가 일부 옵션에 기반 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fe9-122">**X DO NOT** have public members that can either throw or not based on some option.</span></span>  
  
 <span data-ttu-id="d3fe9-123">**X DO NOT** 는 반환 값으로 예외를 반환 하는 공용 멤버만 또는 `out` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="d3fe9-123">**X DO NOT** have public members that return exceptions as the return value or an `out` parameter.</span></span>  
  
 <span data-ttu-id="d3fe9-124">많은 예외 기반의 오류 보고의 혜택을 막습니다 예외를 throw 할 때 해당 하는 대신 공용 Api에서 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fe9-124">Returning exceptions from public APIs instead of throwing them defeats many of the benefits of exception-based error reporting.</span></span>  
  
 <span data-ttu-id="d3fe9-125">**✓ CONSIDER** 예외 작성기 메서드를 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fe9-125">**✓ CONSIDER** using exception builder methods.</span></span>  
  
 <span data-ttu-id="d3fe9-126">것을 다른 위치에서 동일한 예외를 throw 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fe9-126">It is common to throw the same exception from different places.</span></span> <span data-ttu-id="d3fe9-127">코드 크기를 늘리지를 방지 하려면 예외를 만들고 해당 속성을 초기화 하는 도우미 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fe9-127">To avoid code bloat, use helper methods that create exceptions and initialize their properties.</span></span>  
  
 <span data-ttu-id="d3fe9-128">예외를 throw 하는 멤버 가져오지 않습니다. 또한 인라인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fe9-128">Also, members that throw exceptions are not getting inlined.</span></span> <span data-ttu-id="d3fe9-129">작성기 내에 throw 문을 이동 인라인 될 멤버를 통합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3fe9-129">Moving the throw statement inside the builder might allow the member to be inlined.</span></span>  
  
 <span data-ttu-id="d3fe9-130">**X DO NOT** 예외 필터 블록에서 예외를 throw 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fe9-130">**X DO NOT** throw exceptions from exception filter blocks.</span></span>  
  
 <span data-ttu-id="d3fe9-131">예외 필터에서 예외가 발생 하는 경우 예외는 CLR에서 발견 했습니다 및 필터는 false를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fe9-131">When an exception filter raises an exception, the exception is caught by the CLR, and the filter returns false.</span></span> <span data-ttu-id="d3fe9-132">이 동작은 실행 하 고 명시적으로 false 반환 필터 구분 되지 않습니다 이므로 디버그 하기 매우 어렵습니다.</span><span class="sxs-lookup"><span data-stu-id="d3fe9-132">This behavior is indistinguishable from the filter executing and returning false explicitly and is therefore very difficult to debug.</span></span>  
  
 <span data-ttu-id="d3fe9-133">**X AVOID** 명시적으로 finally 블록에서 예외를 throw 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fe9-133">**X AVOID** explicitly throwing exceptions from finally blocks.</span></span> <span data-ttu-id="d3fe9-134">throw 하는 메서드를 호출 하 여 발생 하는 암시적으로 throw 된 예외를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3fe9-134">Implicitly thrown exceptions resulting from calling methods that throw are acceptable.</span></span>  
  
 <span data-ttu-id="d3fe9-135">*Portions © 2005, 2009 Microsoft Corporation. 모든 권리 보유.*</span><span class="sxs-lookup"><span data-stu-id="d3fe9-135">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="d3fe9-136">*피어슨 교육, Inc.에서의 사용 권한으로 재인쇄 [Framework 디자인 지침: 규칙, 특징 및 다시 사용할 수 있는.NET 라이브러리를 2nd Edition에 대 한 패턴](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina 및 Brad Abrams 게시 하 여 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로: Addison Wesley Professional.*</span><span class="sxs-lookup"><span data-stu-id="d3fe9-136">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3fe9-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d3fe9-137">See Also</span></span>  
 [<span data-ttu-id="d3fe9-138">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="d3fe9-138">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="d3fe9-139">예외 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="d3fe9-139">Design Guidelines for Exceptions</span></span>](../../../docs/standard/design-guidelines/exceptions.md)
