---
title: ICLRDataTarget3::GetExceptionThreadID 메서드
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICLRDataTarget3.GetExceptionThreadID
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 307d6ac7-4a86-45f3-999d-6b47004a68f2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7c838c994144307e9c87e3a4628fa80bfcdbeb59
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33406768"
---
# <a name="iclrdatatarget3getexceptionthreadid-method"></a><span data-ttu-id="653d6-102">ICLRDataTarget3::GetExceptionThreadID 메서드</span><span class="sxs-lookup"><span data-stu-id="653d6-102">ICLRDataTarget3::GetExceptionThreadID Method</span></span>
<span data-ttu-id="653d6-103">CLR(공용 언어 런타임) 데이터 액세스 서비스에 의해 호출되어 예외를 throw한 스레드의 ID를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="653d6-103">Called by the common language runtime (CLR) data access services to get the ID of the thread that threw the exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="653d6-104">구문</span><span class="sxs-lookup"><span data-stu-id="653d6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetExceptionThreadID(  
    [out] ULONG32* threadID  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="653d6-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="653d6-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="653d6-106">[out] 예외를 throw한 스레드의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="653d6-106">[out] The ID of the thread that threw the exception.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="653d6-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="653d6-107">Return Value</span></span>  
 <span data-ttu-id="653d6-108">반환 값은 성공 시 `S_OK`이고 실패 시에는 오류 `HRESULT` 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="653d6-108">The return value is `S_OK` on success, or a failure `HRESULT` code on failure.</span></span> <span data-ttu-id="653d6-109">`HRESULT` 코드는 다음을 비롯한 여러 항목을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="653d6-109">The `HRESULT` codes can include but are not limited to the following:</span></span>  
  
|<span data-ttu-id="653d6-110">반환 코드</span><span class="sxs-lookup"><span data-stu-id="653d6-110">Return code</span></span>|<span data-ttu-id="653d6-111">설명</span><span class="sxs-lookup"><span data-stu-id="653d6-111">Description</span></span>|  
|-----------------|-----------------|  
|`S_OK`|<span data-ttu-id="653d6-112">메서드가 정상적으로 실행되었습니다.</span><span class="sxs-lookup"><span data-stu-id="653d6-112">Method succeeded.</span></span>|  
|`HRESULT_FROM_WIN32(ERROR_NOT_FOUND)`|<span data-ttu-id="653d6-113">예외의 유효한 스레드 ID를 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="653d6-113">Could not find a valid thread ID for the exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="653d6-114">설명</span><span class="sxs-lookup"><span data-stu-id="653d6-114">Remarks</span></span>  
 <span data-ttu-id="653d6-115">이 메서드는 디버깅 응용 프로그램의 작성자가 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="653d6-115">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="653d6-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="653d6-116">Requirements</span></span>  
 <span data-ttu-id="653d6-117">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="653d6-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="653d6-118">**헤더:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="653d6-118">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="653d6-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="653d6-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="653d6-120">**.NET framework 버전:** [!INCLUDE[v451_update](../../../../includes/v451-update-md.md)]</span><span class="sxs-lookup"><span data-stu-id="653d6-120">**.NET Framework Versions:** [!INCLUDE[v451_update](../../../../includes/v451-update-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="653d6-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="653d6-121">See Also</span></span>  
 [<span data-ttu-id="653d6-122">ICLRDataTarget3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="653d6-122">ICLRDataTarget3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-interface.md)  
 [<span data-ttu-id="653d6-123">GetExceptionContextRecord 메서드</span><span class="sxs-lookup"><span data-stu-id="653d6-123">GetExceptionContextRecord Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptioncontextrecord-method.md)  
 [<span data-ttu-id="653d6-124">GetExceptionRecord 메서드</span><span class="sxs-lookup"><span data-stu-id="653d6-124">GetExceptionRecord Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptionrecord-method.md)
