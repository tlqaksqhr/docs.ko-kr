---
title: "같음 연산자"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- class library design guidelines [.NET Framework], Equals method
- class library design guidelines [.NET Framework], equality operator
- equality operator (==) [.NET Framework]
- Equals method
- == operator (equality) [.NET Framework]
ms.assetid: bc496a91-fefb-4ce0-ab4c-61f09964119a
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 5aa37d2ee6b3b18d9decbc98bd1c427168e8ab35
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/23/2017
---
# <a name="equality-operators"></a><span data-ttu-id="8c945-102">같음 연산자</span><span class="sxs-lookup"><span data-stu-id="8c945-102">Equality Operators</span></span>
<span data-ttu-id="8c945-103">이 섹션 같음 연산자를 오버 로드에 대해 설명 하 고 가리키는 `operator==` 및 `operator!=` 같음 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="8c945-103">This section discusses overloading equality operators and refers to `operator==` and `operator!=` as equality operators.</span></span>  
  
 <span data-ttu-id="8c945-104">**X 하지 않으면** 같음 연산자 있고 다른 선언 중 하나를 오버 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c945-104">**X DO NOT** overload one of the equality operators and not the other.</span></span>  
  
 <span data-ttu-id="8c945-105">**✓ 않습니다** 되도록 <xref:System.Object.Equals%2A?displayProperty=nameWithType> 및 같음 연산자는 정확히 동일한 의미 체계와 비슷한 성능 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="8c945-105">**✓ DO** ensure that <xref:System.Object.Equals%2A?displayProperty=nameWithType> and the equality operators have exactly the same semantics and similar performance characteristics.</span></span>  
  
 <span data-ttu-id="8c945-106">종종 즉 `Object.Equals` 같음 연산자를 오버 로드 될 때 재정의할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c945-106">This often means that `Object.Equals` needs to be overridden when the equality operators are overloaded.</span></span>  
  
 <span data-ttu-id="8c945-107">**하지 말고 X** 같음 연산자에서 예외를 throw 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c945-107">**X AVOID** throwing exceptions from equality operators.</span></span>  
  
 <span data-ttu-id="8c945-108">예를 들어 인수 중 하나가 throw 하는 대신 null 인 경우 false를 반환 `NullReferenceException`합니다.</span><span class="sxs-lookup"><span data-stu-id="8c945-108">For example, return false if one of the arguments is null instead of throwing `NullReferenceException`.</span></span>  
  
## <a name="equality-operators-on-value-types"></a><span data-ttu-id="8c945-109">값 형식에 같음 연산자</span><span class="sxs-lookup"><span data-stu-id="8c945-109">Equality Operators on Value Types</span></span>  
 <span data-ttu-id="8c945-110">**✓ 않습니다** 같음이 의미가 있을 경우에 값 형식에 같음 연산자를 오버 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c945-110">**✓ DO** overload the equality operators on value types, if equality is meaningful.</span></span>  
  
 <span data-ttu-id="8c945-111">대부분의 프로그래밍 언어에는 기본 구현 된 `operator==` 값 형식에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c945-111">In most programming languages, there is no default implementation of `operator==` for value types.</span></span>  
  
## <a name="equality-operators-on-reference-types"></a><span data-ttu-id="8c945-112">참조 형식에 같음 연산자</span><span class="sxs-lookup"><span data-stu-id="8c945-112">Equality Operators on Reference Types</span></span>  
 <span data-ttu-id="8c945-113">**하지 말고 X** 변경 가능한 참조 형식에 같음 연산자를 오버 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c945-113">**X AVOID** overloading equality operators on mutable reference types.</span></span>  
  
 <span data-ttu-id="8c945-114">여러 언어 참조 형식에 대 한 기본 제공 같음 연산자가 있는 경우.</span><span class="sxs-lookup"><span data-stu-id="8c945-114">Many languages have built-in equality operators for reference types.</span></span> <span data-ttu-id="8c945-115">기본 제공 연산자에는 일반적으로 참조 일치 구현 및 기본 동작 값을 다르게 변경 되 면 대부분의 개발자는 놀라운 사실 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c945-115">The built-in operators usually implement the reference equality, and many developers are surprised when the default behavior is changed to the value equality.</span></span>  
  
 <span data-ttu-id="8c945-116">이 문제는 불변성을 사용 하면 참조 일치와 값이 같은지 간의 차이 쉽게 변경할 수 없는 참조 형식에 대 한 완화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c945-116">This problem is mitigated for immutable reference types because immutability makes it much harder to notice the difference between reference equality and value equality.</span></span>  
  
 <span data-ttu-id="8c945-117">**하지 말고 X** 참조 일치 하는 것 보다 크게 느려지지 구현 되는 경우에 참조 형식에 같음 연산자를 오버 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c945-117">**X AVOID** overloading equality operators on reference types if the implementation would be significantly slower than that of reference equality.</span></span>  
  
 <span data-ttu-id="8c945-118">*일부 © 2005, 2009 Microsoft Corporation. 모든 권리 보유.*</span><span class="sxs-lookup"><span data-stu-id="8c945-118">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="8c945-119">*피어슨 교육, Inc.에서의 사용 권한으로 재인쇄 [Framework 디자인 지침: 규칙, 특징 및 다시 사용할 수 있는.NET 라이브러리를 2nd Edition에 대 한 패턴](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina 및 Brad Abrams 게시 하 여 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로: Addison Wesley Professional.*</span><span class="sxs-lookup"><span data-stu-id="8c945-119">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c945-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8c945-120">See Also</span></span>  
 [<span data-ttu-id="8c945-121">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="8c945-121">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="8c945-122">사용 지침</span><span class="sxs-lookup"><span data-stu-id="8c945-122">Usage Guidelines</span></span>](../../../docs/standard/design-guidelines/usage-guidelines.md)
