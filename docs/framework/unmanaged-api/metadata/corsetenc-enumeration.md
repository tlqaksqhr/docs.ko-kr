---
title: "CorSetENC 열거형"
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
- CorSetENC
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSetENC
helpviewer_keywords:
- CorSetENC enumeration [.NET Framework metadata]
ms.assetid: fe4150e8-071d-43fb-8e06-c3c616dbeed2
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0f39a1481361377fce3f6b55cf6c7daf8c075ce5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="corsetenc-enumeration"></a><span data-ttu-id="357f5-102">CorSetENC 열거형</span><span class="sxs-lookup"><span data-stu-id="357f5-102">CorSetENC Enumeration</span></span>
<span data-ttu-id="357f5-103">메타데이터 생성 중의 동작에 영향을 주는 데 사용되는 값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="357f5-103">Contains values used to influence behavior during the generation of metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="357f5-104">구문</span><span class="sxs-lookup"><span data-stu-id="357f5-104">Syntax</span></span>  
  
```  
typedef enum CorSetENC {  
  
    MDSetENCOn                  = 0x00000001,  
    MDSetENCOff                 = 0x00000002,  
  
    MDUpdateENC                 = 0x00000001,  
    MDUpdateFull                = 0x00000002,  
    MDUpdateExtension           = 0x00000003,  
    MDUpdateIncremental         = 0x00000004,  
    MDUpdateDelta               = 0x00000005,  
    MDUpdateMask                = 0x00000007  
  
} CorSetENC;  
```  
  
## <a name="members"></a><span data-ttu-id="357f5-105">멤버</span><span class="sxs-lookup"><span data-stu-id="357f5-105">Members</span></span>  
  
|<span data-ttu-id="357f5-106">멤버</span><span class="sxs-lookup"><span data-stu-id="357f5-106">Member</span></span>|<span data-ttu-id="357f5-107">설명</span><span class="sxs-lookup"><span data-stu-id="357f5-107">Description</span></span>|  
|------------|-----------------|  
|`MDSetENCOn`|<span data-ttu-id="357f5-108">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="357f5-108">Obsolete.</span></span>|  
|`MDSetENCOff`|<span data-ttu-id="357f5-109">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="357f5-109">Obsolete.</span></span>|  
|`MDUpdateENC`|<span data-ttu-id="357f5-110">메타 데이터, 업데이트 하는 반면 토큰은 이동할 수 없음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="357f5-110">Indicates that whereas metadata can be updated, tokens cannot be moved.</span></span>|  
|`MDUpdateFull`|<span data-ttu-id="357f5-111">업데이트 동안 토큰을 이동할 수 있는지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="357f5-111">Indicates that tokens can be moved during updates.</span></span>|  
|`MDUpdateExtension`|<span data-ttu-id="357f5-112">업데이트 추가만 구성 수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="357f5-112">Indicates that updates can consist only of additions.</span></span> <span data-ttu-id="357f5-113">토큰을 이동할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="357f5-113">Tokens cannot be moved.</span></span>|  
|`MDUpdateIncremental`|<span data-ttu-id="357f5-114">증분 컴파일을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="357f5-114">Indicates that compilation is incremental.</span></span>|  
|`MDUpdateDelta`|<span data-ttu-id="357f5-115">저장 해야 하는 변경 된 메타 데이터만 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="357f5-115">Indicates that only changed metadata should be saved.</span></span>|  
|`MDUpdateMask`|<span data-ttu-id="357f5-116">포함 `MDUpdateENC`, `MDUpdateFull` 및 `MDUpdateIncremental`합니다.</span><span class="sxs-lookup"><span data-stu-id="357f5-116">Includes `MDUpdateENC`, `MDUpdateFull` and `MDUpdateIncremental`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="357f5-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="357f5-117">Requirements</span></span>  
 <span data-ttu-id="357f5-118">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="357f5-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="357f5-119">**헤더:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="357f5-119">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="357f5-120">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="357f5-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="357f5-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="357f5-121">See Also</span></span>  
 [<span data-ttu-id="357f5-122">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="357f5-122">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
