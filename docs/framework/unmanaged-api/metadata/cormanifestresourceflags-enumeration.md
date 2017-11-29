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
ms.openlocfilehash: 5cdaba8b1186d1720ff8b64f50a8effc4691fe8c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="cormanifestresourceflags-enumeration"></a><span data-ttu-id="9e8ea-102">CorManifestResourceFlags 열거형</span><span class="sxs-lookup"><span data-stu-id="9e8ea-102">CorManifestResourceFlags Enumeration</span></span>
<span data-ttu-id="9e8ea-103">어셈블리 매니페스트에 인코딩된 리소스의 표시 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9e8ea-103">Indicates the visibility of resources encoded in an assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e8ea-104">구문</span><span class="sxs-lookup"><span data-stu-id="9e8ea-104">Syntax</span></span>  
  
```  
typedef enum CorManifestResourceFlags {  
  
    mrVisibilityMask        =   0x0007,  
    mrPublic                =   0x0001,  
    mrPrivate               =   0x0002  
  
} CorManifestResourceFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="9e8ea-105">멤버</span><span class="sxs-lookup"><span data-stu-id="9e8ea-105">Members</span></span>  
  
|<span data-ttu-id="9e8ea-106">멤버</span><span class="sxs-lookup"><span data-stu-id="9e8ea-106">Member</span></span>|<span data-ttu-id="9e8ea-107">설명</span><span class="sxs-lookup"><span data-stu-id="9e8ea-107">Description</span></span>|  
|------------|-----------------|  
|`mrVisibilityMask`|<span data-ttu-id="9e8ea-108">예약됨.</span><span class="sxs-lookup"><span data-stu-id="9e8ea-108">Reserved.</span></span>|  
|`mrPublic`|<span data-ttu-id="9e8ea-109">리소스는 공용입니다.</span><span class="sxs-lookup"><span data-stu-id="9e8ea-109">The resources are public.</span></span>|  
|`mrPrivate`|<span data-ttu-id="9e8ea-110">리소스는 private입니다.</span><span class="sxs-lookup"><span data-stu-id="9e8ea-110">The resources are private.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9e8ea-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9e8ea-111">Requirements</span></span>  
 <span data-ttu-id="9e8ea-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9e8ea-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9e8ea-113">**헤더:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="9e8ea-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="9e8ea-114">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9e8ea-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e8ea-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9e8ea-115">See Also</span></span>  
 [<span data-ttu-id="9e8ea-116">메타 데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="9e8ea-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
