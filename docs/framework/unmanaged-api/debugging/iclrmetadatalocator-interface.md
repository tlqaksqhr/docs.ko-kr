---
title: "ICLRMetadataLocator 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICLRMetadataLocator
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRMetadataLocator
helpviewer_keywords:
- ICLRMetadataLocator interface [.NET Framework debugging]
ms.assetid: 43c944f4-406a-4df6-981e-0eabb33dd5d0
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a06997c47a85ced56dc579759192f7256def4f5a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="iclrmetadatalocator-interface"></a><span data-ttu-id="2b353-102">ICLRMetadataLocator 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2b353-102">ICLRMetadataLocator Interface</span></span>
<span data-ttu-id="2b353-103">데이터 액세스 서비스 계층을 대상 프로세스의 어셈블리 메타 데이터를 찾을 때 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b353-103">Used by the data access services layer to locate metadata of assemblies in a target process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2b353-104">메서드</span><span class="sxs-lookup"><span data-stu-id="2b353-104">Methods</span></span>  
  
|<span data-ttu-id="2b353-105">메서드</span><span class="sxs-lookup"><span data-stu-id="2b353-105">Method</span></span>|<span data-ttu-id="2b353-106">설명</span><span class="sxs-lookup"><span data-stu-id="2b353-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2b353-107">GetMetadata 메서드</span><span class="sxs-lookup"><span data-stu-id="2b353-107">GetMetadata Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrmetadatalocator-getmetadata-method.md)|<span data-ttu-id="2b353-108">대상 프로세스에서 이미지의 메타 데이터를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="2b353-108">Retrieves the metadata of an image from the target process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2b353-109">설명</span><span class="sxs-lookup"><span data-stu-id="2b353-109">Remarks</span></span>  
 <span data-ttu-id="2b353-110">API 클라이언트(즉, 디버거)에서는 이 인터페이스를 특정 대상 프로세스에 적절하게 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b353-110">The API client (that is, the debugger) must implement this interface as appropriate for the particular target process.</span></span> <span data-ttu-id="2b353-111">예를 들어 활성 프로세스에 대 한 구현을 메모리 덤프의 것과 다른 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2b353-111">For example, the implementation for a live process would be different from that of a memory dump.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2b353-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2b353-112">Requirements</span></span>  
 <span data-ttu-id="2b353-113">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2b353-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2b353-114">**헤더:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="2b353-114">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="2b353-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2b353-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2b353-116">**.**</span><span class="sxs-lookup"><span data-stu-id="2b353-116">**.**</span></span> <span data-ttu-id="2b353-117">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2b353-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b353-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2b353-118">See Also</span></span>  
 [<span data-ttu-id="2b353-119">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2b353-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
