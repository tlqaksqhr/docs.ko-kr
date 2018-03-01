---
title: "ICLRDataTarget::GetTLSValue 메서드"
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
- ICLRDataTarget.GetTLSValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::GetTLSValue
helpviewer_keywords:
- GetTLSValue method [.NET Framework debugging]
- ICLRDataTarget::GetTLSValue method [.NET Framework debugging]
ms.assetid: 0d8a7730-edc9-4728-898f-41b219cf5a28
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ab3d978e9500a17f5b8ae011322ad05aedddf98b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="iclrdatatargetgettlsvalue-method"></a><span data-ttu-id="4607b-102">ICLRDataTarget::GetTLSValue 메서드</span><span class="sxs-lookup"><span data-stu-id="4607b-102">ICLRDataTarget::GetTLSValue Method</span></span>
<span data-ttu-id="4607b-103">대상 프로세스에서 지정 된 스레드의 스레드 로컬 저장소 (TLS)에서 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="4607b-103">Gets a value from the thread local storage (TLS) of the specified thread in the target process.</span></span> <span data-ttu-id="4607b-104">이 메서드는 공용 언어 런타임 (CLR) 데이터 액세스 서비스에 의해 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4607b-104">This method is called by the common language runtime (CLR) data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4607b-105">구문</span><span class="sxs-lookup"><span data-stu-id="4607b-105">Syntax</span></span>  
  
```  
HRESULT GetTLSValue (  
    [in] ULONG32            threadID,  
    [in] ULONG32            index,  
    [out] CLRDATA_ADDRESS   *value  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4607b-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4607b-106">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="4607b-107">[in] 대상 프로세스에서 스레드의 운영 체제 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="4607b-107">[in] The operating system identifier of a thread in the target process.</span></span>  
  
 `index`  
 <span data-ttu-id="4607b-108">[in] 인덱스 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="4607b-108">[in] The index of the location.</span></span> <span data-ttu-id="4607b-109">이 값은 지정 된 스레드 로컬 저장소의 유효한 인덱스가 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4607b-109">This value must be a valid index in the local store of the specified thread.</span></span>  
  
 `value`  
 <span data-ttu-id="4607b-110">[out] 에 대 한 포인터는 `CLRDATA_ADDRESS` 지정된 TLS 위치에서 반환 된 값을 지정 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="4607b-110">[out] A pointer to a `CLRDATA_ADDRESS` value that specifies the value returned from the given TLS location.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4607b-111">설명</span><span class="sxs-lookup"><span data-stu-id="4607b-111">Remarks</span></span>  
 <span data-ttu-id="4607b-112">이 메서드는 디버깅 응용 프로그램의 작성자가 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="4607b-112">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4607b-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4607b-113">Requirements</span></span>  
 <span data-ttu-id="4607b-114">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4607b-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4607b-115">**헤더:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="4607b-115">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="4607b-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4607b-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4607b-117">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4607b-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4607b-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4607b-118">See Also</span></span>  
 [<span data-ttu-id="4607b-119">ICLRDataTarget 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4607b-119">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
