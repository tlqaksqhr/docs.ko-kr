---
title: ICLRMetadataLocator 인터페이스
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fd7a67237d89864915f8b4f1f7361d1f113d1e5d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33404745"
---
# <a name="iclrmetadatalocator-interface"></a><span data-ttu-id="e5bae-102">ICLRMetadataLocator 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e5bae-102">ICLRMetadataLocator Interface</span></span>
<span data-ttu-id="e5bae-103">데이터 액세스 서비스 계층을 대상 프로세스의 어셈블리 메타 데이터를 찾을 때 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5bae-103">Used by the data access services layer to locate metadata of assemblies in a target process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e5bae-104">메서드</span><span class="sxs-lookup"><span data-stu-id="e5bae-104">Methods</span></span>  
  
|<span data-ttu-id="e5bae-105">메서드</span><span class="sxs-lookup"><span data-stu-id="e5bae-105">Method</span></span>|<span data-ttu-id="e5bae-106">설명</span><span class="sxs-lookup"><span data-stu-id="e5bae-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e5bae-107">GetMetadata 메서드</span><span class="sxs-lookup"><span data-stu-id="e5bae-107">GetMetadata Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrmetadatalocator-getmetadata-method.md)|<span data-ttu-id="e5bae-108">대상 프로세스에서 이미지의 메타 데이터를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="e5bae-108">Retrieves the metadata of an image from the target process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e5bae-109">설명</span><span class="sxs-lookup"><span data-stu-id="e5bae-109">Remarks</span></span>  
 <span data-ttu-id="e5bae-110">API 클라이언트(즉, 디버거)에서는 이 인터페이스를 특정 대상 프로세스에 적절하게 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5bae-110">The API client (that is, the debugger) must implement this interface as appropriate for the particular target process.</span></span> <span data-ttu-id="e5bae-111">예를 들어 활성 프로세스에 대 한 구현을 메모리 덤프의 것과 다른 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e5bae-111">For example, the implementation for a live process would be different from that of a memory dump.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5bae-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e5bae-112">Requirements</span></span>  
 <span data-ttu-id="e5bae-113">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e5bae-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5bae-114">**헤더:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="e5bae-114">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="e5bae-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e5bae-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e5bae-116">**.**</span><span class="sxs-lookup"><span data-stu-id="e5bae-116">**.**</span></span> <span data-ttu-id="e5bae-117">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5bae-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5bae-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e5bae-118">See Also</span></span>  
 [<span data-ttu-id="e5bae-119">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e5bae-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
