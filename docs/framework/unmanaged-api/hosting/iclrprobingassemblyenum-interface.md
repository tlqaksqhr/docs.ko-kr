---
title: "ICLRProbingAssemblyEnum 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRProbingAssemblyEnum
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRProbingAssemblyEnum
helpviewer_keywords: ICLRProbingAssemblyEnum interface [.NET Framework hosting]
ms.assetid: e7d3ccab-b0f0-4872-8935-0ed72920171b
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6d810ab6e62c6df1b00305947de552ecdbe82141
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="iclrprobingassemblyenum-interface"></a><span data-ttu-id="4ade9-102">ICLRProbingAssemblyEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4ade9-102">ICLRProbingAssemblyEnum Interface</span></span>
<span data-ttu-id="4ade9-103">호스트가을 만들거나 해당 id를 이해할 필요 없이 내부 공용 언어 런타임 (CLR)에 있는 어셈블리의 id 정보를 사용 하 여 어셈블리 검색 id를 가져오는 데 사용할 수 있는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ade9-103">Provides methods that enable the host to get the probing identities of an assembly by using the assembly's identity information that is internal to the common language runtime (CLR), without needing to create or understand that identity.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4ade9-104">메서드</span><span class="sxs-lookup"><span data-stu-id="4ade9-104">Methods</span></span>  
  
|<span data-ttu-id="4ade9-105">메서드</span><span class="sxs-lookup"><span data-stu-id="4ade9-105">Method</span></span>|<span data-ttu-id="4ade9-106">설명</span><span class="sxs-lookup"><span data-stu-id="4ade9-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4ade9-107">Get 메서드</span><span class="sxs-lookup"><span data-stu-id="4ade9-107">Get Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-get-method.md)|<span data-ttu-id="4ade9-108">지정된 된 인덱스에서 어셈블리 id를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="4ade9-108">Gets the assembly identity at the specified index.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4ade9-109">설명</span><span class="sxs-lookup"><span data-stu-id="4ade9-109">Remarks</span></span>  
 <span data-ttu-id="4ade9-110">와 같은 메서드 [iclrassemblyidentitymanager:: Getprobingassembliesfromreference](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md) 반환는 `ICLRProbingAssemblyEnum` 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="4ade9-110">Methods such as [ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md) return an `ICLRProbingAssemblyEnum` instance.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4ade9-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4ade9-111">Requirements</span></span>  
 <span data-ttu-id="4ade9-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4ade9-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4ade9-113">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4ade9-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4ade9-114">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="4ade9-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4ade9-115">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4ade9-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ade9-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4ade9-116">See Also</span></span>  
 [<span data-ttu-id="4ade9-117">ICLRAssemblyIdentityManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4ade9-117">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [<span data-ttu-id="4ade9-118">ICLRAssemblyReferenceList 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4ade9-118">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [<span data-ttu-id="4ade9-119">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4ade9-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
