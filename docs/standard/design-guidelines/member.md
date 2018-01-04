---
title: "멤버 디자인 지침"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- member design guidelines [.NET Framework], about member design guidelines
- members [.NET Framework], design guidelines
- class library design guidelines [.NET Framework], members
- member design guidelines [.NET Framework]
ms.assetid: 0ce93180-1d7b-4f8c-9306-f828b2d66b8f
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: ae69b77098c7f2e1de83eedd40cf0f0da9473326
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/23/2017
---
# <a name="member-design-guidelines"></a><span data-ttu-id="91114-102">멤버 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="91114-102">Member Design Guidelines</span></span>
<span data-ttu-id="91114-103">메서드, 속성, 이벤트, 생성자 및 필드 통칭 하 여 멤버 라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="91114-103">Methods, properties, events, constructors, and fields are collectively referred to as members.</span></span> <span data-ttu-id="91114-104">멤버는 궁극적으로 기준인 프레임 워크 기능 프레임 워크의 최종 사용자에 게 노출 되는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="91114-104">Members are ultimately the means by which framework functionality is exposed to the end users of a framework.</span></span>  
  
 <span data-ttu-id="91114-105">멤버 가상 또는 비가상, 구체적인 또는 abstract, 정적 또는 인스턴스를 수 있으며 내게 필요한 옵션의 다양 한 범위를 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91114-105">Members can be virtual or nonvirtual, concrete or abstract, static or instance, and can have several different scopes of accessibility.</span></span> <span data-ttu-id="91114-106">이 모든 다양이 한 놀라운 표현을 제공 하지만 동시에 프레임 워크 디자이너 안되며 때는 주의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="91114-106">All this variety provides incredible expressiveness but at the same time requires care on the part of the framework designer.</span></span>  
  
 <span data-ttu-id="91114-107">이 장에서 모든 형식의 멤버를 디자인할 때 따라야 할 기본 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="91114-107">This chapter offers basic guidelines that should be followed when designing members of any type.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="91114-108">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="91114-108">In This Section</span></span>  
 [<span data-ttu-id="91114-109">멤버 오버로드</span><span class="sxs-lookup"><span data-stu-id="91114-109">Member Overloading</span></span>](../../../docs/standard/design-guidelines/member-overloading.md)  
 [<span data-ttu-id="91114-110">속성 디자인</span><span class="sxs-lookup"><span data-stu-id="91114-110">Property Design</span></span>](../../../docs/standard/design-guidelines/property.md)  
 [<span data-ttu-id="91114-111">생성자 디자인</span><span class="sxs-lookup"><span data-stu-id="91114-111">Constructor Design</span></span>](../../../docs/standard/design-guidelines/constructor.md)  
 [<span data-ttu-id="91114-112">이벤트 디자인</span><span class="sxs-lookup"><span data-stu-id="91114-112">Event Design</span></span>](../../../docs/standard/design-guidelines/event.md)  
 [<span data-ttu-id="91114-113">필드 디자인</span><span class="sxs-lookup"><span data-stu-id="91114-113">Field Design</span></span>](../../../docs/standard/design-guidelines/field.md)  
 [<span data-ttu-id="91114-114">확장명 메서드</span><span class="sxs-lookup"><span data-stu-id="91114-114">Extension Methods</span></span>](../../../docs/standard/design-guidelines/extension-methods.md)  
 [<span data-ttu-id="91114-115">연산자 오버로드</span><span class="sxs-lookup"><span data-stu-id="91114-115">Operator Overloads</span></span>](../../../docs/standard/design-guidelines/operator-overloads.md)  
 [<span data-ttu-id="91114-116">매개 변수 디자인</span><span class="sxs-lookup"><span data-stu-id="91114-116">Parameter Design</span></span>](../../../docs/standard/design-guidelines/parameter-design.md)  
 <span data-ttu-id="91114-117">*일부 © 2005, 2009 Microsoft Corporation. 모든 권리 보유.*</span><span class="sxs-lookup"><span data-stu-id="91114-117">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="91114-118">*피어슨 교육, Inc.에서의 사용 권한으로 재인쇄 [Framework 디자인 지침: 규칙, 특징 및 다시 사용할 수 있는.NET 라이브러리를 2nd Edition에 대 한 패턴](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina 및 Brad Abrams 게시 하 여 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로: Addison Wesley Professional.*</span><span class="sxs-lookup"><span data-stu-id="91114-118">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91114-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="91114-119">See Also</span></span>  
 [<span data-ttu-id="91114-120">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="91114-120">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
