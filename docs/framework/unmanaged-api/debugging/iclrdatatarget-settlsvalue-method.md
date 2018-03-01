---
title: "ICLRDataTarget::SetTLSValue 메서드"
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
- ICLRDataTarget.SetTLSValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::SetTLSValue
helpviewer_keywords:
- ICLRDataTarget::SetTLSValue method [.NET Framework debugging]
- SetTLSValue method [.NET Framework debugging]
ms.assetid: 4a2d6a24-749a-47ad-9f01-4517203d3f35
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4d63f20c3a5c90fab2347ea56a8adedc6b8dc5e0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="iclrdatatargetsettlsvalue-method"></a><span data-ttu-id="090e8-102">ICLRDataTarget::SetTLSValue 메서드</span><span class="sxs-lookup"><span data-stu-id="090e8-102">ICLRDataTarget::SetTLSValue Method</span></span>
<span data-ttu-id="090e8-103">대상 프로세스에서 지정 된 스레드의 스레드 로컬 저장소 (TLS)에 값을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="090e8-103">Sets a value in the thread local storage (TLS) of the specified thread in the target process.</span></span> <span data-ttu-id="090e8-104">이 메서드는 공용 언어 런타임 (CLR) 데이터 액세스 서비스에 의해 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="090e8-104">This method is called by the common language runtime (CLR) data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="090e8-105">구문</span><span class="sxs-lookup"><span data-stu-id="090e8-105">Syntax</span></span>  
  
```  
HRESULT SetTLSValue (  
    [in] ULONG32            threadID,  
    [in] ULONG32            index,  
    [in] CLRDATA_ADDRESS    value  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="090e8-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="090e8-106">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="090e8-107">[in] 대상 프로세스에서 스레드의 운영 체제 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="090e8-107">[in] The operating system identifier of a thread in the target process.</span></span>  
  
 `index`  
 <span data-ttu-id="090e8-108">[in] 인덱스 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="090e8-108">[in] The index of the location.</span></span> <span data-ttu-id="090e8-109">이 값은 지정 된 스레드 로컬 저장소의 유효한 인덱스가 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="090e8-109">This value must be a valid index in the local store of the specified thread.</span></span>  
  
 `value`  
 <span data-ttu-id="090e8-110">[in] A `CLRDATA_ADDRESS` 주어진된 TLS 위치에 배치 하는 값을 지정 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="090e8-110">[in] A `CLRDATA_ADDRESS` value that specifies the value to place in the given TLS location.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="090e8-111">설명</span><span class="sxs-lookup"><span data-stu-id="090e8-111">Remarks</span></span>  
 <span data-ttu-id="090e8-112">이 메서드는 디버깅 응용 프로그램의 작성자가 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="090e8-112">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="090e8-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="090e8-113">Requirements</span></span>  
 <span data-ttu-id="090e8-114">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="090e8-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="090e8-115">**헤더:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="090e8-115">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="090e8-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="090e8-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="090e8-117">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="090e8-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="090e8-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="090e8-118">See Also</span></span>  
 [<span data-ttu-id="090e8-119">ICLRDataTarget 인터페이스</span><span class="sxs-lookup"><span data-stu-id="090e8-119">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
