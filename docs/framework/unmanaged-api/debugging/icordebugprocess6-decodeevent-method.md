---
title: "ICorDebugProcess6::DecodeEvent 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 1453bc0c-6e0d-4d5a-b176-22607f8a3e6c
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 753dce06d9481165bd2f0f1e49fe3c50fc6b3c40
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocess6decodeevent-method"></a><span data-ttu-id="d6f2b-102">ICorDebugProcess6::DecodeEvent 메서드</span><span class="sxs-lookup"><span data-stu-id="d6f2b-102">ICorDebugProcess6::DecodeEvent Method</span></span>
<span data-ttu-id="d6f2b-103">특수하게 작성된 네이티브 예외 디버그 이벤트의 페이로드에서 캡슐화된 관리되는 디버그 이벤트를 디코딩합니다.</span><span class="sxs-lookup"><span data-stu-id="d6f2b-103">Decodes managed debug events that have been encapsulated in the payload of specially crafted native exception debug events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6f2b-104">구문</span><span class="sxs-lookup"><span data-stu-id="d6f2b-104">Syntax</span></span>  
  
```  
HRESULT DecodeEvent(  
        [in, length_is(countBytes), size_is(countBytes)]  const BYTE pRecord[],  
        [in] DWORD countBytes,  
        [in] CorDebugRecordFormat format,  
        [in] DWORD dwFlags,   
        [in] DWORD dwThreadId,   
        [out] ICorDebugDebugEvent **ppEvent  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d6f2b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d6f2b-105">Parameters</span></span>  
 `pRecord`  
 <span data-ttu-id="d6f2b-106">[in] 관리되는 디버그 이벤트에 대한 정보를 포함하는 네이티브 예외 디버그 이벤트의 바이트 배열에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d6f2b-106">[in] A pointer to a byte array from a native exception debug event that includes information about a managed debug event.</span></span>  
  
 `countBytes`  
 <span data-ttu-id="d6f2b-107">[in] `pRecord` 바이트 배열의 요소 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6f2b-107">[in] The number of elements in the `pRecord` byte array.</span></span>  
  
 `format`  
 <span data-ttu-id="d6f2b-108">[in] A [CorDebugRecordFormat](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md) 관리 되지 않는 디버그 이벤트의 형식을 지정 하는 열거형 멤버입니다.</span><span class="sxs-lookup"><span data-stu-id="d6f2b-108">[in] A [CorDebugRecordFormat](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md) enumeration member that specifies the format of the unmanaged debug event.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="d6f2b-109">[in] 대상 아키텍처를 사용하며 디버그 이벤트에 대한 추가 정보를 지정하는 비트 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="d6f2b-109">[in] A bit field that depends on the target architecture and that specifies additional information about the debug event.</span></span> <span data-ttu-id="d6f2b-110">Windows 시스템에 대 한 멤버의 수는 [CorDebugDecodeEventFlagsWindows](../../../../docs/framework/unmanaged-api/debugging/cordebugdecodeeventflagswindows-enumeration.md) 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6f2b-110">For Windows systems, it can be a member of the [CorDebugDecodeEventFlagsWindows](../../../../docs/framework/unmanaged-api/debugging/cordebugdecodeeventflagswindows-enumeration.md) enumeration.</span></span>  
  
 `dwThreadId`  
 <span data-ttu-id="d6f2b-111">[in] 예외가 throw된 스레드의 운영 체제 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="d6f2b-111">[in] The operating system identifier of the thread on which the exception was thrown.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="d6f2b-112">[out] 주소에 대 한 포인터는 [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) 디코딩된 관리 되는 디버그 이벤트를 나타내는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="d6f2b-112">[out] A pointer to the address of an [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) object that represents a decoded managed debug event.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d6f2b-113">설명</span><span class="sxs-lookup"><span data-stu-id="d6f2b-113">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d6f2b-114">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6f2b-114">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d6f2b-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d6f2b-115">Requirements</span></span>  
 <span data-ttu-id="d6f2b-116">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d6f2b-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d6f2b-117">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d6f2b-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d6f2b-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d6f2b-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d6f2b-119">**.NET framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d6f2b-119">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6f2b-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d6f2b-120">See Also</span></span>  
 [<span data-ttu-id="d6f2b-121">ICorDebugProcess6 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d6f2b-121">ICorDebugProcess6 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)  
 [<span data-ttu-id="d6f2b-122">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d6f2b-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
