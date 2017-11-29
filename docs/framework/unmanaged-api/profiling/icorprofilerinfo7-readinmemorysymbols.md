---
title: ICorProfilerInfo7::ReadInMemorySymbols
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
api_name: ICorProfilerInfo7.ReadInMemorySymbols
api_location:
- CorProf.idl
- CorProf.h
- CorGuids.lib
api_type: COM
ms.assetid: 1745a0b9-8332-4777-a670-b549bff3b901
caps.latest.revision: "3"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9ada9f629c3a3c3d8b7c32ebc180c4788b6f6d3f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerinfo7readinmemorysymbols"></a><span data-ttu-id="8b283-102">ICorProfilerInfo7::ReadInMemorySymbols</span><span class="sxs-lookup"><span data-stu-id="8b283-102">ICorProfilerInfo7::ReadInMemorySymbols</span></span>
<span data-ttu-id="8b283-103">[[!INCLUDE[net_v461](../../../../includes/net-v461-md.md)] 이상 버전에서 지원됨]</span><span class="sxs-lookup"><span data-stu-id="8b283-103">[Supported in the [!INCLUDE[net_v461](../../../../includes/net-v461-md.md)] and later versions]</span></span>  
  
 <span data-ttu-id="8b283-104">메모리 내 기호 스트림에서 바이트를 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="8b283-104">Reads bytes from an in-memory symbol stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b283-105">구문</span><span class="sxs-lookup"><span data-stu-id="8b283-105">Syntax</span></span>  
  
```  
HRESULT ReadInMemorySymbols(  
        [in] ModuleID moduleId,  
        [in] DWORD symbolsReadOffset,  
        [out] BYTE* pSymbolBytes,  
        [in] DWORD countSymbolBytes,  
        [out] DWORD* pCountSymbolBytesRead  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8b283-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8b283-106">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="8b283-107">[in] 메모리 스트림을 포함 하는 모듈의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="8b283-107">[in] The identifier of the module containing the in-memory stream.</span></span>  
  
 `symbolsReadOffset`  
 <span data-ttu-id="8b283-108">[in] 바이트 읽기를 시작 하는 메모리 내 스트림 내의 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="8b283-108">[in] The offset within the in-memory stream at which to start reading bytes.</span></span>  
  
 `pSymbolBytes`  
 <span data-ttu-id="8b283-109">[out] 데이터를 복사할 버퍼에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="8b283-109">[out] A pointer to the buffer to which the data will be copied.</span></span> <span data-ttu-id="8b283-110">버퍼 있어야 `countSymbolBytes` 의 사용 가능한 공간입니다.</span><span class="sxs-lookup"><span data-stu-id="8b283-110">The buffer should have `countSymbolBytes` of space available.</span></span>  
  
 `countSymbolBytes`  
 <span data-ttu-id="8b283-111">[in] 복사할 바이트의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="8b283-111">[in] The number of bytes to copy.</span></span>  
  
 `pCountSymbolBytesRead`  
 <span data-ttu-id="8b283-112">[out] 메서드가 반환 될 때 실제 읽은 바이트 수를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b283-112">[out] When the method returns, contains the actual number of bytes read.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8b283-113">반환 값</span><span class="sxs-lookup"><span data-stu-id="8b283-113">Return Value</span></span>  
 <span data-ttu-id="8b283-114">`S_OK`를 읽어 들인 바이트 수를 0이 아닌 경우.</span><span class="sxs-lookup"><span data-stu-id="8b283-114">`S_OK`, if a non-zero number of bytes were read.</span></span>  
  
 <span data-ttu-id="8b283-115">`CORPROF_E_MODULE_IS_DYNAMIC`를 사용 하 여 모듈을 만든 경우 <xref:System.Reflection.Emit>합니다.</span><span class="sxs-lookup"><span data-stu-id="8b283-115">`CORPROF_E_MODULE_IS_DYNAMIC`, if the module was created using <xref:System.Reflection.Emit>.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8b283-116">설명</span><span class="sxs-lookup"><span data-stu-id="8b283-116">Remarks</span></span>  
 <span data-ttu-id="8b283-117">`ReadInMemorySymbols` 메서드 읽으려고 시도 `countSymbolBytes` 오프셋에서 시작 하는 데이터의 `symbolsReadOffset` 메모리 스트림 내에서.</span><span class="sxs-lookup"><span data-stu-id="8b283-117">The `ReadInMemorySymbols` method attempts to read `countSymbolBytes` of data starting at offset      `symbolsReadOffset` within the in-memory stream.</span></span> <span data-ttu-id="8b283-118">데이터 복사 `pSymbolBytes`, 있어야 사용할 수 있는 `countSymbolBytes` 의 사용 가능한 공간입니다.</span><span class="sxs-lookup"><span data-stu-id="8b283-118">The data is copied to `pSymbolBytes`, which is expected to have `countSymbolBytes` of space available.</span></span>     <span data-ttu-id="8b283-119">`pCountSymbolsBytesRead`실제 읽은 발생할 수 있는 작은 바이트 수를 포함 보다 `countSymbolBytes` 스트림의 끝에 도달 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b283-119">`pCountSymbolsBytesRead` contains the actual number of bytes read, which may be less than `countSymbolBytes` if the end of the stream is reached.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8b283-120">현재 구현에서는 Reflection.Emit를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8b283-120">The current implementation does not support Reflection.Emit.</span></span> <span data-ttu-id="8b283-121">메서드가 반환 하는 경우 모듈 Reflection.Emit를 사용 하 여 만든, `CORPROF_E_MODULE_IS_DYNAMIC`합니다.</span><span class="sxs-lookup"><span data-stu-id="8b283-121">If the module was created by using Reflection.Emit, the method returns `CORPROF_E_MODULE_IS_DYNAMIC`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8b283-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8b283-122">Requirements</span></span>  
 <span data-ttu-id="8b283-123">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8b283-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b283-124">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8b283-124">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8b283-125">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8b283-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8b283-126">**.NET Framework 버전:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8b283-126">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b283-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8b283-127">See Also</span></span>  
 [<span data-ttu-id="8b283-128">ICorProfilerInfo7 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8b283-128">ICorProfilerInfo7 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)
