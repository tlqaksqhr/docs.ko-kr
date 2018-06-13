---
title: ICLRDataTarget3::GetExceptionRecord 메서드
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICLRDataTarget3.GetExceptionRecord
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 6643c2af-2ee6-4789-aa25-1d8eaf500c94
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2b6a5a12cb2eac655600e1425a6f9480910caa34
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33407703"
---
# <a name="iclrdatatarget3getexceptionrecord-method"></a><span data-ttu-id="59200-102">ICLRDataTarget3::GetExceptionRecord 메서드</span><span class="sxs-lookup"><span data-stu-id="59200-102">ICLRDataTarget3::GetExceptionRecord Method</span></span>
<span data-ttu-id="59200-103">공용 언어 런타임(CLR)에 의해 호출되는 데이터 액세스는 대상 프로세스와 연관된 예외 레코드 검색을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="59200-103">Called by the common language runtime (CLR) data access services to retrieve the exception record associated with the target process.</span></span> <span data-ttu-id="59200-104">예를 들어 덤프 대상의 경우에 대 한 것을 통해 전달 된 예외 레코드에 해당는 `ExceptionParam` 인수에는 [MiniDumpWriteDump](http://msdn.microsoft.com/library/windows/desktop/ms680360.aspx) Windows 디버그 도움말 라이브러리 (DbgHelp)의 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="59200-104">For example, for a dump target, this would be equivalent to the exception record passed in via the `ExceptionParam` argument to the [MiniDumpWriteDump](http://msdn.microsoft.com/library/windows/desktop/ms680360.aspx) function in the Windows Debug Help Library (DbgHelp).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59200-105">구문</span><span class="sxs-lookup"><span data-stu-id="59200-105">Syntax</span></span>  
  
```cpp  
HRESULT GetExceptionRecord(  
    [in] ULONG32 bufferSize,  
    [out] ULONG32* bufferUsed,  
    [out, size_is(bufferSize] BYTE* buffer  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="59200-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="59200-106">Parameters</span></span>  
 `bufferSize`  
 <span data-ttu-id="59200-107">[in] 입력 버퍼 크기(바이트)로,</span><span class="sxs-lookup"><span data-stu-id="59200-107">[in] The input buffer size, in bytes.</span></span> <span data-ttu-id="59200-108">와 동일 해야이 `sizeof(` [MINIDUMP_EXCEPTION](http://msdn.microsoft.com/library/windows/desktop/ms680367.aspx)`)`합니다.</span><span class="sxs-lookup"><span data-stu-id="59200-108">This must be equal to `sizeof(`[MINIDUMP_EXCEPTION](http://msdn.microsoft.com/library/windows/desktop/ms680367.aspx)`)`.</span></span>  
  
 `bufferUsed`  
 <span data-ttu-id="59200-109">[out] 실제로 버퍼에 기록되는 바이트 수를 받는 `ULONG32` 형식에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="59200-109">[out] A pointer to a `ULONG32` type that receives the number of bytes actually written to the buffer.</span></span>  
  
 `buffer`  
 <span data-ttu-id="59200-110">[out] 예외 레코드 복사본을 받는 메모리 버퍼에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="59200-110">[out] A pointer to a memory buffer that receives a copy of the exception record.</span></span> <span data-ttu-id="59200-111">예외 레코드로 반환 되는 [MINIDUMP_EXCEPTION](http://msdn.microsoft.com/library/windows/desktop/ms680367.aspx) 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="59200-111">The exception record is returned as a [MINIDUMP_EXCEPTION](http://msdn.microsoft.com/library/windows/desktop/ms680367.aspx) type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="59200-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="59200-112">Return Value</span></span>  
 <span data-ttu-id="59200-113">반환 값은 성공 시 `S_OK`이고 실패 시에는 오류 `HRESULT` 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="59200-113">The return value is `S_OK` on success, or a failure `HRESULT` code on failure.</span></span> <span data-ttu-id="59200-114">`HRESULT` 코드는 다음을 비롯한 여러 항목을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59200-114">The `HRESULT` codes can include but are not limited to the following:</span></span>  
  
|<span data-ttu-id="59200-115">반환 코드</span><span class="sxs-lookup"><span data-stu-id="59200-115">Return code</span></span>|<span data-ttu-id="59200-116">설명</span><span class="sxs-lookup"><span data-stu-id="59200-116">Description</span></span>|  
|-----------------|-----------------|  
|`S_OK`|<span data-ttu-id="59200-117">메서드가 정상적으로 실행되었습니다.</span><span class="sxs-lookup"><span data-stu-id="59200-117">Method succeeded.</span></span> <span data-ttu-id="59200-118">예외 레코드가 출력 버퍼에 복사되었습니다.</span><span class="sxs-lookup"><span data-stu-id="59200-118">The exception record has been copied to the output buffer.</span></span>|  
|`HRESULT_FROM_WIN32(ERROR_NOT_FOUND)`|<span data-ttu-id="59200-119">대상에 연결된 예외 레코드가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="59200-119">No exception record is associated with the target.</span></span>|  
|`HRESULT_FROM_WIN32(ERROR_BAD_LENGTH)`|<span data-ttu-id="59200-120">입력 버퍼 크기가 `sizeof(MINIDUMP_EXCEPTION)`와 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="59200-120">The input buffer size is not equal to `sizeof(MINIDUMP_EXCEPTION)`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="59200-121">설명</span><span class="sxs-lookup"><span data-stu-id="59200-121">Remarks</span></span>  
 <span data-ttu-id="59200-122">[MINIDUMP_EXCEPTION](http://msdn.microsoft.com/library/windows/desktop/ms680367.aspx) dbghelp.h 및 imagehlp.h Windows SDK에 정의 된 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="59200-122">[MINIDUMP_EXCEPTION](http://msdn.microsoft.com/library/windows/desktop/ms680367.aspx) is a structure defined in dbghelp.h and imagehlp.h in the Windows SDK.</span></span>  
  
 <span data-ttu-id="59200-123">이 메서드는 디버깅 응용 프로그램의 작성자가 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="59200-123">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="59200-124">요구 사항</span><span class="sxs-lookup"><span data-stu-id="59200-124">Requirements</span></span>  
 <span data-ttu-id="59200-125">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="59200-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="59200-126">**헤더:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="59200-126">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="59200-127">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="59200-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="59200-128">**.NET framework 버전:** [!INCLUDE[v451_update](../../../../includes/v451-update-md.md)]</span><span class="sxs-lookup"><span data-stu-id="59200-128">**.NET Framework Versions:** [!INCLUDE[v451_update](../../../../includes/v451-update-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59200-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="59200-129">See Also</span></span>  
 [<span data-ttu-id="59200-130">ICLRDataTarget3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="59200-130">ICLRDataTarget3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-interface.md)  
 [<span data-ttu-id="59200-131">GetExceptionContextRecord 메서드</span><span class="sxs-lookup"><span data-stu-id="59200-131">GetExceptionContextRecord Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptioncontextrecord-method.md)  
 [<span data-ttu-id="59200-132">GetExceptionThreadID 메서드</span><span class="sxs-lookup"><span data-stu-id="59200-132">GetExceptionThreadID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptionthreadid-method.md)
