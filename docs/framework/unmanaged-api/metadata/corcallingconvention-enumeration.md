---
title: "CorCallingConvention 열거형"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorCallingConvention
api_location: mscoree.dll
api_type: COM
f1_keywords: CorCallingConvention
helpviewer_keywords: CorCallingConvention enumeration [.NET Framework metadata]
ms.assetid: 69156fbf-7219-43bf-b4b8-b13f1a2fcb86
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 154fbcc393bb56ab2c249a4928a4451dced9761a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="corcallingconvention-enumeration"></a><span data-ttu-id="f2718-102">CorCallingConvention 열거형</span><span class="sxs-lookup"><span data-stu-id="f2718-102">CorCallingConvention Enumeration</span></span>
<span data-ttu-id="f2718-103">관리 코드에서 수행된 호출 규칙의 형식을 설명하는 값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="f2718-103">Contains values that describe the types of calling conventions that are made in managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2718-104">구문</span><span class="sxs-lookup"><span data-stu-id="f2718-104">Syntax</span></span>  
  
```  
typedef enum CorCallingConvention  
{  
    IMAGE_CEE_CS_CALLCONV_DEFAULT       = 0x0,  
  
    IMAGE_CEE_CS_CALLCONV_VARARG        = 0x5,  
    IMAGE_CEE_CS_CALLCONV_FIELD         = 0x6,  
    IMAGE_CEE_CS_CALLCONV_LOCAL_SIG     = 0x7,  
    IMAGE_CEE_CS_CALLCONV_PROPERTY      = 0x8,  
    IMAGE_CEE_CS_CALLCONV_UNMGD         = 0x9,  
    IMAGE_CEE_CS_CALLCONV_GENERICINST   = 0xa,  
    IMAGE_CEE_CS_CALLCONV_NATIVEVARARG  = 0xb,  
    IMAGE_CEE_CS_CALLCONV_MAX           = 0xc,  
  
    IMAGE_CEE_CS_CALLCONV_MASK          = 0x0f,  
    IMAGE_CEE_CS_CALLCONV_HASTHIS       = 0x20,  
    IMAGE_CEE_CS_CALLCONV_EXPLICITTHIS  = 0x40,  
    IMAGE_CEE_CS_CALLCONV_GENERIC       = 0x10  
  
} CorCallingConvention;  
```  
  
## <a name="members"></a><span data-ttu-id="f2718-105">멤버</span><span class="sxs-lookup"><span data-stu-id="f2718-105">Members</span></span>  
  
|<span data-ttu-id="f2718-106">멤버</span><span class="sxs-lookup"><span data-stu-id="f2718-106">Member</span></span>|<span data-ttu-id="f2718-107">설명</span><span class="sxs-lookup"><span data-stu-id="f2718-107">Description</span></span>|  
|------------|-----------------|  
|`IMAGE_CEE_CS_CALLCONV_DEFAULT`|<span data-ttu-id="f2718-108">기본 호출 규칙을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f2718-108">Indicates a default calling convention.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_VARARG`|<span data-ttu-id="f2718-109">메서드는 가변 개수의 매개 변수를 사용 하며 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f2718-109">Indicates that the method takes a variable number of parameters.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_FIELD`|<span data-ttu-id="f2718-110">통화 필드 임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f2718-110">Indicates that the call is to a field.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_LOCAL_SIG`|<span data-ttu-id="f2718-111">로컬 메서드를 호출 임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f2718-111">Indicates that the call is to a local method.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_PROPERTY`|<span data-ttu-id="f2718-112">호출 되는 속성을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f2718-112">Indicates that the call is to a property.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_UNMGD`|<span data-ttu-id="f2718-113">관리 되지 않는 호출을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f2718-113">Indicates that the call is unmanaged.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_GENERICINST`|<span data-ttu-id="f2718-114">제네릭 메서드 인스턴스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f2718-114">Indicates a generic method instantiation.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_NATIVEVARARG`|<span data-ttu-id="f2718-115">64 비트 PInvoke 호출에 가변 개수의 매개 변수를 사용 하는 메서드를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f2718-115">Indicates a 64-bit PInvoke call to a method that takes a variable number of parameters.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_MAX`|<span data-ttu-id="f2718-116">잘못 된 4 비트 값에 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f2718-116">Describes an invalid 4-bit value.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_MASK`|<span data-ttu-id="f2718-117">호출 규칙으로 하위 4 비트 설명 되어 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f2718-117">Indicates that the calling convention is described by the bottom four bits.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_HASTHIS`|<span data-ttu-id="f2718-118">최상위 비트를 설명 한다는 사실을 나타냅니다는 `this` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="f2718-118">Indicates that the top bit describes a `this` parameter.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_EXPLICITTHIS`|<span data-ttu-id="f2718-119">나타냅니다는 `this` 서명을에서 명시적으로 설명 하는 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="f2718-119">Indicates that a `this` parameter is explicitly described in the signature.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_GENERIC`|<span data-ttu-id="f2718-120">명시적 개수의 형식 인수를 사용 하 여 제네릭 메서드 시그니처를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f2718-120">Indicates a generic method signature with an explicit number of type arguments.</span></span> <span data-ttu-id="f2718-121">이 표준 매개 변수 개수를 앞에 붙습니다.</span><span class="sxs-lookup"><span data-stu-id="f2718-121">This precedes an ordinary parameter count.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f2718-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f2718-122">Requirements</span></span>  
 <span data-ttu-id="f2718-123">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f2718-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2718-124">**헤더:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="f2718-124">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="f2718-125">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2718-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2718-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f2718-126">See Also</span></span>  
 [<span data-ttu-id="f2718-127">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="f2718-127">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
