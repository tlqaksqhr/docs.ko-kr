---
title: "안정성"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SQL Server [.NET Framework]
- managed code, reliability
- reliability [.NET Framework]
- writing reliable code
- code, reliability
ms.assetid: 294aa306-0afe-4cbe-b397-86ba9f1860f8
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3329bff14d2ab395fecfde0f26942b7cb1b9640e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="reliability"></a><span data-ttu-id="aa047-102">안정성</span><span class="sxs-lookup"><span data-stu-id="aa047-102">Reliability</span></span>
<span data-ttu-id="aa047-103">SQL Server와 같은 서버 환경에서 실행되는 코드를 비동기 예외로부터 보호하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="aa047-103">It is important that code executing in server environments such as SQL Server protect against asynchronous exceptions.</span></span> <span data-ttu-id="aa047-104">여기에서 설명한 대로 안정성은 SQL Server에는 특별하지 않지만 .NET Framework 버전 2.0 환경에서 실행되는 모든 호스트용으로 신뢰할 수 있는 코드를 작성할 때는 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="aa047-104">Reliability, as discussed here, is not specific to SQL Server but to writing reliable code for any host executing in a .NET Framework version 2.0 environment.</span></span> <span data-ttu-id="aa047-105">그러나 SQL Server는 버전 2.0의 새로운 안정성 기능을 광범위하게 이용하는 첫 번째 서비스이므로 예제로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa047-105">However, SQL Server is the first service making extensive use of the new reliability features of version 2.0, so it is used as an example.</span></span>  
  
 <span data-ttu-id="aa047-106">SQL Server에서 실행되는 코드는 다른 서버 환경보다 더 엄격한 안정성 지침을 처리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa047-106">Code running in SQL Server must deal with more stringent reliability guidelines than other server environments.</span></span> <span data-ttu-id="aa047-107">리소스 사용의 에지에서 SQL Server가 지속적으로 작동하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="aa047-107">This is due to SQL Server’s steady operation at the edge of resource consumption.</span></span>  <span data-ttu-id="aa047-108"><xref:System.OutOfMemoryException> 및 <xref:System.Threading.ThreadAbortException> 예외는 SQL Server 환경에서 일반적으로 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="aa047-108"><xref:System.OutOfMemoryException> and <xref:System.Threading.ThreadAbortException> exceptions are not uncommon in the SQL Server environment.</span></span> <span data-ttu-id="aa047-109">이러한 지침은 일반적으로 안정성보다는 완전히 신뢰할 수 있는 관리 코드가 <xref:System.AppDomain> 수준 재활용 시 올바른 절차에 따라 실패할 수 있도록 하는 데 더 중점을 둡니다. 이것이 서버에서 일관성과 가용성을 유지하는 기본 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="aa047-109">These guidelines in general are focused less on reliability and more on allowing fully trusted managed code to fail gracefully in the face of <xref:System.AppDomain>-level recycling, which is the primary way the server maintains consistency and availability.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="aa047-110">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="aa047-110">In This Section</span></span>  
 [<span data-ttu-id="aa047-111">SQL Server 프로그래밍 및 호스트 보호 특성</span><span class="sxs-lookup"><span data-stu-id="aa047-111">SQL Server Programming and Host Protection Attributes</span></span>](../../../docs/framework/performance/sql-server-programming-and-host-protection-attributes.md)  
 <span data-ttu-id="aa047-112">SQL Server에서 <xref:System.Security.Permissions.HostProtectionAttribute> 특성을 사용하여 관리 코드의 실행을 제한하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="aa047-112">Describes how the <xref:System.Security.Permissions.HostProtectionAttribute> attribute is used by SQL Server to restrict the execution of managed code.</span></span>  
  
 [<span data-ttu-id="aa047-113">안전성 모범 사례</span><span class="sxs-lookup"><span data-stu-id="aa047-113">Reliability Best Practices</span></span>](../../../docs/framework/performance/reliability-best-practices.md)  
 <span data-ttu-id="aa047-114">안정성 요구 사항을 충족하는 코드를 작성하기 위한 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="aa047-114">Provides guidelines for writing code that meets reliability requirements.</span></span>  
  
 [<span data-ttu-id="aa047-115">제약이 있는 실행 영역</span><span class="sxs-lookup"><span data-stu-id="aa047-115">Constrained Execution Regions</span></span>](../../../docs/framework/performance/constrained-execution-regions.md)  
 <span data-ttu-id="aa047-116">제약이 있는 실행 영역(CER)의 동작과 함수에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="aa047-116">Describes the function and behavior of constrained execution regions (CERs).</span></span>  
  
## <a name="reference"></a><span data-ttu-id="aa047-117">참조</span><span class="sxs-lookup"><span data-stu-id="aa047-117">Reference</span></span>  
 <xref:System.Security.Permissions.HostProtectionAttribute>  
  
 <xref:System.Security.Permissions.HostProtectionResource>
