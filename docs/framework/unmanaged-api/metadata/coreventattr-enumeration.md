---
title: "CorEventAttr 열거형"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorEventAttr
api_location: mscoree.dll
api_type: COM
f1_keywords: CorEventAttr
helpviewer_keywords: CorEventAttr enumeration [.NET Framework metadata]
ms.assetid: dc2b3281-3820-487e-930d-350b66dc6417
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c4302ff7627bf5e06f3c1b1263ec38a31393d411
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="coreventattr-enumeration"></a><span data-ttu-id="bfb93-102">CorEventAttr 열거형</span><span class="sxs-lookup"><span data-stu-id="bfb93-102">CorEventAttr Enumeration</span></span>
<span data-ttu-id="bfb93-103">이벤트의 메타데이터를 설명하는 값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="bfb93-103">Contains values that describe the metadata of an event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bfb93-104">구문</span><span class="sxs-lookup"><span data-stu-id="bfb93-104">Syntax</span></span>  
  
```  
typedef enum CorEventAttr {  
  
    evSpecialName           =   0x0200,  
  
    evReservedMask          =   0x0400,  
    evRTSpecialName         =   0x0400,  
  
} CorEventAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="bfb93-105">멤버</span><span class="sxs-lookup"><span data-stu-id="bfb93-105">Members</span></span>  
  
|<span data-ttu-id="bfb93-106">멤버</span><span class="sxs-lookup"><span data-stu-id="bfb93-106">Member</span></span>|<span data-ttu-id="bfb93-107">설명</span><span class="sxs-lookup"><span data-stu-id="bfb93-107">Description</span></span>|  
|------------|-----------------|  
|`evSpecialName`|<span data-ttu-id="bfb93-108">이벤트, 특별 한 이며 해당 이름을 설명 하 고 있음을 지정 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="bfb93-108">Specifies that the event is special, and that its name describes how.</span></span>|  
|`evReservedMask`|<span data-ttu-id="bfb93-109">공용 언어 런타임에서 내부 용도로 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfb93-109">Reserved for internal use by the common language runtime.</span></span>|  
|`evRTSpecialName`|<span data-ttu-id="bfb93-110">공용 언어 런타임에서 이벤트 이름을 인코딩을 확인 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfb93-110">Specifies that the common language runtime should check the encoding of the event name.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bfb93-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bfb93-111">Requirements</span></span>  
 <span data-ttu-id="bfb93-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="bfb93-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bfb93-113">**헤더:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="bfb93-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="bfb93-114">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bfb93-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfb93-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bfb93-115">See Also</span></span>  
 [<span data-ttu-id="bfb93-116">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="bfb93-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
