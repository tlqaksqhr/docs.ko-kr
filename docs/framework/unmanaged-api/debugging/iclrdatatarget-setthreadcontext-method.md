---
title: ICLRDataTarget::SetThreadContext 메서드
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.SetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::SetThreadContext
helpviewer_keywords:
- SetThreadContext method, ICLRDataTarget interface [.NET Framework debugging]
- ICLRDataTarget::SetThreadContext method [.NET Framework debugging]
ms.assetid: 103c8502-81fe-40d7-9c1e-9008d8fb19e1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 73697fdd19f2492aabdc0d76e8c1a27c917c85f1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33405540"
---
# <a name="iclrdatatargetsetthreadcontext-method"></a><span data-ttu-id="c456c-102">ICLRDataTarget::SetThreadContext 메서드</span><span class="sxs-lookup"><span data-stu-id="c456c-102">ICLRDataTarget::SetThreadContext Method</span></span>
<span data-ttu-id="c456c-103">대상 프로세스에서 지정 된 스레드의 현재 컨텍스트를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c456c-103">Sets the current context of the specified thread in the target process.</span></span> <span data-ttu-id="c456c-104">이 메서드는 공용 언어 런타임 (CLR) 데이터 액세스 서비스에 의해 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c456c-104">This method is called by the common language runtime (CLR) data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c456c-105">구문</span><span class="sxs-lookup"><span data-stu-id="c456c-105">Syntax</span></span>  
  
```  
HRESULT SetThreadContext (  
    [in] ULONG32            threadID,  
    [in] ULONG32            contextSize,  
    [in, size_is(contextSize)]   
         BYTE               *context  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c456c-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c456c-106">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="c456c-107">[in] 대상 프로세스에서 스레드의 운영 체제 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="c456c-107">[in] The operating system identifier of a thread in the target process.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="c456c-108">[in] 컨텍스트 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="c456c-108">[in] The size of the context.</span></span>  
  
 `context`  
 <span data-ttu-id="c456c-109">[in] 컨텍스트를 포함 하는 버퍼에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c456c-109">[in] Pointer to a buffer containing the context.</span></span>  
  
 <span data-ttu-id="c456c-110">데이터는 `context` 버퍼 Win32 형식에 포함 될 `CONTEXT` 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="c456c-110">The data in the `context` buffer will be in the format of the Win32 `CONTEXT` structure.</span></span> <span data-ttu-id="c456c-111">컨텍스트 프로세스별 등록 데이터를 지정 하므로 Win32 정의 `CONTEXT` 구조는 프로세서 아키텍처에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="c456c-111">The context specifies processor-specific register data, so the definition of the Win32 `CONTEXT` structure depends on the processor's architecture.</span></span> <span data-ttu-id="c456c-112">Win32 정의 대 한 WinNT.h 헤더 파일을 참조 `CONTEXT` 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="c456c-112">Refer to the WinNT.h header file for the definition of the Win32 `CONTEXT` structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c456c-113">설명</span><span class="sxs-lookup"><span data-stu-id="c456c-113">Remarks</span></span>  
 <span data-ttu-id="c456c-114">이 메서드는 디버깅 응용 프로그램의 작성자가 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="c456c-114">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c456c-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c456c-115">Requirements</span></span>  
 <span data-ttu-id="c456c-116">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c456c-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c456c-117">**헤더:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="c456c-117">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="c456c-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c456c-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c456c-119">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c456c-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c456c-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c456c-120">See Also</span></span>  
 [<span data-ttu-id="c456c-121">ICLRDataTarget 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c456c-121">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
