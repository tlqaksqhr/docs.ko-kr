---
title: "CorUnmanagedCallingConvention 열거형"
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
- CorUnmanagedCallingConvention
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorUnmanagedCallingConvention
helpviewer_keywords:
- CorUnmanagedCallingConvention enumeration [.NET Framework metadata]
ms.assetid: 83058790-160b-4703-a5eb-74b66acbdfa9
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 446a948c8809d9f098ede8fbb9b426f6169ce812
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="corunmanagedcallingconvention-enumeration"></a><span data-ttu-id="b7b2c-102">CorUnmanagedCallingConvention 열거형</span><span class="sxs-lookup"><span data-stu-id="b7b2c-102">CorUnmanagedCallingConvention Enumeration</span></span>
<span data-ttu-id="b7b2c-103">비관리 코드에 대 한 호출 규칙을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b7b2c-103">Specifies the calling conventions for unmanaged code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7b2c-104">구문</span><span class="sxs-lookup"><span data-stu-id="b7b2c-104">Syntax</span></span>  
  
```  
typedef enum CorUnmanagedCallingConvention {  
  
    IMAGE_CEE_UNMANAGED_CALLCONV_C         = 0x1,  
    IMAGE_CEE_UNMANAGED_CALLCONV_STDCALL   = 0x2,  
    IMAGE_CEE_UNMANAGED_CALLCONV_THISCALL  = 0x3,  
    IMAGE_CEE_UNMANAGED_CALLCONV_FASTCALL  = 0x4,  
  
    IMAGE_CEE_CS_CALLCONV_C                = 0x1,  
    IMAGE_CEE_CS_CALLCONV_STDCALL          = 0x2,  
    IMAGE_CEE_CS_CALLCONV_THISCALL         = 0x3,  
    IMAGE_CEE_CS_CALLCONV_FASTCALL         = 0x4  
  
} CorUnmanagedCallingConvention;  
```  
  
## <a name="members"></a><span data-ttu-id="b7b2c-105">멤버</span><span class="sxs-lookup"><span data-stu-id="b7b2c-105">Members</span></span>  
  
|<span data-ttu-id="b7b2c-106">멤버</span><span class="sxs-lookup"><span data-stu-id="b7b2c-106">Member</span></span>|<span data-ttu-id="b7b2c-107">설명</span><span class="sxs-lookup"><span data-stu-id="b7b2c-107">Description</span></span>|  
|------------|-----------------|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_C`|<span data-ttu-id="b7b2c-108">C 언어 호출 규칙입니다.</span><span class="sxs-lookup"><span data-stu-id="b7b2c-108">The C language calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_STDCALL`|<span data-ttu-id="b7b2c-109">표준 호출 규칙입니다.</span><span class="sxs-lookup"><span data-stu-id="b7b2c-109">The standard calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_THISCALL`|<span data-ttu-id="b7b2c-110">"This" 호출 규칙입니다.</span><span class="sxs-lookup"><span data-stu-id="b7b2c-110">The "this" calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_FASTCALL`|<span data-ttu-id="b7b2c-111">"빠른" 호출 규칙입니다.</span><span class="sxs-lookup"><span data-stu-id="b7b2c-111">The "fast" calling convention.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_C`|<span data-ttu-id="b7b2c-112">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b7b2c-112">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_STDCALL`|<span data-ttu-id="b7b2c-113">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b7b2c-113">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_THISCALL`|<span data-ttu-id="b7b2c-114">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b7b2c-114">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_FASTCALL`|<span data-ttu-id="b7b2c-115">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b7b2c-115">Not used.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b7b2c-116">설명</span><span class="sxs-lookup"><span data-stu-id="b7b2c-116">Remarks</span></span>  
 <span data-ttu-id="b7b2c-117">CLR은.NET Framework 버전 1.0에서에서 "고속" 호출 규칙을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b7b2c-117">The CLR does not support the "fast" calling convention in the .NET Framework version 1.0.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7b2c-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b7b2c-118">Requirements</span></span>  
 <span data-ttu-id="b7b2c-119">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b7b2c-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7b2c-120">**헤더:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="b7b2c-120">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="b7b2c-121">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b7b2c-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7b2c-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b7b2c-122">See Also</span></span>  
 [<span data-ttu-id="b7b2c-123">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="b7b2c-123">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
