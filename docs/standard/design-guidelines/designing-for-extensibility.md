---
title: 확장성을 위한 디자인
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- extending class libraries
- extensibility with class libraries in .NET Framework
- class library design guidelines [.NET Framework], extensibility
- class library extensibility [.NET Framework]
ms.assetid: 1cdb8740-871a-456c-9bd9-db96ca8d79b3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 68419fe293dd25936aa3c1e3def10bbe8852e175
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33571386"
---
# <a name="designing-for-extensibility"></a><span data-ttu-id="c6c5a-102">확장성을 위한 디자인</span><span class="sxs-lookup"><span data-stu-id="c6c5a-102">Designing for Extensibility</span></span>
<span data-ttu-id="c6c5a-103">프레임 워크를 디자인할 때의 중요 한 측면 있는지 확인 하는 프레임 워크의 확장성을 신중 하 게 고려 했습니다.</span><span class="sxs-lookup"><span data-stu-id="c6c5a-103">One important aspect of designing a framework is making sure the extensibility of the framework has been carefully considered.</span></span> <span data-ttu-id="c6c5a-104">이렇게 하려면 다양 한 확장성 메커니즘와 관련 된 이점과 비용을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6c5a-104">This requires that you understand the costs and benefits associated with various extensibility mechanisms.</span></span> <span data-ttu-id="c6c5a-105">이 장에서 확장성 메커니즘 중 어떤 것인지-서브클래싱, 이벤트, 가상 멤버, 콜백 및 등-프레임 워크의 요구 사항을 충족할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6c5a-105">This chapter helps you decide which of the extensibility mechanisms—subclassing, events, virtual members, callbacks, and so on—can best meet the requirements of your framework.</span></span>  
  
 <span data-ttu-id="c6c5a-106">프레임 워크의 확장성을 허용 하는 방법은 여러 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6c5a-106">There are many ways to allow extensibility in frameworks.</span></span> <span data-ttu-id="c6c5a-107">까지의 덜 강력 하지만 보다 저렴 한 비용 저렴 하지만 매우 강력 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6c5a-107">They range from less powerful but less costly to very powerful but expensive.</span></span> <span data-ttu-id="c6c5a-108">모든 지정된 확장성 요구 사항에 대 한 요구 사항을 충족 하는 가장 비용이 많이 드는 확장성 메커니즘을 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6c5a-108">For any given extensibility requirement, you should choose the least costly extensibility mechanism that meets the requirements.</span></span> <span data-ttu-id="c6c5a-109">일반적으로 보다 높은 확장성은 나중에 추가할 수는 있지만 사용할 수 있으며 되지 자리를 비울 주요 변경 없이 염두에서에 둬야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6c5a-109">Keep in mind that it’s usually possible to add more extensibility later, but you can never take it away without introducing breaking changes.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c6c5a-110">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="c6c5a-110">In This Section</span></span>  
 [<span data-ttu-id="c6c5a-111">봉인되지 않은 클래스</span><span class="sxs-lookup"><span data-stu-id="c6c5a-111">Unsealed Classes</span></span>](../../../docs/standard/design-guidelines/unsealed-classes.md)  
 [<span data-ttu-id="c6c5a-112">보호된 멤버</span><span class="sxs-lookup"><span data-stu-id="c6c5a-112">Protected Members</span></span>](../../../docs/standard/design-guidelines/protected-members.md)  
 [<span data-ttu-id="c6c5a-113">이벤트 및 콜백</span><span class="sxs-lookup"><span data-stu-id="c6c5a-113">Events and Callbacks</span></span>](../../../docs/standard/design-guidelines/events-and-callbacks.md)  
 [<span data-ttu-id="c6c5a-114">가상 멤버</span><span class="sxs-lookup"><span data-stu-id="c6c5a-114">Virtual Members</span></span>](../../../docs/standard/design-guidelines/virtual-members.md)  
 [<span data-ttu-id="c6c5a-115">추상화(추상 형식 및 인터페이스)</span><span class="sxs-lookup"><span data-stu-id="c6c5a-115">Abstractions (Abstract Types and Interfaces)</span></span>](../../../docs/standard/design-guidelines/abstractions-abstract-types-and-interfaces.md)  
 [<span data-ttu-id="c6c5a-116">추상화 구현을 위한 기본 클래스</span><span class="sxs-lookup"><span data-stu-id="c6c5a-116">Base Classes for Implementing Abstractions</span></span>](../../../docs/standard/design-guidelines/base-classes-for-implementing-abstractions.md)  
 [<span data-ttu-id="c6c5a-117">봉인</span><span class="sxs-lookup"><span data-stu-id="c6c5a-117">Sealing</span></span>](../../../docs/standard/design-guidelines/sealing.md)  
 <span data-ttu-id="c6c5a-118">*Portions © 2005, 2009 Microsoft Corporation. 모든 권리 보유.*</span><span class="sxs-lookup"><span data-stu-id="c6c5a-118">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="c6c5a-119">*피어슨 교육, Inc.에서의 사용 권한으로 재인쇄 [Framework 디자인 지침: 규칙, 특징 및 다시 사용할 수 있는.NET 라이브러리를 2nd Edition에 대 한 패턴](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina 및 Brad Abrams 게시 하 여 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로: Addison Wesley Professional.*</span><span class="sxs-lookup"><span data-stu-id="c6c5a-119">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6c5a-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c6c5a-120">See Also</span></span>  
 [<span data-ttu-id="c6c5a-121">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="c6c5a-121">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
