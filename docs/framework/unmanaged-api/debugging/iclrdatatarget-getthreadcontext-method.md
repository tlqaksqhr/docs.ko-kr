---
title: "ICLRDataTarget::GetThreadContext 메서드"
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
- ICLRDataTarget.GetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::GetThreadContext
helpviewer_keywords:
- ICLRDataTarget::GetThreadContext method [.NET Framework debugging]
- GetThreadContext method, ICLRDataTarget interface [.NET Framework debugging]
ms.assetid: b9d8c3b5-3a2e-4225-95d4-dd052c4532c3
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5b03af2f1b1fb851ebc08c23827f59eed9153f19
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="iclrdatatargetgetthreadcontext-method"></a><span data-ttu-id="466b5-102">ICLRDataTarget::GetThreadContext 메서드</span><span class="sxs-lookup"><span data-stu-id="466b5-102">ICLRDataTarget::GetThreadContext Method</span></span>
<span data-ttu-id="466b5-103">대상 프로세스에서 지정 된 스레드의 현재 실행 컨텍스트를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="466b5-103">Gets the current execution context for the given thread in the target process.</span></span> <span data-ttu-id="466b5-104">이 메서드는 공용 언어 런타임 데이터 액세스 서비스에 의해 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="466b5-104">This method is called by the common language runtime data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="466b5-105">구문</span><span class="sxs-lookup"><span data-stu-id="466b5-105">Syntax</span></span>  
  
```  
HRESULT GetThreadContext (  
    [in] ULONG32            threadID,  
    [in] ULONG32            contextFlags,  
    [in] ULONG32            contextSize,  
    [out, size_is(contextSize)]   
        BYTE                *context  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="466b5-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="466b5-106">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="466b5-107">[in] 대상 프로세스에서 스레드의 운영 체제 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="466b5-107">[in] The operating system identifier of a thread in the target process.</span></span>  
  
 `contextFlags`  
 <span data-ttu-id="466b5-108">[in] 반환할 컨텍스트 부분을 지정 하는 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="466b5-108">[in] Flags that specify which parts of the context to return.</span></span> <span data-ttu-id="466b5-109">구현에는 최소한 이러한 컨텍스트 부분을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="466b5-109">The implementation will return at least these parts of the context.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="466b5-110">[in] 컨텍스트 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="466b5-110">[in] The size of the context.</span></span>  
  
 `context`  
 <span data-ttu-id="466b5-111">[out] 컨텍스트를 버퍼에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="466b5-111">[out] Pointer to a buffer in which to place the context.</span></span>  
  
 <span data-ttu-id="466b5-112">데이터는 `context` 버퍼에서 win32 형식 이어야 합니다 `CONTEXT` 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="466b5-112">The data in the `context` buffer must be in the format of the Win32 `CONTEXT` structure.</span></span> <span data-ttu-id="466b5-113">컨텍스트 프로세스별 등록 데이터를 지정 하므로 Win32 정의 `CONTEXT` 구조는 프로세서 아키텍처에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="466b5-113">The context specifies processor-specific register data, so the definition of the Win32 `CONTEXT` structure depends on the processor's architecture.</span></span> <span data-ttu-id="466b5-114">Win32 정의 대 한 WinNT.h 헤더 파일을 참조 `CONTEXT` 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="466b5-114">Refer to the WinNT.h header file for the definition of the Win32 `CONTEXT` structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="466b5-115">설명</span><span class="sxs-lookup"><span data-stu-id="466b5-115">Remarks</span></span>  
 <span data-ttu-id="466b5-116">이 메서드는 디버깅 응용 프로그램의 작성자가 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="466b5-116">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="466b5-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="466b5-117">Requirements</span></span>  
 <span data-ttu-id="466b5-118">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="466b5-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="466b5-119">**헤더:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="466b5-119">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="466b5-120">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="466b5-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="466b5-121">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="466b5-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="466b5-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="466b5-122">See Also</span></span>  
 [<span data-ttu-id="466b5-123">ICLRDataTarget 인터페이스</span><span class="sxs-lookup"><span data-stu-id="466b5-123">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
