---
title: "ICLRDataTarget3::GetExceptionContextRecord 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: cpp
api_name: ICLRDataTarget3.GetContextRecord
api_location: mscordbi.dll
api_type: COM
ms.assetid: 66076ed5-f05c-4114-9788-94cb143abb8a
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 517e2a692c3b67a85bc24437dd5fbaedd5fc7254
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="iclrdatatarget3getexceptioncontextrecord-method"></a><span data-ttu-id="ed058-102">ICLRDataTarget3::GetExceptionContextRecord 메서드</span><span class="sxs-lookup"><span data-stu-id="ed058-102">ICLRDataTarget3::GetExceptionContextRecord Method</span></span>
<span data-ttu-id="ed058-103">CLR(공용 언어 런타임) 데이터 액세스 서비스에 의해 호출되어 대상 프로세스와 연결된 컨텍스트 레코드를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="ed058-103">Called by the common language runtime (CLR) data access services to retrieve the context record associated with the target process.</span></span> <span data-ttu-id="ed058-104">예를 들어 덤프 대상의 경우에 대 한 것을 통해 전달 된 컨텍스트 레코드에 해당는 `ExceptionParam` 인수에는 [MiniDumpWriteDump](http://msdn.microsoft.com/library/windows/desktop/ms680360\(v=vs.85\).aspx) Windows 디버그 도움말 라이브러리 (DbgHelp)의 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="ed058-104">For example, for a dump target, this would be equivalent to the context record passed in via the `ExceptionParam` argument to the [MiniDumpWriteDump](http://msdn.microsoft.com/library/windows/desktop/ms680360\(v=vs.85\).aspx) function in the Windows Debug Help Library (DbgHelp).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed058-105">구문</span><span class="sxs-lookup"><span data-stu-id="ed058-105">Syntax</span></span>  
  
```cpp  
HRESULT GetExceptionContextRecord(  
    [in] ULONG32 bufferSize,  
    [out] ULONG32* bufferUsed,  
    [out, size_is(bufferSize)] BYTE* buffer  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ed058-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ed058-106">Parameters</span></span>  
 `bufferSize`  
 <span data-ttu-id="ed058-107">[in] 입력 버퍼 크기(바이트)로,</span><span class="sxs-lookup"><span data-stu-id="ed058-107">[in] The input buffer size, in bytes.</span></span> <span data-ttu-id="ed058-108">컨텍스트 레코드를 포함할 수 있을 정도로 커야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed058-108">This must be large enough to accommodate the context record.</span></span>  
  
 `bufferUsed`  
 <span data-ttu-id="ed058-109">[out] 실제로 버퍼에 기록되는 바이트 수를 받는 `ULONG32` 형식에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ed058-109">[out] A pointer to a `ULONG32` type that receives the number of bytes actually written to the buffer.</span></span>  
  
 `buffer`  
 <span data-ttu-id="ed058-110">[out] 컨텍스트 레코드 복사본을 받는 메모리 버퍼에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ed058-110">[out] A pointer to a memory buffer that receives a copy of the context record.</span></span> <span data-ttu-id="ed058-111">예외 레코드로 반환 됩니다는 [컨텍스트](http://msdn.microsoft.com/library/windows/desktop/ms679284\(v=vs.85\).aspx) 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="ed058-111">The exception record is returned as a [CONTEXT](http://msdn.microsoft.com/library/windows/desktop/ms679284\(v=vs.85\).aspx) type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ed058-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="ed058-112">Return Value</span></span>  
 <span data-ttu-id="ed058-113">반환 값은 성공 시 `S_OK`이고 실패 시에는 오류 `HRESULT` 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="ed058-113">The return value is `S_OK` on success, or a failure `HRESULT` code on failure.</span></span> <span data-ttu-id="ed058-114">`HRESULT` 코드는 다음을 비롯한 여러 항목을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed058-114">The `HRESULT` codes can include but are not limited to the following:</span></span>  
  
|<span data-ttu-id="ed058-115">반환 코드</span><span class="sxs-lookup"><span data-stu-id="ed058-115">Return code</span></span>|<span data-ttu-id="ed058-116">설명</span><span class="sxs-lookup"><span data-stu-id="ed058-116">Description</span></span>|  
|-----------------|-----------------|  
|`S_OK`|<span data-ttu-id="ed058-117">메서드가 정상적으로 실행되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ed058-117">Method succeeded.</span></span> <span data-ttu-id="ed058-118">컨텍스트 레코드가 출력 버퍼에 복사되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ed058-118">The context record has been copied to the output buffer.</span></span>|  
|`HRESULT_FROM_WIN32(ERROR_NOT_FOUND)`|<span data-ttu-id="ed058-119">컨텍스트 레코드가 대상에 연결되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="ed058-119">No context record is associated with the target.</span></span>|  
|`HRESULT_FROM_WIN32(ERROR_BAD_LENGTH)`|<span data-ttu-id="ed058-120">입력 버퍼 크기가 컨텍스트 레코드를 수용할 수 있을 정도로 크지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ed058-120">The input buffer size is not large enough to accommodate the context record.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ed058-121">설명</span><span class="sxs-lookup"><span data-stu-id="ed058-121">Remarks</span></span>  
 <span data-ttu-id="ed058-122">[상황에 맞는](http://msdn.microsoft.com/library/windows/desktop/ms679284\(v=vs.85\).aspx) Windows SDK에서 제공 하는 헤더에 정의 된 플랫폼별 구조체입니다.</span><span class="sxs-lookup"><span data-stu-id="ed058-122">[CONTEXT](http://msdn.microsoft.com/library/windows/desktop/ms679284\(v=vs.85\).aspx) is a platform-specific structure defined in headers provided by the Windows SDK.</span></span>  
  
 <span data-ttu-id="ed058-123">이 메서드는 디버깅 응용 프로그램의 작성자가 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="ed058-123">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed058-124">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ed058-124">Requirements</span></span>  
 <span data-ttu-id="ed058-125">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ed058-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed058-126">**헤더:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="ed058-126">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="ed058-127">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ed058-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ed058-128">**.NET framework 버전:**[!INCLUDE[v451_update](../../../../includes/v451-update-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ed058-128">**.NET Framework Versions:** [!INCLUDE[v451_update](../../../../includes/v451-update-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed058-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ed058-129">See Also</span></span>  
 [<span data-ttu-id="ed058-130">ICLRDataTarget3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ed058-130">ICLRDataTarget3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-interface.md)  
 [<span data-ttu-id="ed058-131">GetExceptionRecord 메서드</span><span class="sxs-lookup"><span data-stu-id="ed058-131">GetExceptionRecord Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptionrecord-method.md)  
 [<span data-ttu-id="ed058-132">GetExceptionThreadID 메서드</span><span class="sxs-lookup"><span data-stu-id="ed058-132">GetExceptionThreadID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptionthreadid-method.md)
