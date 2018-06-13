---
title: CorUnmanagedCallingConvention 열거형
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0b249d26335a66b55d0643f3e75bfd90554f731e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33448871"
---
# <a name="corunmanagedcallingconvention-enumeration"></a><span data-ttu-id="85a91-102">CorUnmanagedCallingConvention 열거형</span><span class="sxs-lookup"><span data-stu-id="85a91-102">CorUnmanagedCallingConvention Enumeration</span></span>
<span data-ttu-id="85a91-103">비관리 코드에 대 한 호출 규칙을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="85a91-103">Specifies the calling conventions for unmanaged code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85a91-104">구문</span><span class="sxs-lookup"><span data-stu-id="85a91-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="85a91-105">멤버</span><span class="sxs-lookup"><span data-stu-id="85a91-105">Members</span></span>  
  
|<span data-ttu-id="85a91-106">멤버</span><span class="sxs-lookup"><span data-stu-id="85a91-106">Member</span></span>|<span data-ttu-id="85a91-107">설명</span><span class="sxs-lookup"><span data-stu-id="85a91-107">Description</span></span>|  
|------------|-----------------|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_C`|<span data-ttu-id="85a91-108">C 언어 호출 규칙입니다.</span><span class="sxs-lookup"><span data-stu-id="85a91-108">The C language calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_STDCALL`|<span data-ttu-id="85a91-109">표준 호출 규칙입니다.</span><span class="sxs-lookup"><span data-stu-id="85a91-109">The standard calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_THISCALL`|<span data-ttu-id="85a91-110">"This" 호출 규칙입니다.</span><span class="sxs-lookup"><span data-stu-id="85a91-110">The "this" calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_FASTCALL`|<span data-ttu-id="85a91-111">"빠른" 호출 규칙입니다.</span><span class="sxs-lookup"><span data-stu-id="85a91-111">The "fast" calling convention.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_C`|<span data-ttu-id="85a91-112">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="85a91-112">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_STDCALL`|<span data-ttu-id="85a91-113">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="85a91-113">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_THISCALL`|<span data-ttu-id="85a91-114">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="85a91-114">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_FASTCALL`|<span data-ttu-id="85a91-115">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="85a91-115">Not used.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="85a91-116">설명</span><span class="sxs-lookup"><span data-stu-id="85a91-116">Remarks</span></span>  
 <span data-ttu-id="85a91-117">CLR은.NET Framework 버전 1.0에서에서 "고속" 호출 규칙을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="85a91-117">The CLR does not support the "fast" calling convention in the .NET Framework version 1.0.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="85a91-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="85a91-118">Requirements</span></span>  
 <span data-ttu-id="85a91-119">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="85a91-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="85a91-120">**헤더:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="85a91-120">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="85a91-121">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="85a91-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85a91-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="85a91-122">See Also</span></span>  
 [<span data-ttu-id="85a91-123">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="85a91-123">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
