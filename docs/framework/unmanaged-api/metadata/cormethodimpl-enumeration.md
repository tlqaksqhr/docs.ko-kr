---
title: "CorMethodImpl 열거형"
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
- CorMethodImpl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorMethodImpl
helpviewer_keywords:
- CorMethodImpl enumeration [.NET Framework metadata]
ms.assetid: ffbb3caf-20da-4a4b-8983-77376e72b990
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e82eb50e4850ffbb4d5fc67d9603a3128cf8bcf6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="cormethodimpl-enumeration"></a><span data-ttu-id="99a99-102">CorMethodImpl 열거형</span><span class="sxs-lookup"><span data-stu-id="99a99-102">CorMethodImpl Enumeration</span></span>
<span data-ttu-id="99a99-103">메서드 구현 기능을 설명하는 값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="99a99-103">Contains values that describe method implementation features.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99a99-104">구문</span><span class="sxs-lookup"><span data-stu-id="99a99-104">Syntax</span></span>  
  
```  
typedef enum CorMethodImpl {  
  
    miCodeTypeMask      =   0x0003,  
    miIL                =   0x0000,  
    miNative            =   0x0001,  
    miOPTIL             =   0x0002,  
    miRuntime           =   0x0003,  
  
    miManagedMask       =   0x0004,  
    miUnmanaged         =   0x0004,  
    miManaged           =   0x0000,  
  
    miForwardRef        =   0x0010,  
    miPreserveSig       =   0x0080,  
  
    miInternalCall      =   0x1000,  
    miSynchronized      =   0x0020,  
    miNoInlining        =   0x0008,  
    miAggressiveInlining =  0x0100,  
    miNoOptimization     =  0x0040,  
    miMaxMethodImplVal  =   0xffff  
  
} CorMethodImpl;  
```  
  
## <a name="members"></a><span data-ttu-id="99a99-105">멤버</span><span class="sxs-lookup"><span data-stu-id="99a99-105">Members</span></span>  
  
|<span data-ttu-id="99a99-106">멤버</span><span class="sxs-lookup"><span data-stu-id="99a99-106">Member</span></span>|<span data-ttu-id="99a99-107">설명</span><span class="sxs-lookup"><span data-stu-id="99a99-107">Description</span></span>|  
|------------|-----------------|  
|`miCodeTypeMask`|<span data-ttu-id="99a99-108">코드 형식을 설명 하는 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="99a99-108">Flags that describe code type.</span></span>|  
|`miIL`|<span data-ttu-id="99a99-109">메서드 구현 Microsoft MSIL (intermediate language) 임을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="99a99-109">Specifies that the method implementation is Microsoft intermediate language (MSIL).</span></span>|  
|`miNative`|<span data-ttu-id="99a99-110">메서드 구현이 네이티브임을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="99a99-110">Specifies that the method implementation is native.</span></span>|  
|`miOPTIL`|<span data-ttu-id="99a99-111">메서드 구현 optil로 임을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="99a99-111">Specifies that the method implementation is OPTIL.</span></span>|  
|`miRuntime`|<span data-ttu-id="99a99-112">공용 언어 런타임에 의해 메서드 구현을 제공 되도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="99a99-112">Specifies that the method implementation is provided by the common language runtime.</span></span>|  
|`miManagedMask`|<span data-ttu-id="99a99-113">코드 관리 여부를 나타내는 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="99a99-113">Flags that indicate whether the code is managed or unmanaged.</span></span>|  
|`miUnmanaged`|<span data-ttu-id="99a99-114">메서드 구현 관리 되는 임을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="99a99-114">Specifies that the method implementation is unmanaged.</span></span>|  
|`miManaged`|<span data-ttu-id="99a99-115">메서드 구현 관리 되 고 있는지를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="99a99-115">Specifies that the method implementation is managed.</span></span>|  
|`miForwardRef`|<span data-ttu-id="99a99-116">메서드가 정의 된 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="99a99-116">Specifies that the method is defined.</span></span> <span data-ttu-id="99a99-117">이 플래그는 병합 시나리오에 주로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="99a99-117">This flag is used primarily in merge scenarios.</span></span>|  
|`miPreserveSig`|<span data-ttu-id="99a99-118">HRESULT 변환에 대 한 메서드 시그니처를 변환 될 수 없는 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="99a99-118">Specifies that the method signature cannot be mangled for an HRESULT conversion.</span></span>|  
|`miInternalCall`|<span data-ttu-id="99a99-119">공용 언어 런타임에서 내부 용도로 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99a99-119">Reserved for internal use by the common language runtime.</span></span>|  
|`miSynchronized`|<span data-ttu-id="99a99-120">메서드 본문을 통해 단일 스레드 임을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="99a99-120">Specifies that the method is single-threaded through its body.</span></span>|  
|`miNoInlining`|<span data-ttu-id="99a99-121">메서드를 인라인될 수 없도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="99a99-121">Specifies that the method cannot be inlined.</span></span>|  
|`miAggressiveInlining`|<span data-ttu-id="99a99-122">이어야 함을 지정 메서드가 하지 인라인 처리 가능한 경우.</span><span class="sxs-lookup"><span data-stu-id="99a99-122">Specifies that the method should be inlined if possible.</span></span>|  
|`miNoOptimization`|<span data-ttu-id="99a99-123">메서드를 최적화 되지 않도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="99a99-123">Specifies that the method should not be optimized.</span></span>|  
|`miMaxMethodImplVal`|<span data-ttu-id="99a99-124">에 대 한 최대 유효 값은 `CorMethodImpl`합니다.</span><span class="sxs-lookup"><span data-stu-id="99a99-124">The maximum valid value for a `CorMethodImpl`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="99a99-125">요구 사항</span><span class="sxs-lookup"><span data-stu-id="99a99-125">Requirements</span></span>  
 <span data-ttu-id="99a99-126">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="99a99-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99a99-127">**헤더:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="99a99-127">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="99a99-128">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="99a99-128">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99a99-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="99a99-129">See Also</span></span>  
 [<span data-ttu-id="99a99-130">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="99a99-130">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
