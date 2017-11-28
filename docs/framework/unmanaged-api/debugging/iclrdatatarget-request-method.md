---
title: "ICLRDataTarget::Request 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDataTarget.Request
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICLRDataTarget::Request
helpviewer_keywords:
- ICLRDataTarget::Request method [.NET Framework debugging]
- Request method [.NET Framework debugging]
ms.assetid: 4723bd1c-eddb-4ed2-897a-010024a47e01
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0e0ce905ea21267419e6a68e73f918de8fc364f3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="iclrdatatargetrequest-method"></a><span data-ttu-id="8a941-102">ICLRDataTarget::Request 메서드</span><span class="sxs-lookup"><span data-stu-id="8a941-102">ICLRDataTarget::Request Method</span></span>
<span data-ttu-id="8a941-103">구현에 의해 정의 된 대로 작업을 요청 하는 공용 언어 런타임 (CLR) 데이터 액세스 서비스에서 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a941-103">Called by the common language runtime (CLR) data access services to request an operation, as defined by the implementation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a941-104">구문</span><span class="sxs-lookup"><span data-stu-id="8a941-104">Syntax</span></span>  
  
```  
HRESULT Request (  
    [in] ULONG32            reqCode,  
    [in] ULONG32            inBufferSize,  
    [in, size_is(inBufferSize)]   
        BYTE                *inBuffer,  
    [in] ULONG32            outBufferSize,  
    [out, size_is(outBufferSize)]   
        BYTE                *outBuffer  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8a941-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8a941-105">Parameters</span></span>  
 `reqCode`  
 <span data-ttu-id="8a941-106">[in] 사용자 정의입니다.</span><span class="sxs-lookup"><span data-stu-id="8a941-106">[in] User-defined.</span></span>  
  
 `inBufferSize`  
 <span data-ttu-id="8a941-107">[in] 들어오는 요청에 사용 되는 입력된 버퍼의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="8a941-107">[in] The size of the input buffer, which is used for the incoming request.</span></span>  
  
 `inBuffer`  
 <span data-ttu-id="8a941-108">[in] 요청을 포함 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="8a941-108">[in] A buffer containing the request.</span></span>  
  
 `outBufferSize`  
 <span data-ttu-id="8a941-109">[in] 응답에 사용 되는 출력 버퍼의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="8a941-109">[in] The size of the output buffer, which is used for the response.</span></span>  
  
 `outBuffer`  
 <span data-ttu-id="8a941-110">[out] 응답을 포함 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="8a941-110">[out] A Buffer containing the response.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8a941-111">설명</span><span class="sxs-lookup"><span data-stu-id="8a941-111">Remarks</span></span>  
 <span data-ttu-id="8a941-112">`Request` 메서드 지정 되지 않은 사용자 지정 작업 추가 용이 하 게 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a941-112">The `Request` method facilitates the addition of unspecified custom operations.</span></span> <span data-ttu-id="8a941-113">즉,이 메서드는 인터페이스 정의 수정할 필요 없이 확장성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a941-113">That is, this method provides extensibility without requiring revision of the interface definition.</span></span>  
  
 <span data-ttu-id="8a941-114">이 메서드는 디버깅 응용 프로그램의 작성자가 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="8a941-114">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a941-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8a941-115">Requirements</span></span>  
 <span data-ttu-id="8a941-116">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8a941-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a941-117">**헤더:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="8a941-117">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="8a941-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8a941-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8a941-119">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a941-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a941-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8a941-120">See Also</span></span>  
 [<span data-ttu-id="8a941-121">ICLRDataTarget 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8a941-121">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
