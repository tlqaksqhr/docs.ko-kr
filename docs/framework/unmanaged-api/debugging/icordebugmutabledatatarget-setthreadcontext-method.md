---
title: ICorDebugMutableDataTarget::SetThreadContext 메서드
ms.date: 03/30/2017
ms.assetid: 8c0d01d5-67e5-4522-9ccf-c8f3a78cb4fd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 05f0c0d23b4885f2d6fd351fdf845a25c899228e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33418420"
---
# <a name="icordebugmutabledatatargetsetthreadcontext-method"></a><span data-ttu-id="d1350-102">ICorDebugMutableDataTarget::SetThreadContext 메서드</span><span class="sxs-lookup"><span data-stu-id="d1350-102">ICorDebugMutableDataTarget::SetThreadContext Method</span></span>
<span data-ttu-id="d1350-103">스레드에 대한 컨텍스트(레지스터 값)를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d1350-103">Sets the context (register values) for a thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1350-104">구문</span><span class="sxs-lookup"><span data-stu-id="d1350-104">Syntax</span></span>  
  
```  
HRESULT SetThreadContext(  
   [in] DWORD dwThreadID,  
   [in] ULONG32 contextSize,   [in, size_is(contextSize)] const BYTE * pContext);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d1350-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d1350-105">Parameters</span></span>  
 `dwThreadID`  
 <span data-ttu-id="d1350-106">[in] 운영 체제에서 정의된 스레드 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="d1350-106">[in] The operating system-defined thread identifier.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="d1350-107">[in] 쓸 `pContext` 버퍼의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="d1350-107">[in] The size of the `pContext` buffer to be written.</span></span>  
  
 `pContext`  
 <span data-ttu-id="d1350-108">[in] 쓸 바이트에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d1350-108">[in] A pointer to the bytes to be written.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d1350-109">설명</span><span class="sxs-lookup"><span data-stu-id="d1350-109">Remarks</span></span>  
 <span data-ttu-id="d1350-110">`SetThreadContext` 메서드는 운영 체제에서 정의된 `dwThreadID` 인수로 지정된 스레드에 대한 현재 컨텍스트를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="d1350-110">The `SetThreadContext` method updates the current context for the thread specified by the operating system-defined `dwThreadID` argument.</span></span> <span data-ttu-id="d1350-111">컨텍스트 레코드의 형식으로 표시 되는 플랫폼 따라 사용자가 [icordebugdatatarget:: Getplatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="d1350-111">The format of the context record is determined by the platform indicated by the [ICorDebugDataTarget::GetPlatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) method.</span></span> <span data-ttu-id="d1350-112">이 windows에서 [컨텍스트](http://msdn.microsoft.com/library/windows/desktop/ms679284.aspx) 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="d1350-112">On Windows, this is a [CONTEXT](http://msdn.microsoft.com/library/windows/desktop/ms679284.aspx) structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d1350-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d1350-113">Requirements</span></span>  
 <span data-ttu-id="d1350-114">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d1350-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d1350-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d1350-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d1350-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d1350-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d1350-117">**.NET framework 버전:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d1350-117">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1350-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d1350-118">See Also</span></span>  
 [<span data-ttu-id="d1350-119">ICorDebugMutableDataTarget 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d1350-119">ICorDebugMutableDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmutabledatatarget-interface.md)  
 [<span data-ttu-id="d1350-120">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d1350-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
