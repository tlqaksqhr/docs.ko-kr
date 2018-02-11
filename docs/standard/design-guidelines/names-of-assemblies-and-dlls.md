---
title: "어셈블리 및 DLL의 이름"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- names [.NET Framework], DLLs
- names [.NET Framework], assemblies
- assemblies [.NET Framework], names
- DLLs, names
ms.assetid: e800b610-31b4-4949-9c14-cb60e9f254be
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: f74c37821d730ec8dcaa74763967c662bafd6699
ms.sourcegitcommit: be1fb5d9447ad459bef22b91a91c72e3e0b2d916
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2018
---
# <a name="names-of-assemblies-and-dlls"></a><span data-ttu-id="45ac4-102">어셈블리 및 DLL의 이름</span><span class="sxs-lookup"><span data-stu-id="45ac4-102">Names of Assemblies and DLLs</span></span>
<span data-ttu-id="45ac4-103">어셈블리는 배포 및 관리 코드 프로그램에 대 한 id의 단위입니다.</span><span class="sxs-lookup"><span data-stu-id="45ac4-103">An assembly is the unit of deployment and identity for managed code programs.</span></span> <span data-ttu-id="45ac4-104">어셈블리 하나 이상의 파일에 걸쳐 있을 수 있습니다, 있지만 일반적으로 어셈블리가 매핑됩니다 DLL과 일 대 일로 합니다.</span><span class="sxs-lookup"><span data-stu-id="45ac4-104">Although assemblies can span one or more files, typically an assembly maps one-to-one with a DLL.</span></span> <span data-ttu-id="45ac4-105">따라서이 섹션에서는 다음 어셈블리 명명 규칙으로 매핑할 수 있습니다만 DLL 명명 규칙을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="45ac4-105">Therefore, this section describes only DLL naming conventions, which then can be mapped to assembly naming conventions.</span></span>  
  
 <span data-ttu-id="45ac4-106">**✓ 않습니다** 대량의 System.Data 등의 기능을 제안 하는 Dll 어셈블리의 이름을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="45ac4-106">**✓ DO** choose names for your assembly DLLs that suggest large chunks of functionality, such as System.Data.</span></span>  
  
 <span data-ttu-id="45ac4-107">DLL 이름은 네임 스페이스 이름에 해당 필요는 없지만 어셈블리의 이름을 지정할 때 네임 스페이스 이름 뒤에 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="45ac4-107">Assembly and DLL names don’t have to correspond to namespace names, but it is reasonable to follow the namespace name when naming assemblies.</span></span> <span data-ttu-id="45ac4-108">경험에의 한 어셈블리에 포함 된 네임 스페이스의 공통 접두사에 따라 DLL 이름을 지정 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="45ac4-108">A good rule of thumb is to name the DLL based on the common prefix of the namespaces contained in the assembly.</span></span> <span data-ttu-id="45ac4-109">예를 들어 두 개의 네임 스페이스를 사용 하 여 어셈블리 `MyCompany.MyTechnology.FirstFeature` 및 `MyCompany.MyTechnology.SecondFeature`, 호출 될 수 있는 `MyCompany.MyTechnology.dll`합니다.</span><span class="sxs-lookup"><span data-stu-id="45ac4-109">For example, an assembly with two namespaces, `MyCompany.MyTechnology.FirstFeature` and `MyCompany.MyTechnology.SecondFeature`, could be called `MyCompany.MyTechnology.dll`.</span></span>  
  
 <span data-ttu-id="45ac4-110">**✓ 고려** 다음 패턴에 따라 Dll 이름 지정:</span><span class="sxs-lookup"><span data-stu-id="45ac4-110">**✓ CONSIDER** naming DLLs according to the following pattern:</span></span>  
  
 `<Company>.<Component>.dll`  
  
 <span data-ttu-id="45ac4-111">여기서 `<Component>` 점으로 구분 된 하나 이상의 절을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="45ac4-111">where `<Component>` contains one or more dot-separated clauses.</span></span> <span data-ttu-id="45ac4-112">예:</span><span class="sxs-lookup"><span data-stu-id="45ac4-112">For example:</span></span>  
  
 <span data-ttu-id="45ac4-113">`Litware.Controls.dll`.</span><span class="sxs-lookup"><span data-stu-id="45ac4-113">`Litware.Controls.dll`.</span></span>  
  
 <span data-ttu-id="45ac4-114">*Portions © 2005, 2009 Microsoft Corporation. 모든 권리 보유.*</span><span class="sxs-lookup"><span data-stu-id="45ac4-114">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="45ac4-115">*피어슨 교육, Inc.에서의 사용 권한으로 재인쇄 [Framework 디자인 지침: 규칙, 특징 및 다시 사용할 수 있는.NET 라이브러리를 2nd Edition에 대 한 패턴](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina 및 Brad Abrams 게시 하 여 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로: Addison Wesley Professional.*</span><span class="sxs-lookup"><span data-stu-id="45ac4-115">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45ac4-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="45ac4-116">See Also</span></span>  
 [<span data-ttu-id="45ac4-117">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="45ac4-117">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="45ac4-118">명명 지침</span><span class="sxs-lookup"><span data-stu-id="45ac4-118">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
