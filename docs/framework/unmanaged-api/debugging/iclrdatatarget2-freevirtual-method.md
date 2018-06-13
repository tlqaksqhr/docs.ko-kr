---
title: ICLRDataTarget2::FreeVirtual 메서드
ms.date: 03/30/2017
api_name:
- ICLRDataTarget2.FreeVirtual
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget2::FreeVirtual
helpviewer_keywords:
- ICLRDataTarget::FreeVirtual method [.NET Framework debugging]
- FreeVirtual method [.NET Framework debugging]
ms.assetid: 26fb69f8-1467-4711-bd24-cb117c63938f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e7351dfb046653e4f3e20e0dc8a4bba8653ec36e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33404650"
---
# <a name="iclrdatatarget2freevirtual-method"></a><span data-ttu-id="9410e-102">ICLRDataTarget2::FreeVirtual 메서드</span><span class="sxs-lookup"><span data-stu-id="9410e-102">ICLRDataTarget2::FreeVirtual Method</span></span>
<span data-ttu-id="9410e-103">대상 프로세스의 주소 공간에서 이전에 할당 된 메모리를 확보는 공용 언어 런타임 (CLR) 데이터 액세스 서비스에서 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9410e-103">Called by the common language runtime (CLR) data access services to free memory that was previously allocated in the address space of the target process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9410e-104">구문</span><span class="sxs-lookup"><span data-stu-id="9410e-104">Syntax</span></span>  
  
```  
HRESULT FreeVirtual(  
    [in] CLRDATA_ADDRESS addr,  
    [in] ULONG32 size,  
    [in] ULONG32 typeFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9410e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9410e-105">Parameters</span></span>  
 `addr`  
 <span data-ttu-id="9410e-106">[in] A `CLRDATA_ADDRESS` 해제할 메모리의 시작 주소를 지정 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="9410e-106">[in] A `CLRDATA_ADDRESS` value that specifies the starting address of the memory to be freed.</span></span>  
  
 `size`  
 <span data-ttu-id="9410e-107">[in] 해제할 메모리를 바이트 단위로 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="9410e-107">[in] The size, in bytes, of the memory to be freed.</span></span>  
  
 `typeFlags`  
 <span data-ttu-id="9410e-108">[in] 메모리 해제를 제어 하는 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="9410e-108">[in] Flags that control the freeing of memory.</span></span> <span data-ttu-id="9410e-109">Win32 참조 `VirtualFree` 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="9410e-109">See the Win32 `VirtualFree` function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9410e-110">설명</span><span class="sxs-lookup"><span data-stu-id="9410e-110">Remarks</span></span>  
 <span data-ttu-id="9410e-111">`FreeVirtual` 메서드 래퍼 역할을 논리는 win32 `VirtualFree` 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="9410e-111">The `FreeVirtual` method serves as a logical wrapper for the Win32 `VirtualFree` function.</span></span>  
  
 <span data-ttu-id="9410e-112">이 메서드는 디버깅 응용 프로그램의 작성자가 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="9410e-112">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9410e-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9410e-113">Requirements</span></span>  
 <span data-ttu-id="9410e-114">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9410e-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9410e-115">**헤더:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="9410e-115">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="9410e-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9410e-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9410e-117">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9410e-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9410e-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9410e-118">See Also</span></span>  
 [<span data-ttu-id="9410e-119">ICLRDataTarget2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9410e-119">ICLRDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md)  
 [<span data-ttu-id="9410e-120">AllocVirtual 메서드</span><span class="sxs-lookup"><span data-stu-id="9410e-120">AllocVirtual Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-allocvirtual-method.md)
