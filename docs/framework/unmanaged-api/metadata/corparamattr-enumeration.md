---
title: "CorParamAttr 열거형"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorParamAttr
api_location: mscoree.dll
api_type: COM
f1_keywords: CorParamAttr
helpviewer_keywords: CorParamAttr enumeration [.NET Framework metadata]
ms.assetid: a7ff90ad-dad8-48e8-917d-4aa9a118cbc8
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 87afe125536473f99053db7d2fd4ae61fa4017ba
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="corparamattr-enumeration"></a><span data-ttu-id="e2ce6-102">CorParamAttr 열거형</span><span class="sxs-lookup"><span data-stu-id="e2ce6-102">CorParamAttr Enumeration</span></span>
<span data-ttu-id="e2ce6-103">메서드 매개 변수의 메타데이터를 설명하는 값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="e2ce6-103">Contains values that describe the metadata of a method parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2ce6-104">구문</span><span class="sxs-lookup"><span data-stu-id="e2ce6-104">Syntax</span></span>  
  
```  
typedef enum CorParamAttr {  
  
    pdIn                        =   0x0001,  
    pdOut                       =   0x0002,  
    pdOptional                  =   0x0010,  
  
    pdReservedMask              =   0xf000,  
    pdHasDefault                =   0x1000,  
    pdHasFieldMarshal           =   0x2000,  
  
    pdUnused                    =   0xcfe0  
  
} CorParamAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="e2ce6-105">멤버</span><span class="sxs-lookup"><span data-stu-id="e2ce6-105">Members</span></span>  
  
|<span data-ttu-id="e2ce6-106">멤버</span><span class="sxs-lookup"><span data-stu-id="e2ce6-106">Member</span></span>|<span data-ttu-id="e2ce6-107">설명</span><span class="sxs-lookup"><span data-stu-id="e2ce6-107">Description</span></span>|  
|------------|-----------------|  
|`pdIn`|<span data-ttu-id="e2ce6-108">매개 변수 메서드 호출으로 전달 되도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2ce6-108">Specifies that the parameter is passed into the method call.</span></span>|  
|`pdOut`|<span data-ttu-id="e2ce6-109">전달 되도록 지정 매개 변수는 메서드의 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2ce6-109">Specifies that the parameter is passed from the method return.</span></span>|  
|`pdOptional`|<span data-ttu-id="e2ce6-110">매개 변수가 옵션 임을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2ce6-110">Specifies that the parameter is optional.</span></span>|  
|`pdReservedMask`|<span data-ttu-id="e2ce6-111">공용 언어 런타임에서 내부 용도로 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2ce6-111">Reserved for internal use by the common language runtime.</span></span>|  
|`pdHasDefault`|<span data-ttu-id="e2ce6-112">매개 변수 기본값을 갖도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2ce6-112">Specifies that the parameter has a default value.</span></span>|  
|`pdHasFieldMarshal`|<span data-ttu-id="e2ce6-113">매개 변수 마샬링 정보 갖도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2ce6-113">Specifies that the parameter has marshaling information.</span></span>|  
|`pdUnused`|<span data-ttu-id="e2ce6-114">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e2ce6-114">Unused.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e2ce6-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e2ce6-115">Requirements</span></span>  
 <span data-ttu-id="e2ce6-116">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e2ce6-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2ce6-117">**헤더:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="e2ce6-117">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="e2ce6-118">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e2ce6-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2ce6-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e2ce6-119">See Also</span></span>  
 [<span data-ttu-id="e2ce6-120">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="e2ce6-120">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
