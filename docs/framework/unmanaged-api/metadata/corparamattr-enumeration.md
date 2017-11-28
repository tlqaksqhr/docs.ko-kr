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
ms.openlocfilehash: 469c148dbce4139a3d72021991185f3ed6f7c5da
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="corparamattr-enumeration"></a><span data-ttu-id="e7df7-102">CorParamAttr 열거형</span><span class="sxs-lookup"><span data-stu-id="e7df7-102">CorParamAttr Enumeration</span></span>
<span data-ttu-id="e7df7-103">메서드 매개 변수의 메타데이터를 설명하는 값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="e7df7-103">Contains values that describe the metadata of a method parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7df7-104">구문</span><span class="sxs-lookup"><span data-stu-id="e7df7-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="e7df7-105">멤버</span><span class="sxs-lookup"><span data-stu-id="e7df7-105">Members</span></span>  
  
|<span data-ttu-id="e7df7-106">멤버</span><span class="sxs-lookup"><span data-stu-id="e7df7-106">Member</span></span>|<span data-ttu-id="e7df7-107">설명</span><span class="sxs-lookup"><span data-stu-id="e7df7-107">Description</span></span>|  
|------------|-----------------|  
|`pdIn`|<span data-ttu-id="e7df7-108">매개 변수 메서드 호출으로 전달 되도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7df7-108">Specifies that the parameter is passed into the method call.</span></span>|  
|`pdOut`|<span data-ttu-id="e7df7-109">전달 되도록 지정 매개 변수는 메서드의 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7df7-109">Specifies that the parameter is passed from the method return.</span></span>|  
|`pdOptional`|<span data-ttu-id="e7df7-110">매개 변수가 옵션 임을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7df7-110">Specifies that the parameter is optional.</span></span>|  
|`pdReservedMask`|<span data-ttu-id="e7df7-111">공용 언어 런타임에서 내부 용도로 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7df7-111">Reserved for internal use by the common language runtime.</span></span>|  
|`pdHasDefault`|<span data-ttu-id="e7df7-112">매개 변수 기본값을 갖도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7df7-112">Specifies that the parameter has a default value.</span></span>|  
|`pdHasFieldMarshal`|<span data-ttu-id="e7df7-113">매개 변수 마샬링 정보 갖도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7df7-113">Specifies that the parameter has marshaling information.</span></span>|  
|`pdUnused`|<span data-ttu-id="e7df7-114">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e7df7-114">Unused.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e7df7-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e7df7-115">Requirements</span></span>  
 <span data-ttu-id="e7df7-116">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e7df7-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e7df7-117">**헤더:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="e7df7-117">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="e7df7-118">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e7df7-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7df7-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e7df7-119">See Also</span></span>  
 [<span data-ttu-id="e7df7-120">메타 데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="e7df7-120">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
