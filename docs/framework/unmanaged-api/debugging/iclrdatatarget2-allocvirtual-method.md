---
title: ICLRDataTarget2::AllocVirtual 메서드
ms.date: 03/30/2017
api_name:
- ICLRDataTarget2.AllocVirtual
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget2::AllocVirtual
helpviewer_keywords:
- ICLRDataTarget2::AllocVirtual method [.NET Framework debugging]
- AllocVirtual method [.NET Framework debugging]
ms.assetid: e3226230-964b-47fb-9f53-d6fdbeda1e9e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 46532592057f4fa6d9883d46dcef2f8f9e5f7228
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33406346"
---
# <a name="iclrdatatarget2allocvirtual-method"></a><span data-ttu-id="e9b8a-102">ICLRDataTarget2::AllocVirtual 메서드</span><span class="sxs-lookup"><span data-stu-id="e9b8a-102">ICLRDataTarget2::AllocVirtual Method</span></span>
<span data-ttu-id="e9b8a-103">이 대상 프로세스의 주소 공간에 메모리를 할당할는 공용 언어 런타임 (CLR) 데이터 액세스 서비스에서 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e9b8a-103">Called by the common language runtime (CLR) data access services to allocate memory in the address space of this target process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9b8a-104">구문</span><span class="sxs-lookup"><span data-stu-id="e9b8a-104">Syntax</span></span>  
  
```  
HRESULT AllocVirtual(  
    [in] CLRDATA_ADDRESS addr,  
    [in] ULONG32 size,  
    [in] ULONG32 typeFlags,  
    [in] ULONG32 protectFlags,  
    [out] CLRDATA_ADDRESS* virt  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e9b8a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e9b8a-105">Parameters</span></span>  
 `addr`  
 <span data-ttu-id="e9b8a-106">[in] A `CLRDATA_ADDRESS` 할당할 메모리의 요청 된 시작 주소를 지정 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="e9b8a-106">[in] A `CLRDATA_ADDRESS` value that specifies the requested starting address of the memory to be allocated.</span></span>  
  
 `size`  
 <span data-ttu-id="e9b8a-107">[in] 에 할당할 메모리의 바이트 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="e9b8a-107">[in] The size, in bytes, of the memory to be allocated.</span></span>  
  
 `typeFlags`  
 <span data-ttu-id="e9b8a-108">[in] 메모리의 할당을 제어 하는 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="e9b8a-108">[in] Flags that control the allocation of memory.</span></span> <span data-ttu-id="e9b8a-109">Win32 참조 `VirtualAlloc` 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="e9b8a-109">See the Win32 `VirtualAlloc` function.</span></span>  
  
 `protectFlags`  
 <span data-ttu-id="e9b8a-110">[in] 할당된 된 메모리에 대 한 보호 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="e9b8a-110">[in] The protection attributes for the allocated memory.</span></span> <span data-ttu-id="e9b8a-111">Win32 참조 `VirtualAlloc` 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="e9b8a-111">See the Win32 `VirtualAlloc` function.</span></span>  
  
 `virt`  
 <span data-ttu-id="e9b8a-112">[out] 에 대 한 포인터는 `CLRDATA_ADDRESS` 할당된 된 메모리의 실제 시작 주소를 지정 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="e9b8a-112">[out] A pointer to a `CLRDATA_ADDRESS` value that specifies the actual starting address of the allocated memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e9b8a-113">설명</span><span class="sxs-lookup"><span data-stu-id="e9b8a-113">Remarks</span></span>  
 <span data-ttu-id="e9b8a-114">`AllocVirtual` 메서드 래퍼 역할을 논리는 win32 `VirtualAlloc` 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="e9b8a-114">The `AllocVirtual` method serves as a logical wrapper for the Win32 `VirtualAlloc` function.</span></span>  
  
 <span data-ttu-id="e9b8a-115">이 메서드는 디버깅 응용 프로그램의 작성자가 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="e9b8a-115">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9b8a-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e9b8a-116">Requirements</span></span>  
 <span data-ttu-id="e9b8a-117">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e9b8a-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9b8a-118">**헤더:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="e9b8a-118">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="e9b8a-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e9b8a-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e9b8a-120">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9b8a-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9b8a-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e9b8a-121">See Also</span></span>  
 [<span data-ttu-id="e9b8a-122">ICLRDataTarget2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e9b8a-122">ICLRDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md)  
 [<span data-ttu-id="e9b8a-123">FreeVirtual 메서드</span><span class="sxs-lookup"><span data-stu-id="e9b8a-123">FreeVirtual Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-freevirtual-method.md)
