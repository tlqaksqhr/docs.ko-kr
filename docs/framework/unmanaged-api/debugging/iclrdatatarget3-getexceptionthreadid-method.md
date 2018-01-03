---
title: "ICLRDataTarget3::GetExceptionThreadID 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: cpp
api_name: ICLRDataTarget3.GetExceptionThreadID
api_location: mscordbi.dll
api_type: COM
ms.assetid: 307d6ac7-4a86-45f3-999d-6b47004a68f2
topic_type: apiref
caps.latest.revision: "3"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0f8b2e7c764eb5d7694633be7fb095b3d19be6e2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="iclrdatatarget3getexceptionthreadid-method"></a><span data-ttu-id="329b7-102">ICLRDataTarget3::GetExceptionThreadID 메서드</span><span class="sxs-lookup"><span data-stu-id="329b7-102">ICLRDataTarget3::GetExceptionThreadID Method</span></span>
<span data-ttu-id="329b7-103">CLR(공용 언어 런타임) 데이터 액세스 서비스에 의해 호출되어 예외를 throw한 스레드의 ID를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="329b7-103">Called by the common language runtime (CLR) data access services to get the ID of the thread that threw the exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="329b7-104">구문</span><span class="sxs-lookup"><span data-stu-id="329b7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetExceptionThreadID(  
    [out] ULONG32* threadID  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="329b7-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="329b7-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="329b7-106">[out] 예외를 throw한 스레드의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="329b7-106">[out] The ID of the thread that threw the exception.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="329b7-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="329b7-107">Return Value</span></span>  
 <span data-ttu-id="329b7-108">반환 값은 성공 시 `S_OK`이고 실패 시에는 오류 `HRESULT` 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="329b7-108">The return value is `S_OK` on success, or a failure `HRESULT` code on failure.</span></span> <span data-ttu-id="329b7-109">`HRESULT` 코드는 다음을 비롯한 여러 항목을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="329b7-109">The `HRESULT` codes can include but are not limited to the following:</span></span>  
  
|<span data-ttu-id="329b7-110">반환 코드</span><span class="sxs-lookup"><span data-stu-id="329b7-110">Return code</span></span>|<span data-ttu-id="329b7-111">설명</span><span class="sxs-lookup"><span data-stu-id="329b7-111">Description</span></span>|  
|-----------------|-----------------|  
|`S_OK`|<span data-ttu-id="329b7-112">메서드가 정상적으로 실행되었습니다.</span><span class="sxs-lookup"><span data-stu-id="329b7-112">Method succeeded.</span></span>|  
|`HRESULT_FROM_WIN32(ERROR_NOT_FOUND)`|<span data-ttu-id="329b7-113">예외의 유효한 스레드 ID를 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="329b7-113">Could not find a valid thread ID for the exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="329b7-114">설명</span><span class="sxs-lookup"><span data-stu-id="329b7-114">Remarks</span></span>  
 <span data-ttu-id="329b7-115">이 메서드는 디버깅 응용 프로그램의 작성자가 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="329b7-115">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="329b7-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="329b7-116">Requirements</span></span>  
 <span data-ttu-id="329b7-117">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="329b7-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="329b7-118">**헤더:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="329b7-118">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="329b7-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="329b7-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="329b7-120">**.NET framework 버전:**[!INCLUDE[v451_update](../../../../includes/v451-update-md.md)]</span><span class="sxs-lookup"><span data-stu-id="329b7-120">**.NET Framework Versions:** [!INCLUDE[v451_update](../../../../includes/v451-update-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="329b7-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="329b7-121">See Also</span></span>  
 [<span data-ttu-id="329b7-122">ICLRDataTarget3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="329b7-122">ICLRDataTarget3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-interface.md)  
 [<span data-ttu-id="329b7-123">GetExceptionContextRecord 메서드</span><span class="sxs-lookup"><span data-stu-id="329b7-123">GetExceptionContextRecord Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptioncontextrecord-method.md)  
 [<span data-ttu-id="329b7-124">GetExceptionRecord 메서드</span><span class="sxs-lookup"><span data-stu-id="329b7-124">GetExceptionRecord Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptionrecord-method.md)
