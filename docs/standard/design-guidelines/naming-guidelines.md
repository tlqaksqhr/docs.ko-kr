---
title: 명명 지침
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- names [.NET Framework], about naming guidelines
- naming guidelines [.NET Framework]
- class library design guidelines [.NET Framework], names
- formatting [.NET Framework], names
- identifiers, class library element names
- names [.NET Framework]
- format naming guidelines [.NET Framework]
ms.assetid: fc076d66-9b5f-42d3-aa65-61d970c794a3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 53ffb641d3e507a937c304725b3c8590d046338e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33572972"
---
# <a name="naming-guidelines"></a><span data-ttu-id="1f52e-102">명명 지침</span><span class="sxs-lookup"><span data-stu-id="1f52e-102">Naming Guidelines</span></span>
<span data-ttu-id="1f52e-103">일관성 있는 개발 프레임 워크의 명명 규칙의 집합을 따라 프레임 워크의 유용성에 대 한 주요 기여도 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f52e-103">Following a consistent set of naming conventions in the development of a framework can be a major contribution to the framework’s usability.</span></span> <span data-ttu-id="1f52e-104">프레임 워크를에 광범위 하 게 분리 된 프로젝트에서 많은 개발자가 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f52e-104">It allows the framework to be used by many developers on widely separated projects.</span></span> <span data-ttu-id="1f52e-105">폼의 일관성을 벗어나는 프레임 워크 요소의 이름을 쉽게 이해할 수 및 각 요소의 기능을 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f52e-105">Beyond consistency of form, names of framework elements must be easily understood and must convey the function of each element.</span></span>  
  
 <span data-ttu-id="1f52e-106">이 장의 목표 개발자에 게 즉시 의미 있는 이름에 만들어지는 일관성 있는 집합의 명명 규칙을 제공 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1f52e-106">The goal of this chapter is to provide a consistent set of naming conventions that results in names that make immediate sense to developers.</span></span>  
  
 <span data-ttu-id="1f52e-107">공개적으로 노출 되는 Api에 적용 하도록만 해야 하지만이 명명 규칙을 채택 하 고 코드 전체에서 보다 일관성 있는 명명 인해 일반 코드 개발 지침으로, (public 또는 protected 형식 및 멤버에 및 명시적으로 구현 된 인터페이스).</span><span class="sxs-lookup"><span data-stu-id="1f52e-107">Although adopting these naming conventions as general code development guidelines would result in more consistent naming throughout your code, you are required only to apply them to APIs that are publicly exposed (public or protected types and members, and explicitly implemented interfaces).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1f52e-108">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="1f52e-108">In This Section</span></span>  
 [<span data-ttu-id="1f52e-109">대/소문자 표기법</span><span class="sxs-lookup"><span data-stu-id="1f52e-109">Capitalization Conventions</span></span>](../../../docs/standard/design-guidelines/capitalization-conventions.md)  
 [<span data-ttu-id="1f52e-110">일반 명명 규칙</span><span class="sxs-lookup"><span data-stu-id="1f52e-110">General Naming Conventions</span></span>](../../../docs/standard/design-guidelines/general-naming-conventions.md)  
 [<span data-ttu-id="1f52e-111">어셈블리 및 DLL의 이름</span><span class="sxs-lookup"><span data-stu-id="1f52e-111">Names of Assemblies and DLLs</span></span>](../../../docs/standard/design-guidelines/names-of-assemblies-and-dlls.md)  
 [<span data-ttu-id="1f52e-112">네임스페이스의 이름</span><span class="sxs-lookup"><span data-stu-id="1f52e-112">Names of Namespaces</span></span>](../../../docs/standard/design-guidelines/names-of-namespaces.md)  
 [<span data-ttu-id="1f52e-113">클래스, 구조체 및 인터페이스의 이름</span><span class="sxs-lookup"><span data-stu-id="1f52e-113">Names of Classes, Structs, and Interfaces</span></span>](../../../docs/standard/design-guidelines/names-of-classes-structs-and-interfaces.md)  
 [<span data-ttu-id="1f52e-114">형식 멤버의 이름</span><span class="sxs-lookup"><span data-stu-id="1f52e-114">Names of Type Members</span></span>](../../../docs/standard/design-guidelines/names-of-type-members.md)  
 [<span data-ttu-id="1f52e-115">매개 변수 이름 지정</span><span class="sxs-lookup"><span data-stu-id="1f52e-115">Naming Parameters</span></span>](../../../docs/standard/design-guidelines/naming-parameters.md)  
 [<span data-ttu-id="1f52e-116">리소스 이름 지정</span><span class="sxs-lookup"><span data-stu-id="1f52e-116">Naming Resources</span></span>](../../../docs/standard/design-guidelines/naming-resources.md)  
 <span data-ttu-id="1f52e-117">*Portions © 2005, 2009 Microsoft Corporation. 모든 권리 보유.*</span><span class="sxs-lookup"><span data-stu-id="1f52e-117">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="1f52e-118">*피어슨 교육, Inc.에서의 사용 권한으로 재인쇄 [Framework 디자인 지침: 규칙, 특징 및 다시 사용할 수 있는.NET 라이브러리를 2nd Edition에 대 한 패턴](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina 및 Brad Abrams 게시 하 여 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로: Addison Wesley Professional.*</span><span class="sxs-lookup"><span data-stu-id="1f52e-118">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f52e-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1f52e-119">See Also</span></span>  
 [<span data-ttu-id="1f52e-120">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="1f52e-120">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
