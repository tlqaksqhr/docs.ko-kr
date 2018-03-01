---
title: "ICLRDataTarget::GetCurrentThreadID 메서드"
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
- ICLRDataTarget.GetCurrentThreadID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::GetCurrentThreadID
helpviewer_keywords:
- GetCurrentThreadID method, ICLRDataTarget interface [.NET Framework debugging]
- ICLRDataTarget::GetCurrentThreadID method [.NET Framework debugging]
ms.assetid: dc9a0a6c-d592-4fb7-86ed-62684da3b0e1
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2fd2c39b20b823e18232081d1655a6770bafccc5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="iclrdatatargetgetcurrentthreadid-method"></a><span data-ttu-id="1caaf-102">ICLRDataTarget::GetCurrentThreadID 메서드</span><span class="sxs-lookup"><span data-stu-id="1caaf-102">ICLRDataTarget::GetCurrentThreadID Method</span></span>
<span data-ttu-id="1caaf-103">현재 스레드에 대 한 운영 체제 식별자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1caaf-103">Gets the operating system identifier for the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1caaf-104">구문</span><span class="sxs-lookup"><span data-stu-id="1caaf-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentThreadID (  
    [out] ULONG32    *threadID  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1caaf-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1caaf-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="1caaf-106">[out] 대상 프로세스에 대 한 현재 스레드의 운영 체제 식별자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="1caaf-106">[out] A pointer to the operating system identifier of the current thread for the target process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1caaf-107">설명</span><span class="sxs-lookup"><span data-stu-id="1caaf-107">Remarks</span></span>  
 <span data-ttu-id="1caaf-108">대상 프로세스에 대 한 현재 스레드가 없는 경우는 `GetCurrentThreadID` 메서드가 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1caaf-108">If there is no current thread for the target process, the `GetCurrentThreadID` method may fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1caaf-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1caaf-109">Requirements</span></span>  
 <span data-ttu-id="1caaf-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1caaf-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1caaf-111">**헤더:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="1caaf-111">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="1caaf-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1caaf-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1caaf-113">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1caaf-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1caaf-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1caaf-114">See Also</span></span>  
 [<span data-ttu-id="1caaf-115">ICLRDataTarget 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1caaf-115">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
