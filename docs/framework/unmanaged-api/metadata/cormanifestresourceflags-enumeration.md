---
title: "CorManifestResourceFlags 열거형"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorManifestResourceFlags
api_location: mscoree.dll
api_type: COM
f1_keywords: CorManifestResourceFlags
helpviewer_keywords: CorManifestResourceFlags enumeration [.NET Framework metadata]
ms.assetid: 1b0306b7-622b-4b57-8edc-3c713bb147ae
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7a1ad2aa505ba77f136a28b2cfa9f1fa357c37ab
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="cormanifestresourceflags-enumeration"></a><span data-ttu-id="1f7bb-102">CorManifestResourceFlags 열거형</span><span class="sxs-lookup"><span data-stu-id="1f7bb-102">CorManifestResourceFlags Enumeration</span></span>
<span data-ttu-id="1f7bb-103">어셈블리 매니페스트에 인코딩된 리소스의 표시 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1f7bb-103">Indicates the visibility of resources encoded in an assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f7bb-104">구문</span><span class="sxs-lookup"><span data-stu-id="1f7bb-104">Syntax</span></span>  
  
```  
typedef enum CorManifestResourceFlags {  
  
    mrVisibilityMask        =   0x0007,  
    mrPublic                =   0x0001,  
    mrPrivate               =   0x0002  
  
} CorManifestResourceFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="1f7bb-105">멤버</span><span class="sxs-lookup"><span data-stu-id="1f7bb-105">Members</span></span>  
  
|<span data-ttu-id="1f7bb-106">멤버</span><span class="sxs-lookup"><span data-stu-id="1f7bb-106">Member</span></span>|<span data-ttu-id="1f7bb-107">설명</span><span class="sxs-lookup"><span data-stu-id="1f7bb-107">Description</span></span>|  
|------------|-----------------|  
|`mrVisibilityMask`|<span data-ttu-id="1f7bb-108">예약됨.</span><span class="sxs-lookup"><span data-stu-id="1f7bb-108">Reserved.</span></span>|  
|`mrPublic`|<span data-ttu-id="1f7bb-109">리소스는 공용입니다.</span><span class="sxs-lookup"><span data-stu-id="1f7bb-109">The resources are public.</span></span>|  
|`mrPrivate`|<span data-ttu-id="1f7bb-110">리소스는 private입니다.</span><span class="sxs-lookup"><span data-stu-id="1f7bb-110">The resources are private.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1f7bb-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1f7bb-111">Requirements</span></span>  
 <span data-ttu-id="1f7bb-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1f7bb-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1f7bb-113">**헤더:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="1f7bb-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="1f7bb-114">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1f7bb-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f7bb-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1f7bb-115">See Also</span></span>  
 [<span data-ttu-id="1f7bb-116">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="1f7bb-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
