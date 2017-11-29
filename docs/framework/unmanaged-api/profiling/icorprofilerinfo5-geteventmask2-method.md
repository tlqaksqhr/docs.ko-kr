---
title: "ICorProfilerInfo5::GetEventMask2 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: cpp
api_name: ICorProfilerInfo5.GetEventMask2
api_location: mscorwks.dll
api_type: COM
ms.assetid: f854b68f-009c-4ffb-89cd-ca874d1c0fb7
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: da1c4c11adaac21e9769330ee24beceff64e020b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo5geteventmask2-method"></a><span data-ttu-id="bedf9-102">ICorProfilerInfo5::GetEventMask2 메서드</span><span class="sxs-lookup"><span data-stu-id="bedf9-102">ICorProfilerInfo5::GetEventMask2 Method</span></span>
<span data-ttu-id="bedf9-103">[.NET Framework 4.5.2 이상 버전에서 지원됨]</span><span class="sxs-lookup"><span data-stu-id="bedf9-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="bedf9-104">프로파일러가 CLR(공용 언어 런타임)에서 알림을 받으려는 현재 이벤트 범주를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="bedf9-104">Gets the current event categories for which the profiler wants to receive notifications from the common language runtime (CLR).</span></span>  <span data-ttu-id="bedf9-105">제공 하지 않는 기능을 제공 하기는 [icorprofilerinfo:: Geteventmask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="bedf9-105">It provides functionality not provided by the [ICorProfilerInfo::GetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bedf9-106">구문</span><span class="sxs-lookup"><span data-stu-id="bedf9-106">Syntax</span></span>  
  
```cpp
HRESULT GetEventMask2(  
        [out] DWORD* pdwEventsLow,  
        [out] DWORD* pdwEventsHigh  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bedf9-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="bedf9-107">Parameters</span></span>  
 `pdwEventsLow`  
 <span data-ttu-id="bedf9-108">[out] 이벤트 범주를 지정하는 4바이트 값에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="bedf9-108">[out] A pointer to a 4-byte value that specifies the categories of events.</span></span> <span data-ttu-id="bedf9-109">각 비트는 서로 다른 기능, 동작 또는 이벤트 형식을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="bedf9-109">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="bedf9-110">비트에 대 한 설명은 [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="bedf9-110">The bits are described in the [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeration.</span></span>  
  
 `pdwEventsHigh`  
 <span data-ttu-id="bedf9-111">[out] 이벤트 범주를 지정하는 4바이트 값에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="bedf9-111">[out] A pointer to a 4-byte value that specifies the categories of events.</span></span>  <span data-ttu-id="bedf9-112">각 비트는 서로 다른 기능, 동작 또는 이벤트 형식을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="bedf9-112">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="bedf9-113">비트에 대 한 설명은 [COR_PRF_HIGH_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="bedf9-113">The bits are described in the [COR_PRF_HIGH_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bedf9-114">설명</span><span class="sxs-lookup"><span data-stu-id="bedf9-114">Remarks</span></span>  
 <span data-ttu-id="bedf9-115">`GetEventMask2` 메서드를 사용하여 프로파일러가 구독한 콜백을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="bedf9-115">The `GetEventMask2` method is used to determine which callbacks the profiler has subscribed to.</span></span> <span data-ttu-id="bedf9-116">논리 OR를 수행 하는 일반적으로 `pdwEventsLow` 및 `pdwEventsHigh` 값과을 설정 하 고 호출 하려는 새 비트의 [SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="bedf9-116">Typically, you perform a logical OR of the `pdwEventsLow` and `pdwEventsHigh` values and any new bits you want to set, and then call the [SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) method.</span></span>  
  
 <span data-ttu-id="bedf9-117">이 메서드는 메서드 대신에는 [GetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="bedf9-117">This method is the recommended alternative to the [GetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bedf9-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bedf9-118">Requirements</span></span>  
 <span data-ttu-id="bedf9-119">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="bedf9-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bedf9-120">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="bedf9-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="bedf9-121">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bedf9-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bedf9-122">**.NET framework 버전:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bedf9-122">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bedf9-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bedf9-123">See Also</span></span>  
 [<span data-ttu-id="bedf9-124">ICorProfilerInfo5 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bedf9-124">ICorProfilerInfo5 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md)  
 [<span data-ttu-id="bedf9-125">SetEventMask2 메서드</span><span class="sxs-lookup"><span data-stu-id="bedf9-125">SetEventMask2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md)
