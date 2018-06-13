---
title: ICLRDataTarget::WriteVirtual 메서드
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.WriteVirtual
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::WriteVirtual
helpviewer_keywords:
- ICLRDataTarget::WriteVirtual method [.NET Framework debugging]
- WriteVirtual method [.NET Framework debugging]
ms.assetid: d627e8b7-a605-40ac-b9bb-da9a3f1b66d9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e55bc18c7a41e235d1ba6274067c45c26dc7262a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33405460"
---
# <a name="iclrdatatargetwritevirtual-method"></a><span data-ttu-id="a33fe-102">ICLRDataTarget::WriteVirtual 메서드</span><span class="sxs-lookup"><span data-stu-id="a33fe-102">ICLRDataTarget::WriteVirtual Method</span></span>
<span data-ttu-id="a33fe-103">지정 된 가상 메모리 주소에 지정된 된 버퍼에서 데이터를 씁니다.</span><span class="sxs-lookup"><span data-stu-id="a33fe-103">Writes data from the specified buffer to the specified virtual memory address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a33fe-104">구문</span><span class="sxs-lookup"><span data-stu-id="a33fe-104">Syntax</span></span>  
  
```  
HRESULT WriteVirtual (  
    [in] CLRDATA_ADDRESS    address,  
    [in, size_is(bytesRequested)]   
        BYTE                *buffer,  
    [in] ULONG32            bytesRequested,  
    [out] ULONG32           *bytesWritten  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a33fe-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a33fe-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="a33fe-106">[in] 가상 메모리 주소를 저장 하는 CLRDATA_ADDRESS 합니다.</span><span class="sxs-lookup"><span data-stu-id="a33fe-106">[in] A CLRDATA_ADDRESS that stores the virtual memory address.</span></span>  
  
 `buffer`  
 <span data-ttu-id="a33fe-107">[in] 쓸 데이터를 저장 하는 버퍼에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a33fe-107">[in] A pointer to a buffer that stores the data to be written.</span></span>  
  
 `bytesRequested`  
 <span data-ttu-id="a33fe-108">[in] 쓸 바이트 수의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="a33fe-108">[in] The number of bytes to be written.</span></span>  
  
 `bytesWritten`  
 <span data-ttu-id="a33fe-109">[out] 실제 쓴 바이트 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a33fe-109">[out] A pointer to the actual number of bytes that were written.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a33fe-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a33fe-110">Requirements</span></span>  
 <span data-ttu-id="a33fe-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a33fe-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a33fe-112">**헤더:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="a33fe-112">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="a33fe-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a33fe-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a33fe-114">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a33fe-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a33fe-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a33fe-115">See Also</span></span>  
 [<span data-ttu-id="a33fe-116">ICLRDataTarget 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a33fe-116">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
