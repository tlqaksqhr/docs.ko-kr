---
title: "네임스페이스의 이름"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- names [.NET Framework], conflicts
- names [.NET Framework], namespaces
- type names, conflicts
- namespaces [.NET Framework], names
- names [.NET Framework], type names
ms.assetid: a49058d2-0276-43a7-9502-04adddf857b2
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4fc0cb9183fde33887a3e84bb30cc3f79892586e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="names-of-namespaces"></a><span data-ttu-id="06491-102">네임스페이스의 이름</span><span class="sxs-lookup"><span data-stu-id="06491-102">Names of Namespaces</span></span>
<span data-ttu-id="06491-103">으로 다른 이름 지정 지침으로 목표 네임 스페이스의 이름을 지정할 때 만들어지고 충분 한 명확성 즉시 내용을 알 수 네임 스페이스의 내용을 가능성이 프레임 워크를 사용 하 여 프로그래머에 대 한 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06491-103">As with other naming guidelines, the goal when naming namespaces is creating sufficient clarity for the programmer using the framework to immediately know what the content of the namespace is likely to be.</span></span> <span data-ttu-id="06491-104">다음 템플릿 네임 스페이스 이름 지정에 대 한 일반적인 규칙을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="06491-104">The following template specifies the general rule for naming namespaces:</span></span>  
  
 `<Company>.(<Product>|<Technology>)[.<Feature>][.<Subnamespace>]`  
  
 <span data-ttu-id="06491-105">다음은 예입니다.</span><span class="sxs-lookup"><span data-stu-id="06491-105">The following are examples:</span></span>  
  
 `Fabrikam.Math`  
 `Litware.Security`  
  
 <span data-ttu-id="06491-106">**✓ 않습니다** 이름이 같은 다른 회사의 네임 스페이스를 방지 하기 위해 회사 이름이 있는 네임 스페이스 이름 접두사를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="06491-106">**✓ DO** prefix namespace names with a company name to prevent namespaces from different companies from having the same name.</span></span>  
  
 <span data-ttu-id="06491-107">**✓ 않습니다** 네임 스페이스 이름의 두 번째 수준에서 안정적이 고 버전에 관계 없이 제품 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="06491-107">**✓ DO** use a stable, version-independent product name at the second level of a namespace name.</span></span>  
  
 <span data-ttu-id="06491-108">**X 하지 않으면** 사용 하 여 조직 계층의 기준으로 네임 스페이스 계층의 이름에 대 한 기업의 그룹 이름은 일시적인 경우가 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="06491-108">**X DO NOT** use organizational hierarchies as the basis for names in namespace hierarchies, because group names within corporations tend to be short-lived.</span></span> <span data-ttu-id="06491-109">관련된 기술 그룹 주위 네임 스페이스의 계층 구조를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="06491-109">Organize the hierarchy of namespaces around groups of related technologies.</span></span>  
  
 <span data-ttu-id="06491-110">**✓ 않습니다** 기간이 PascalCasing, 및 별도 네임 스페이스 구성 요소를 사용 하 여 (예: `Microsoft.Office.PowerPoint`).</span><span class="sxs-lookup"><span data-stu-id="06491-110">**✓ DO** use PascalCasing, and separate namespace components with periods (e.g., `Microsoft.Office.PowerPoint`).</span></span> <span data-ttu-id="06491-111">브랜드에서 않던 대/소문자를 적용 하는 경우 규칙 대/소문자 일반적인 네임 스페이스에서에서 파생 하는 경우에 대/소문자 브랜드에 정의 된 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="06491-111">If your brand employs nontraditional casing, you should follow the casing defined by your brand, even if it deviates from normal namespace casing.</span></span>  
  
 <span data-ttu-id="06491-112">**✓ 고려** 적절 한 복수형 네임 스페이스 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="06491-112">**✓ CONSIDER** using plural namespace names where appropriate.</span></span>  
  
 <span data-ttu-id="06491-113">사용 예를 들어 `System.Collections` 대신 `System.Collection`합니다.</span><span class="sxs-lookup"><span data-stu-id="06491-113">For example, use `System.Collections` instead of `System.Collection`.</span></span> <span data-ttu-id="06491-114">하지만 브랜드 이름 및 머리글자어이 규칙에 대 한 예외는 됩니다.</span><span class="sxs-lookup"><span data-stu-id="06491-114">Brand names and acronyms are exceptions to this rule, however.</span></span> <span data-ttu-id="06491-115">사용 예를 들어 `System.IO` 대신 `System.IOs`합니다.</span><span class="sxs-lookup"><span data-stu-id="06491-115">For example, use `System.IO` instead of `System.IOs`.</span></span>  
  
 <span data-ttu-id="06491-116">**X 하지 않으면** 해당 네임 스페이스에서 네임 스페이스 및 형식에 대 한 동일한 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="06491-116">**X DO NOT** use the same name for a namespace and a type in that namespace.</span></span>  
  
 <span data-ttu-id="06491-117">예를 들어 사용 하지 마십시오 `Debug` 는 네임 스페이스와 이름을 지정 하 고 다음 라는 클래스도 제공 `Debug` 동일한 네임 스페이스에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06491-117">For example, do not use `Debug` as a namespace name and then also provide a class named `Debug` in the same namespace.</span></span> <span data-ttu-id="06491-118">여러 가지 컴파일러에서는 해당 형식을 정규화 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="06491-118">Several compilers require such types to be fully qualified.</span></span>  
  
### <a name="namespaces-and-type-name-conflicts"></a><span data-ttu-id="06491-119">네임 스페이스 및 형식 이름 충돌</span><span class="sxs-lookup"><span data-stu-id="06491-119">Namespaces and Type Name Conflicts</span></span>  
 <span data-ttu-id="06491-120">**X 하지 않으면** 와 같은 제네릭 형식 이름을 소개 `Element`, `Node`, `Log`, 및 `Message`합니다.</span><span class="sxs-lookup"><span data-stu-id="06491-120">**X DO NOT** introduce generic type names such as `Element`, `Node`, `Log`, and `Message`.</span></span>  
  
 <span data-ttu-id="06491-121">이름을 입력 이어질 수 있으므로 시나리오 공통 충돌 가능성이 높음 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06491-121">There is a very high probability that doing so will lead to type name conflicts in common scenarios.</span></span> <span data-ttu-id="06491-122">제네릭 형식 이름을 정규화 해야 (`FormElement`, `XmlNode`, `EventLog`, `SoapMessage`).</span><span class="sxs-lookup"><span data-stu-id="06491-122">You should qualify the generic type names (`FormElement`, `XmlNode`, `EventLog`, `SoapMessage`).</span></span>  
  
 <span data-ttu-id="06491-123">네임 스페이스의 다른 범주에 대 한 유형 이름 충돌 방지에 대 한 지침이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06491-123">There are specific guidelines for avoiding type name conflicts for different categories of namespaces.</span></span>  
  
-   <span data-ttu-id="06491-124">**응용 프로그램 모델 네임 스페이스**</span><span class="sxs-lookup"><span data-stu-id="06491-124">**Application model namespaces**</span></span>  
  
     <span data-ttu-id="06491-125">단일 응용 프로그램 모델에 속한 네임 스페이스는 종종 매우 함께 사용 하지만 거의 네임 스페이스의 다른 응용 프로그램 모델과 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="06491-125">Namespaces belonging to a single application model are very often used together, but they are almost never used with namespaces of other application models.</span></span> <span data-ttu-id="06491-126">예를 들어는 <xref:System.Windows.Forms?displayProperty=nameWithType> 네임 스페이스와 함께 사용 되는 아주 드물게는 <xref:System.Web.UI?displayProperty=nameWithType> 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="06491-126">For example, the <xref:System.Windows.Forms?displayProperty=nameWithType> namespace is very rarely used together with the <xref:System.Web.UI?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="06491-127">다음은 잘 알려진 응용 프로그램 모델 네임 스페이스 그룹의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="06491-127">The following is a list of well-known application model namespace groups:</span></span>  
  
     `System.Windows*`   
     `System.Web.UI*`  
  
     <span data-ttu-id="06491-128">**X 하지 않으면** 단일 응용 프로그램 모델 내에서는 네임 스페이스의 형식에 같은 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="06491-128">**X DO NOT** give the same name to types in namespaces within a single application model.</span></span>  
  
     <span data-ttu-id="06491-129">예를 들어 이라는 형식을 추가 하지 마십시오 `Page` 에 <xref:System.Web.UI.Adapters?displayProperty=nameWithType> 네임 스페이스, 때문에 <xref:System.Web.UI?displayProperty=nameWithType> 이라는 형식을 네임 스페이스에 이미 포함 되어 `Page`합니다.</span><span class="sxs-lookup"><span data-stu-id="06491-129">For example, do not add a type named `Page` to the <xref:System.Web.UI.Adapters?displayProperty=nameWithType> namespace, because the <xref:System.Web.UI?displayProperty=nameWithType> namespace already contains a type named `Page`.</span></span>  
  
-   <span data-ttu-id="06491-130">**인프라 네임 스페이스**</span><span class="sxs-lookup"><span data-stu-id="06491-130">**Infrastructure namespaces**</span></span>  
  
     <span data-ttu-id="06491-131">이 그룹 거의 일반 응용 프로그램을 개발 하는 동안 가져온 네임 스페이스를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="06491-131">This group contains namespaces that are rarely imported during development of common applications.</span></span> <span data-ttu-id="06491-132">예를 들어 `.Design` 네임 스페이스는 프로그래밍 개발 도구 때 주로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="06491-132">For example, `.Design` namespaces are mainly used when developing programming tools.</span></span> <span data-ttu-id="06491-133">이러한 네임 스페이스의 유형과 충돌을 방지 중요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="06491-133">Avoiding conflicts with types in these namespaces is not critical.</span></span>  
  
-   <span data-ttu-id="06491-134">**핵심 네임 스페이스**</span><span class="sxs-lookup"><span data-stu-id="06491-134">**Core namespaces**</span></span>  
  
     <span data-ttu-id="06491-135">모든 핵심 네임 스페이스 포함 `System` 네임 스페이스를 응용 프로그램 모델 및 인프라 네임 스페이스를 제외 합니다.</span><span class="sxs-lookup"><span data-stu-id="06491-135">Core namespaces include all `System` namespaces, excluding namespaces of the application models and the Infrastructure namespaces.</span></span> <span data-ttu-id="06491-136">맺음 코어 네임 스페이스에 포함 `System`, `System.IO`, `System.Xml`, 및 `System.Net`합니다.</span><span class="sxs-lookup"><span data-stu-id="06491-136">Core namespaces include, among others, `System`, `System.IO`, `System.Xml`, and `System.Net`.</span></span>  
  
     <span data-ttu-id="06491-137">**X 하지 않으면** 제공 핵심 네임 스페이스에서 종류와 충돌 하는 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="06491-137">**X DO NOT** give types names that would conflict with any type in the Core namespaces.</span></span>  
  
     <span data-ttu-id="06491-138">예를 들어 사용 하지 마십시오 `Stream` 형식 이름으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="06491-138">For example, never use `Stream` as a type name.</span></span> <span data-ttu-id="06491-139">과 충돌 <xref:System.IO.Stream?displayProperty=nameWithType>, 매우 일반적으로 형식을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="06491-139">It would conflict with <xref:System.IO.Stream?displayProperty=nameWithType>, a very commonly used type.</span></span>  
  
-   <span data-ttu-id="06491-140">**기술 네임 스페이스 그룹**</span><span class="sxs-lookup"><span data-stu-id="06491-140">**Technology namespace groups**</span></span>  
  
     <span data-ttu-id="06491-141">모든 네임 스페이스의 동일한 처음 두 개의 네임 스페이스 노드를 포함 하는이 범주 `(<Company>.<Technology>*`), 같은 `Microsoft.Build.Utilities` 및 `Microsoft.Build.Tasks`합니다.</span><span class="sxs-lookup"><span data-stu-id="06491-141">This category includes all namespaces with the same first two namespace nodes `(<Company>.<Technology>*`), such as `Microsoft.Build.Utilities` and `Microsoft.Build.Tasks`.</span></span> <span data-ttu-id="06491-142">한 가지 기술에 속하는 형식 서로 충돌 하지 않는 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="06491-142">It is important that types belonging to a single technology do not conflict with each other.</span></span>  
  
     <span data-ttu-id="06491-143">**X 하지 않으면** 단일 기술에서 다른 종류와 충돌 하는 형식 이름을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="06491-143">**X DO NOT** assign type names that would conflict with other types within a single technology.</span></span>  
  
     <span data-ttu-id="06491-144">**X 하지 않으면** (없는 경우 기술 응용 프로그램 모델에 사용할 수 없습니다) 기술 네임 스페이스의 형식 및 응용 프로그램 모델 네임 스페이스는 간의 유형 이름 충돌을 소개 합니다.</span><span class="sxs-lookup"><span data-stu-id="06491-144">**X DO NOT** introduce type name conflicts between types in technology namespaces and an application model namespace (unless the technology is not intended to be used with the application model).</span></span>  
  
 <span data-ttu-id="06491-145">*일부 © 2005, 2009 Microsoft Corporation. 모든 권리 보유.*</span><span class="sxs-lookup"><span data-stu-id="06491-145">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="06491-146">*피어슨 교육, Inc.에서의 사용 권한으로 재인쇄 [Framework 디자인 지침: 규칙, 특징 및 다시 사용할 수 있는.NET 라이브러리를 2nd Edition에 대 한 패턴](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina 및 Brad Abrams 게시 하 여 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로: Addison Wesley Professional.*</span><span class="sxs-lookup"><span data-stu-id="06491-146">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06491-147">참고 항목</span><span class="sxs-lookup"><span data-stu-id="06491-147">See Also</span></span>  
 [<span data-ttu-id="06491-148">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="06491-148">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="06491-149">명명 지침</span><span class="sxs-lookup"><span data-stu-id="06491-149">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
