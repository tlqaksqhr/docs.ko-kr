---
title: "ICorDebugModule3::CreateReaderForInMemorySymbols 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugModule3.CreateReaderForInMemorySymbols
api_location: CorDebug.dll
api_type: COM
f1_keywords: ICorDebugModule3::CreateReaderForInMemorySymbols
helpviewer_keywords:
- CreateReaderForInMemorySymbols method, ICorDebugModule3 interface [.NET Framework debugging]
- ICorDebugModule3::CreateReaderForInMemorySymbols method [.NET Framework debugging]
ms.assetid: af317171-d66d-4114-89eb-063554c74940
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2838c6c1fe8641e343fac1a3efa82a39ee177abc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmodule3createreaderforinmemorysymbols-method"></a><span data-ttu-id="a2697-102">ICorDebugModule3::CreateReaderForInMemorySymbols 메서드</span><span class="sxs-lookup"><span data-stu-id="a2697-102">ICorDebugModule3::CreateReaderForInMemorySymbols Method</span></span>
<span data-ttu-id="a2697-103">동적 모듈에 대 한 디버그 기호 판독기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a2697-103">Creates a debug symbol reader for a dynamic module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2697-104">구문</span><span class="sxs-lookup"><span data-stu-id="a2697-104">Syntax</span></span>  
  
```  
HRESULT CreateReaderForInMemorySymbols (  
      [in] REFIID riid,  
      [out][iid_is(riid)] void **    ppObj  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a2697-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a2697-105">Parameters</span></span>  
 <span data-ttu-id="a2697-106">riid</span><span class="sxs-lookup"><span data-stu-id="a2697-106">riid</span></span>  
 <span data-ttu-id="a2697-107">[in] 반환할 COM 인터페이스의 IID입니다.</span><span class="sxs-lookup"><span data-stu-id="a2697-107">[in] The IID of the COM interface to return.</span></span> <span data-ttu-id="a2697-108">이 일반적으로 [ISymUnmanagedReader 인터페이스](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a2697-108">Typically, this is an [ISymUnmanagedReader Interface](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md).</span></span>  
  
 <span data-ttu-id="a2697-109">ppObj</span><span class="sxs-lookup"><span data-stu-id="a2697-109">ppObj</span></span>  
 <span data-ttu-id="a2697-110">[out] 반환 되는 인터페이스에 대 한 포인터에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a2697-110">[out] Pointer to a pointer to the returned interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a2697-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="a2697-111">Return Value</span></span>  
 <span data-ttu-id="a2697-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="a2697-112">S_OK</span></span>  
 <span data-ttu-id="a2697-113">판독기를 성공적으로 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="a2697-113">Successfully created the reader.</span></span>  
  
 <span data-ttu-id="a2697-114">CORDBG_E_MODULE_LOADED_FROM_DISK</span><span class="sxs-lookup"><span data-stu-id="a2697-114">CORDBG_E_MODULE_LOADED_FROM_DISK</span></span>  
 <span data-ttu-id="a2697-115">모듈은 메모리 또는 동적 모듈이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="a2697-115">The module is not an in-memory or dynamic module.</span></span>  
  
 <span data-ttu-id="a2697-116">CORDBG_E_SYMBOLS_NOT_AVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a2697-116">CORDBG_E_SYMBOLS_NOT_AVAILABLE</span></span>  
 <span data-ttu-id="a2697-117">응용 프로그램에서 지정 되지 않은 기호나 아직 제공 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a2697-117">Symbols have not been supplied by the application or are not yet available.</span></span>  
  
 <span data-ttu-id="a2697-118">E_FAIL(또는 다른 E_ 반환 코드)</span><span class="sxs-lookup"><span data-stu-id="a2697-118">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="a2697-119">판독기를 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a2697-119">Unable to create the reader.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a2697-120">설명</span><span class="sxs-lookup"><span data-stu-id="a2697-120">Remarks</span></span>  
 <span data-ttu-id="a2697-121">이 메서드도만 될 수 있습니다를 메모리에 있는 (동적이 지 않은) 모듈에 대 한 기호 판독기 개체를 만드는 사용 되는 기호는 사용할 수 있는 먼저 후 (가리키는 [UpdateModuleSymbols 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-updatemodulesymbols-method.md) 콜백).</span><span class="sxs-lookup"><span data-stu-id="a2697-121">This method can also be used to create a symbol reader object for in-memory (non-dynamic) modules, but only after the symbols are first available (indicated by the [UpdateModuleSymbols Method](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-updatemodulesymbols-method.md) callback).</span></span>  
  
 <span data-ttu-id="a2697-122">이 메서드가 호출 될 때마다 새 판독기 인스턴스를 반환 (같은 [CComPtrBase::CoCreateInstance](http://msdn.microsoft.com/library/c0965041-6cb6-40c5-b272-2b99f02668a6)).</span><span class="sxs-lookup"><span data-stu-id="a2697-122">This method returns a new reader instance every time it is called (like [CComPtrBase::CoCreateInstance](http://msdn.microsoft.com/library/c0965041-6cb6-40c5-b272-2b99f02668a6)).</span></span> <span data-ttu-id="a2697-123">디버거가 해야 결과 캐시 하 고 기본 데이터 변경 하는 경우에 새 인스턴스를 요청 하는 따라서 (때, 즉는 [LoadClass 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) 콜백을 수신) 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2697-123">Therefore, the debugger should cache the result and request a new instance only when the underlying data may have changed (that is, when a [LoadClass Method](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) callback is received).</span></span>  
  
 <span data-ttu-id="a2697-124">동적 모듈의 기호를 사용할 수 있는 권한이 첫 번째 유형은 로드할 때까지 (나타내듯이 [LoadClass 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) 콜백).</span><span class="sxs-lookup"><span data-stu-id="a2697-124">Dynamic modules do not have any symbols available until the first type has been loaded (as indicated by the [LoadClass Method](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) callback).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a2697-125">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a2697-125">Requirements</span></span>  
 <span data-ttu-id="a2697-126">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a2697-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a2697-127">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a2697-127">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a2697-128">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a2697-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a2697-129">**.NET framework 버전:** 4.5, 4, 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="a2697-129">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2697-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a2697-130">See Also</span></span>  
 [<span data-ttu-id="a2697-131">ICorDebugRemoteTarget 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a2697-131">ICorDebugRemoteTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)  
 [<span data-ttu-id="a2697-132">ICorDebug 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a2697-132">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
    
 [<span data-ttu-id="a2697-133">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a2697-133">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
