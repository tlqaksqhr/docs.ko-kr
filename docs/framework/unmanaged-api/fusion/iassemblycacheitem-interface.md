---
title: "IAssemblyCacheItem 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IAssemblyCacheItem
api_location: fusion.dll
api_type: COM
f1_keywords: IAssemblyCacheItem
helpviewer_keywords: IAssemblyCacheItem interface [.NET Framework fusion]
ms.assetid: ccc9387a-9f44-4f4f-bf8f-0ea6d2afa21b
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e61b8dd90bb9311c1314a4cb4d68d75e0cd511c5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="iassemblycacheitem-interface"></a><span data-ttu-id="0e5cd-102">IAssemblyCacheItem 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0e5cd-102">IAssemblyCacheItem Interface</span></span>
<span data-ttu-id="0e5cd-103">전역 어셈블리 캐시에 단일 어셈블리를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0e5cd-103">Represents a single assembly in the global assembly cache.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0e5cd-104">메서드</span><span class="sxs-lookup"><span data-stu-id="0e5cd-104">Methods</span></span>  
  
|<span data-ttu-id="0e5cd-105">메서드</span><span class="sxs-lookup"><span data-stu-id="0e5cd-105">Method</span></span>|<span data-ttu-id="0e5cd-106">설명</span><span class="sxs-lookup"><span data-stu-id="0e5cd-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0e5cd-107">AbortItem 메서드</span><span class="sxs-lookup"><span data-stu-id="0e5cd-107">AbortItem Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-abortitem-method.md)|<span data-ttu-id="0e5cd-108">전역 어셈블리 캐시에 어셈블리를 해제 되기 전에 정리 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e5cd-108">Allows the assembly in the global assembly cache to perform cleanup operations before it is released.</span></span>|  
|[<span data-ttu-id="0e5cd-109">Commit 메서드</span><span class="sxs-lookup"><span data-stu-id="0e5cd-109">Commit Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-commit-method.md)|<span data-ttu-id="0e5cd-110">메모리에 캐시 된 어셈블리 참조를 커밋합니다.</span><span class="sxs-lookup"><span data-stu-id="0e5cd-110">Commits the cached assembly reference to memory.</span></span>|  
|[<span data-ttu-id="0e5cd-111">CreateStream 메서드</span><span class="sxs-lookup"><span data-stu-id="0e5cd-111">CreateStream Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-createstream-method.md)|<span data-ttu-id="0e5cd-112">지정 된 이름 및 형식 스트림을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0e5cd-112">Creates a stream with the specified name and format.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0e5cd-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0e5cd-113">Requirements</span></span>  
 <span data-ttu-id="0e5cd-114">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0e5cd-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0e5cd-115">**헤더:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="0e5cd-115">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="0e5cd-116">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0e5cd-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e5cd-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0e5cd-117">See Also</span></span>  
 [<span data-ttu-id="0e5cd-118">Fusion 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0e5cd-118">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)  
 [<span data-ttu-id="0e5cd-119">전역 어셈블리 캐시</span><span class="sxs-lookup"><span data-stu-id="0e5cd-119">Global Assembly Cache</span></span>](../../../../docs/framework/app-domains/gac.md)  
 [<span data-ttu-id="0e5cd-120">IAssemblyCache 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0e5cd-120">IAssemblyCache Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)
