---
title: 예외 및 성능
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tester-doer pattern
- TryParse pattern
- exceptions, throwing
- exceptions, performance
- throwing exceptions, performance
ms.assetid: 3ad6aad9-08e6-4232-b336-0e301f2493e6
caps.latest.revision: 12
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 7972cf7d63ee22e791d46046f30c9be467cc758e
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2018
---
# <a name="exceptions-and-performance"></a><span data-ttu-id="a883c-102">예외 및 성능</span><span class="sxs-lookup"><span data-stu-id="a883c-102">Exceptions and Performance</span></span>
<span data-ttu-id="a883c-103">예외와 관련 된 일반적인 문제 하나는 지속적으로 실패 하는 코드에 대 한 예외를 사용 하면 성능을 구현 됩니다 허용입니다.</span><span class="sxs-lookup"><span data-stu-id="a883c-103">One common concern related to exceptions is that if exceptions are used for code that routinely fails, the performance of the implementation will be unacceptable.</span></span> <span data-ttu-id="a883c-104">이 유효한 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="a883c-104">This is a valid concern.</span></span> <span data-ttu-id="a883c-105">예외를 throw 하는 멤버 성능이 현저히 저하 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a883c-105">When a member throws an exception, its performance can be orders of magnitude slower.</span></span> <span data-ttu-id="a883c-106">그러나, 오류 코드를 사용 하지 않도록 설정 하는 예외 지침을 따르면 엄격 하 게 하는 동안 좋은 성능을 얻을 수는 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a883c-106">However, it is possible to achieve good performance while strictly adhering to the exception guidelines that disallow using error codes.</span></span> <span data-ttu-id="a883c-107">이 섹션에 설명 된 두 개의 패턴에는이 작업을 수행 하는 방법을 제안 합니다.</span><span class="sxs-lookup"><span data-stu-id="a883c-107">Two patterns described in this section suggest ways to do this.</span></span>  
  
 <span data-ttu-id="a883c-108">**X 하지 않으면** 있는지 예외 영향을 줄 수 성능 저하 문제 때문에 오류 코드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a883c-108">**X DO NOT** use error codes because of concerns that exceptions might affect performance negatively.</span></span>  
  
 <span data-ttu-id="a883c-109">성능을 향상 시키기 위해 Tester-doer 패턴 나 다음 두 섹션에서 설명 하는 Try 구문 분석 패턴을 사용 하는 것이 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a883c-109">To improve performance, it is possible to use either the Tester-Doer Pattern or the Try-Parse Pattern, described in the next two sections.</span></span>  
  
## <a name="tester-doer-pattern"></a><span data-ttu-id="a883c-110">Tester-doer 패턴</span><span class="sxs-lookup"><span data-stu-id="a883c-110">Tester-Doer Pattern</span></span>  
 <span data-ttu-id="a883c-111">경우에 따라 성능 예외 throw 멤버의 멤버 두 개로 나누어 향상 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a883c-111">Sometimes performance of an exception-throwing member can be improved by breaking the member into two.</span></span> <span data-ttu-id="a883c-112">에 <xref:System.Collections.Generic.ICollection%601.Add%2A> 의 메서드는 <xref:System.Collections.Generic.ICollection%601> 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="a883c-112">Let’s look at the <xref:System.Collections.Generic.ICollection%601.Add%2A> method of the <xref:System.Collections.Generic.ICollection%601> interface.</span></span>  
  
```  
ICollection<int> numbers = ...   
numbers.Add(1);  
```  
  
 <span data-ttu-id="a883c-113">메서드가 `Add` 컬렉션이 읽기 전용인 경우 throw 합니다.</span><span class="sxs-lookup"><span data-stu-id="a883c-113">The method `Add` throws if the collection is read-only.</span></span> <span data-ttu-id="a883c-114">이 자주 실패 하 고 메서드 호출 필요한 시나리오에서 성능 문제를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a883c-114">This can be a performance problem in scenarios where the method call is expected to fail often.</span></span> <span data-ttu-id="a883c-115">문제를 완화 하는 방법 중 하나는 컬렉션 값을 추가 하기 전에 쓰기 가능 인지를 테스트 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a883c-115">One of the ways to mitigate the problem is to test whether the collection is writable before trying to add a value.</span></span>  
  
```  
ICollection<int> numbers = ...   
...  
if(!numbers.IsReadOnly){  
    numbers.Add(1);  
}  
```  
  
 <span data-ttu-id="a883c-116">속성은 예에서 사용 하는 조건을 테스트 하는 데 사용 하는 멤버 `IsReadOnly`은 테스터 라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="a883c-116">The member used to test a condition, which in our example is the property `IsReadOnly`, is referred to as the tester.</span></span> <span data-ttu-id="a883c-117">잠재적으로 발생 작업을 수행 하는 데 사용 되는 멤버는 `Add` 예에서 메서드 doer 부분으로 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a883c-117">The member used to perform a potentially throwing operation, the `Add` method in our example, is referred to as the doer.</span></span>  
  
 <span data-ttu-id="a883c-118">**✓ 고려** Tester-doer 패턴 예외를 throw 할 수 있는 멤버에 대 한 공통 성능 문제를 방지 하는 시나리오와 관련 된 예외입니다.</span><span class="sxs-lookup"><span data-stu-id="a883c-118">**✓ CONSIDER** the Tester-Doer Pattern for members that might throw exceptions in common scenarios to avoid performance problems related to exceptions.</span></span>  
  
## <a name="try-parse-pattern"></a><span data-ttu-id="a883c-119">시도 구문 분석 패턴</span><span class="sxs-lookup"><span data-stu-id="a883c-119">Try-Parse Pattern</span></span>  
 <span data-ttu-id="a883c-120">성능이 매우 중요 한 Api에 대 한 이전 섹션에서 설명한 Tester-doer 패턴 보다 훨씬 빠른는 패턴을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a883c-120">For extremely performance-sensitive APIs, an even faster pattern than the Tester-Doer Pattern described in the previous section should be used.</span></span> <span data-ttu-id="a883c-121">멤버 이름에 멤버 의미 체계의 일부 경우 잘 정의 된 테스트를 조정 하기 위한 패턴을 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="a883c-121">The pattern calls for adjusting the member name to make a well-defined test case a part of the member semantics.</span></span> <span data-ttu-id="a883c-122">예를 들어 <xref:System.DateTime> 정의 <xref:System.DateTime.Parse%2A> 메서드는 실패 하는 문자열을 구문 분석 하는 경우 예외를 throw 합니다.</span><span class="sxs-lookup"><span data-stu-id="a883c-122">For example, <xref:System.DateTime> defines a <xref:System.DateTime.Parse%2A> method that throws an exception if parsing of a string fails.</span></span> <span data-ttu-id="a883c-123">또한 해당 정의 <xref:System.DateTime.TryParse%2A> , 구문 분석을 시도 하는 하지만 메서드 구문 분석 실패 하 고 사용 하 여 성공적으로 구문 분석의 결과 반환 하는 경우는 `out` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="a883c-123">It also defines a corresponding <xref:System.DateTime.TryParse%2A> method that attempts to parse, but returns false if parsing is unsuccessful and returns the result of a successful parsing using an `out` parameter.</span></span>  
  
```  
public struct DateTime {  
    public static DateTime Parse(string dateTime){   
        ...   
    }  
    public static bool TryParse(string dateTime, out DateTime result){  
        ...  
    }  
}  
```  
  
 <span data-ttu-id="a883c-124">이 패턴을 사용할 경우에 엄격한 측면에서 시도 기능을 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a883c-124">When using this pattern, it is important to define the try functionality in strict terms.</span></span> <span data-ttu-id="a883c-125">멤버 잘 정의 된 try 이외의 어떤 이유로 든 실패할 경우 멤버에 해당 하는 예외가 throw 여전히 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a883c-125">If the member fails for any reason other than the well-defined try, the member must still throw a corresponding exception.</span></span>  
  
 <span data-ttu-id="a883c-126">**✓ 고려** Try 구문 분석 패턴 예외를 throw 할 수 있는 멤버에 대 한 공통 성능 문제를 방지 하는 시나리오와 관련 된 예외입니다.</span><span class="sxs-lookup"><span data-stu-id="a883c-126">**✓ CONSIDER** the Try-Parse Pattern for members that might throw exceptions in common scenarios to avoid performance problems related to exceptions.</span></span>  
  
 <span data-ttu-id="a883c-127">**✓ 않습니다** 이 패턴을 구현 하는 방법에 대 한 접두사 "Try" 및 Boolean 반환 형식을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a883c-127">**✓ DO** use the prefix "Try" and Boolean return type for methods implementing this pattern.</span></span>  
  
 <span data-ttu-id="a883c-128">**✓ 않습니다** Try 구문 분석 패턴을 사용 하 여 각 멤버에 대 한 예외 throw 멤버를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a883c-128">**✓ DO** provide an exception-throwing member for each member using the Try-Parse Pattern.</span></span>  
  
 <span data-ttu-id="a883c-129">*Portions © 2005, 2009 Microsoft Corporation. 모든 권리 보유.*</span><span class="sxs-lookup"><span data-stu-id="a883c-129">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="a883c-130">*피어슨 교육, Inc.에서의 사용 권한으로 재인쇄 [Framework 디자인 지침: 규칙, 특징 및 다시 사용할 수 있는.NET 라이브러리를 2nd Edition에 대 한 패턴](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina 및 Brad Abrams 게시 하 여 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로: Addison Wesley Professional.*</span><span class="sxs-lookup"><span data-stu-id="a883c-130">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a883c-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a883c-131">See Also</span></span>  
 [<span data-ttu-id="a883c-132">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="a883c-132">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="a883c-133">예외 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="a883c-133">Design Guidelines for Exceptions</span></span>](../../../docs/standard/design-guidelines/exceptions.md)
