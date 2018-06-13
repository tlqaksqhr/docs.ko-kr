---
title: ICorDebugManagedCallback2::Exception 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.Exception
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::Exception
helpviewer_keywords:
- ICorDebugManagedCallback2::Exception method [.NET Framework debugging]
- Exception method, ICorDebugManagedCallback2 interface [.NET Framework debugging]
ms.assetid: 78b0f14f-2fae-4e63-8412-4df119ee8468
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: faefff879142d66c4c596f1b30a25e349a4014b9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33421803"
---
# <a name="icordebugmanagedcallback2exception-method"></a><span data-ttu-id="ee2a7-102">ICorDebugManagedCallback2::Exception 메서드</span><span class="sxs-lookup"><span data-stu-id="ee2a7-102">ICorDebugManagedCallback2::Exception Method</span></span>
<span data-ttu-id="ee2a7-103">예외 처리기에 대 한 검색이 시작 되었음을 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="ee2a7-103">Notifies the debugger that a search for an exception handler has started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee2a7-104">구문</span><span class="sxs-lookup"><span data-stu-id="ee2a7-104">Syntax</span></span>  
  
```  
HRESULT Exception (  
    [in] ICorDebugAppDomain   *pAppDomain,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugFrame       *pFrame,  
    [in] ULONG32              nOffset,  
    [in] CorDebugExceptionCallbackType dwEventType,  
    [in] DWORD                dwFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ee2a7-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ee2a7-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="ee2a7-106">[in] 예외가 throw 된 스레드를 포함 하는 응용 프로그램 도메인을 나타내는 ICorDebugAppDomain 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ee2a7-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the thread on which the exception was thrown.</span></span>  
  
 `pThread`  
 <span data-ttu-id="ee2a7-107">[in] 예외가 throw 된 스레드를 나타내는 ICorDebugThread 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ee2a7-107">[in] A pointer to an ICorDebugThread object that represents the thread on which the exception was thrown.</span></span>  
  
 `pFrame`  
 <span data-ttu-id="ee2a7-108">[in] 프레임을 기준으로를 나타내는 ICorDebugFrame 개체에 대 한 포인터는 `dwEventType` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="ee2a7-108">[in] A pointer to an ICorDebugFrame object that represents a frame, as determined by the `dwEventType` parameter.</span></span> <span data-ttu-id="ee2a7-109">자세한 내용은 주의 섹션의 표를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee2a7-109">For more information, see the table in the Remarks section.</span></span>  
  
 `nOffset`  
 <span data-ttu-id="ee2a7-110">[in] 의해 결정 되는 오프셋을 지정 하는 정수는 `dwEventType` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="ee2a7-110">[in] An integer that specifies an offset, as determined by the `dwEventType` parameter.</span></span> <span data-ttu-id="ee2a7-111">자세한 내용은 주의 섹션의 표를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee2a7-111">For more information, see the table in the Remarks section.</span></span>  
  
 `dwEventType`  
 <span data-ttu-id="ee2a7-112">[in] 이 예외 콜백의 유형을 지정 하는 CorDebugExceptionCallbackType 열거형의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="ee2a7-112">[in] A value of the CorDebugExceptionCallbackType enumeration that specifies the type of this exception callback.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="ee2a7-113">[in] 값은 [CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md) 예외에 대 한 추가 정보를 지정 하는 열거형</span><span class="sxs-lookup"><span data-stu-id="ee2a7-113">[in] A value of the [CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md) enumeration that specifies additional information about the exception</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ee2a7-114">설명</span><span class="sxs-lookup"><span data-stu-id="ee2a7-114">Remarks</span></span>  
 <span data-ttu-id="ee2a7-115">`Exception` 콜백은 예외 처리 프로세스의 검색 단계 동안 다양 한 시점에서 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ee2a7-115">The `Exception` callback is called at various points during the search phase of the exception-handling process.</span></span> <span data-ttu-id="ee2a7-116">즉,이 호출 될 수 동안 두 번 이상 예외를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee2a7-116">That is, it can be called more than once while unwinding an exception.</span></span>  
  
 <span data-ttu-id="ee2a7-117">처리 중인 예외를 참조 하는 ICorDebugThread 개체에서 검색할 수 있습니다는 `pThread` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="ee2a7-117">The exception being processed can be retrieved from the ICorDebugThread object referenced by the `pThread` parameter.</span></span>  
  
 <span data-ttu-id="ee2a7-118">특정 프레임 및 오프셋에 의해 결정 되는 `dwEventType` 다음과 같이 매개 변수:</span><span class="sxs-lookup"><span data-stu-id="ee2a7-118">The particular frame and offset are determined by the `dwEventType` parameter as follows:</span></span>  
  
|<span data-ttu-id="ee2a7-119">`dwEventType`의 값</span><span class="sxs-lookup"><span data-stu-id="ee2a7-119">Value of `dwEventType`</span></span>|<span data-ttu-id="ee2a7-120">`pFrame`의 값</span><span class="sxs-lookup"><span data-stu-id="ee2a7-120">Value of `pFrame`</span></span>|<span data-ttu-id="ee2a7-121">`nOffset`의 값</span><span class="sxs-lookup"><span data-stu-id="ee2a7-121">Value of `nOffset`</span></span>|  
|----------------------------|-----------------------|------------------------|  
|<span data-ttu-id="ee2a7-122">DEBUG_EXCEPTION_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="ee2a7-122">DEBUG_EXCEPTION_FIRST_CHANCE</span></span>|<span data-ttu-id="ee2a7-123">예외를 발생 시킨 프레임입니다.</span><span class="sxs-lookup"><span data-stu-id="ee2a7-123">The frame that threw the exception.</span></span>|<span data-ttu-id="ee2a7-124">프레임의 명령 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ee2a7-124">The instruction pointer in the frame.</span></span>|  
|<span data-ttu-id="ee2a7-125">DEBUG_EXCEPTION_USER_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="ee2a7-125">DEBUG_EXCEPTION_USER_FIRST_CHANCE</span></span>|<span data-ttu-id="ee2a7-126">예외가 throw 된 지점과 가장 가까운 사용자 코드 프레임입니다.</span><span class="sxs-lookup"><span data-stu-id="ee2a7-126">The user-code frame closest to the point of the thrown exception.</span></span>|<span data-ttu-id="ee2a7-127">프레임의 명령 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ee2a7-127">The instruction pointer in the frame.</span></span>|  
|<span data-ttu-id="ee2a7-128">DEBUG_EXCEPTION_CATCH_HANDLER_FOUND</span><span class="sxs-lookup"><span data-stu-id="ee2a7-128">DEBUG_EXCEPTION_CATCH_HANDLER_FOUND</span></span>|<span data-ttu-id="ee2a7-129">Catch 처리기가 포함 된 프레임입니다.</span><span class="sxs-lookup"><span data-stu-id="ee2a7-129">The frame that contains the catch handler.</span></span>|<span data-ttu-id="ee2a7-130">Catch 처리기를 시작 하는 Microsoft MSIL (intermediate language) 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="ee2a7-130">The Microsoft intermediate language (MSIL) offset of the beginning of the catch handler.</span></span>|  
|<span data-ttu-id="ee2a7-131">DEBUG_EXCEPTION_UNHANDLED</span><span class="sxs-lookup"><span data-stu-id="ee2a7-131">DEBUG_EXCEPTION_UNHANDLED</span></span>|<span data-ttu-id="ee2a7-132">NULL</span><span class="sxs-lookup"><span data-stu-id="ee2a7-132">NULL</span></span>|<span data-ttu-id="ee2a7-133">정의 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="ee2a7-133">Undefined.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ee2a7-134">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ee2a7-134">Requirements</span></span>  
 <span data-ttu-id="ee2a7-135">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ee2a7-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ee2a7-136">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ee2a7-136">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ee2a7-137">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ee2a7-137">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ee2a7-138">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ee2a7-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee2a7-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ee2a7-139">See Also</span></span>  
 [<span data-ttu-id="ee2a7-140">ICorDebugManagedCallback2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ee2a7-140">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)  
 [<span data-ttu-id="ee2a7-141">ICorDebugManagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ee2a7-141">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
