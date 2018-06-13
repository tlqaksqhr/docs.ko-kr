---
title: 호스팅 인터페이스
ms.date: 03/30/2017
helpviewer_keywords:
- interfaces [.NET Framework hosting]
- hosting interfaces [.NET Framework]
- unmanaged interfaces [.NET Framework], hosting
ms.assetid: cc64cb05-38da-418e-815a-daac8e8e26e5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c2bef9e1671b8487a6702cce71106c84a2984317
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33436162"
---
# <a name="hosting-interfaces"></a><span data-ttu-id="90066-102">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="90066-102">Hosting Interfaces</span></span>
<span data-ttu-id="90066-103">이 섹션에서는 관리 되지 않은 인터페이스 설명 호스트 응용 프로그램에 공용 언어 런타임 (CLR)를 통합 하 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90066-103">This section describes the interfaces that unmanaged hosts can use to integrate the common language runtime (CLR) into their applications.</span></span>  
  
 <span data-ttu-id="90066-104">.NET Framework 버전 2.0 호스팅 인터페이스는.NET Framework 버전 1.0 및 1.1 인터페이스 보다 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="90066-104">The .NET Framework version 2.0 hosting interfaces supersede the .NET Framework version 1.0 and 1.1 interfaces.</span></span> <span data-ttu-id="90066-105">인터페이스의 두 집합 간의 중요 한 차이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90066-105">There are significant differences between the two sets of interfaces.</span></span> <span data-ttu-id="90066-106">인터페이스를 혼합 해 예기치 않은 동작이 발생할 수 있으며 권장 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="90066-106">Mixing them could cause unexpected behavior and is not recommended.</span></span>  
  
 <span data-ttu-id="90066-107">.NET Framework 버전 3.0 및 3.5는.NET Framework 버전 2.0 호스팅 인터페이스를 사용 하 여 및 호스팅 기능을 정의 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="90066-107">The .NET Framework versions 3.0 and 3.5 use the .NET Framework version 2.0 hosting interfaces, and do not introduce any hosting features.</span></span>  
  
 <span data-ttu-id="90066-108">[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] 호스팅 인터페이스는.NET Framework 2.0 인터페이스 보다 우선 합니다.</span><span class="sxs-lookup"><span data-stu-id="90066-108">The [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] hosting interfaces supersede the .NET Framework 2.0 interfaces.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="90066-109">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="90066-109">In This Section</span></span>  
 [<span data-ttu-id="90066-110">사용되지 않는 CLR 호스팅 인터페이스 및 Coclass</span><span class="sxs-lookup"><span data-stu-id="90066-110">Deprecated CLR Hosting Interfaces and Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-interfaces-and-coclasses.md)  
 <span data-ttu-id="90066-111">.NET Framework 버전 1.0 및 1.1에서에서 도입 된 호스팅 인터페이스에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="90066-111">Describes the hosting interfaces introduced in the .NET Framework versions 1.0 and 1.1.</span></span>  
  
 [<span data-ttu-id="90066-112">CLR 호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="90066-112">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)  
 <span data-ttu-id="90066-113">.NET Framework 버전 2.0에에서 도입 된 호스팅 인터페이스에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="90066-113">Describes the hosting interfaces introduced in the .NET Framework version 2.0.</span></span>  
  
 [<span data-ttu-id="90066-114">.NET Framework 4 및 4.5에 추가된 CLR 호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="90066-114">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)  
 <span data-ttu-id="90066-115">에 도입 된 호스팅 인터페이스에 설명 된 [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="90066-115">Describes the hosting interfaces introduced in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="90066-116">관련 단원</span><span class="sxs-lookup"><span data-stu-id="90066-116">Related Sections</span></span>  
 [<span data-ttu-id="90066-117">호스팅 Coclass</span><span class="sxs-lookup"><span data-stu-id="90066-117">Hosting Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)  
  
 [<span data-ttu-id="90066-118">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="90066-118">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)  
  
 [<span data-ttu-id="90066-119">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="90066-119">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)  
  
 [<span data-ttu-id="90066-120">호스팅 구조체</span><span class="sxs-lookup"><span data-stu-id="90066-120">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)  
  
 [<span data-ttu-id="90066-121">호스팅</span><span class="sxs-lookup"><span data-stu-id="90066-121">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)  
  
 [<span data-ttu-id="90066-122">런타임 호스트</span><span class="sxs-lookup"><span data-stu-id="90066-122">Runtime Hosts</span></span>](http://msdn.microsoft.com/library/99d9246a-b994-4fe5-985c-8588d1d59998)
