---
title: COR_PRF_HIGH_MONITOR 열거형
ms.date: 04/10/2018
ms.assetid: 3ba543d8-15e5-4322-b6e7-1ebfc92ed7dd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c92ba2b5eac5eb1368a7d7ccf3b666886f4ca92a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33454716"
---
# <a name="corprfhighmonitor-enumeration"></a><span data-ttu-id="66506-102">COR_PRF_HIGH_MONITOR 열거형</span><span class="sxs-lookup"><span data-stu-id="66506-102">COR_PRF_HIGH_MONITOR Enumeration</span></span>
<span data-ttu-id="66506-103">[.NET Framework 4.5.2 이상 버전에서 지원됨]</span><span class="sxs-lookup"><span data-stu-id="66506-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="66506-104">에 있는 것 외에도 플래그를 제공는 [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) 프로파일러를 지정할 수 있는 열거는 [icorprofilerinfo5:: Seteventmask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) 로드 될 때 메서드.</span><span class="sxs-lookup"><span data-stu-id="66506-104">Provides flags in addition to those found in the [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeration that the profiler can specify to the [ICorProfilerInfo5::SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) method when it is loading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66506-105">구문</span><span class="sxs-lookup"><span data-stu-id="66506-105">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_HIGH_MONITOR_NONE                     = 0x00000000,  
    COR_PRF_HIGH_ADD_ASSEMBLY_REFERENCES          = 0x00000001,  
    COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED        = 0x00000002,     
    COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS = 0x00000004,    
    COR_PRF_HIGH_REQUIRE_PROFILE_IMAGE            = 0,  
    COR_PRF_HIGH_ALLOWABLE_AFTER_ATTACH           = COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED | 
                                                    COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS,  
    COR_PRF_HIGH_MONITOR_IMMUTABLE                = 0  
} COR_PRF_HIGH_MONITOR;  
```  
  
## <a name="members"></a><span data-ttu-id="66506-106">멤버</span><span class="sxs-lookup"><span data-stu-id="66506-106">Members</span></span>  
  
|<span data-ttu-id="66506-107">멤버</span><span class="sxs-lookup"><span data-stu-id="66506-107">Member</span></span>|<span data-ttu-id="66506-108">설명</span><span class="sxs-lookup"><span data-stu-id="66506-108">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_HIGH_MONITOR_NONE`|<span data-ttu-id="66506-109">플래그가 설정되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="66506-109">No flags are set.</span></span>|  
|`COR_PRF_HIGH_ADD_ASSEMBLY_REFERENCES`|<span data-ttu-id="66506-110">컨트롤의 [icorprofilercallback6:: Getassemblyreference](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) CLR 어셈블리 참조 closure 워커 중에 어셈블리 참조를 추가 하기 위한 콜백 합니다.</span><span class="sxs-lookup"><span data-stu-id="66506-110">Controls the [ICorProfilerCallback6::GetAssemblyReference](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) callback for adding assembly references during the CLR assembly reference closure walk.</span></span>|  
|`COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED`|<span data-ttu-id="66506-111">컨트롤의 [ICorProfilerCallback7::ModuleInMemorySymbolsUpdated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback7-moduleinmemorysymbolsupdated-method.md) 메모리 내 모듈과 연관 된 기호 스트림이 업데이트에 대 한 콜백입니다.</span><span class="sxs-lookup"><span data-stu-id="66506-111">Controls the [ICorProfilerCallback7::ModuleInMemorySymbolsUpdated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback7-moduleinmemorysymbolsupdated-method.md) callback for updates to the symbol stream associated with an in-memory module.</span></span>|  
|`COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS`|<span data-ttu-id="66506-112">컨트롤의 [ICorProfilerCallback9::DynamicMethodUnloaded](icorprofilercallback9-dynamicmethodunloaded-method.md) 동적 메서드가 가비지 된 시기를 나타내는 대 한 콜백을 수집 하 고 언로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="66506-112">Controls the [ICorProfilerCallback9::DynamicMethodUnloaded](icorprofilercallback9-dynamicmethodunloaded-method.md) callback for indicating when a dynamic method has been garbage collected and unloaded.</span></span> <br/> [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]|   
|`COR_PRF_HIGH_REQUIRE_PROFILE_IMAGE`|<span data-ttu-id="66506-113">프로필 향상 이미지가 필요한 모든 `COR_PRF_HIGH_MONITOR` 플래그를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="66506-113">Represents all `COR_PRF_HIGH_MONITOR` flags that require profile-enhanced images.</span></span> <span data-ttu-id="66506-114">해당 하는 `COR_PRF_REQUIRE_PROFILE_IMAGE` 플래그는 [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) 열거형.</span><span class="sxs-lookup"><span data-stu-id="66506-114">It corresponds to the `COR_PRF_REQUIRE_PROFILE_IMAGE` flag in the [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeration.</span></span>|  
|`COR_PRF_HIGH_ALLOWABLE_AFTER_ATTACH`|<span data-ttu-id="66506-115">실행 중인 앱에 프로파일러를 연결한 후에 설정할 수 있는 모든 `COR_PRF_HIGH_MONITOR` 플래그를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="66506-115">Represents all `COR_PRF_HIGH_MONITOR` flags that can be set after the profiler is attached to a running app.</span></span>|  
|`COR_PRF_HIGH_MONITOR_IMMUTABLE`|<span data-ttu-id="66506-116">초기화 중에만 설정할 수 있는 모든 `COR_PRF_HIGH_MONITOR` 플래그를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="66506-116">Represents all `COR_PRF_HIGH_MONITOR` flags that can be set only during initialization.</span></span> <span data-ttu-id="66506-117">다른 위치에서 이러한 플래그를 변경하려고 하면 오류를 나타내는 `HRESULT` 값이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="66506-117">Trying to change any of these flags elsewhere results in an `HRESULT` value that indicates failure.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="66506-118">설명</span><span class="sxs-lookup"><span data-stu-id="66506-118">Remarks</span></span>  
 <span data-ttu-id="66506-119">`COR_PRF_HIGH_MONITOR` 플래그는 함께 사용 되는 `pdwEventsHigh` 의 매개 변수는 [icorprofilerinfo5:: Geteventmask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md) 및 [icorprofilerinfo5:: Seteventmask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="66506-119">The `COR_PRF_HIGH_MONITOR` flags are used with the `pdwEventsHigh` parameter of the [ICorProfilerInfo5::GetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md) and [ICorProfilerInfo5::SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) methods.</span></span>  
  
<span data-ttu-id="66506-120">부터는 [!INCLUDE[net_v461](../../../../includes/net-v461-md.md)]의 값은 `COR_PRF_HIGH_ALLOWABLE_AFTER_ATTACH` 0에서 변경 `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED` (0x00000002).</span><span class="sxs-lookup"><span data-stu-id="66506-120">Starting with the [!INCLUDE[net_v461](../../../../includes/net-v461-md.md)], the value of the `COR_PRF_HIGH_ALLOWABLE_AFTER_ATTACH` changed from 0 to `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED` (0x00000002).</span></span> <span data-ttu-id="66506-121">해당 값을 변경할.NET Framework 4.7.2 부터는 `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED` 를 `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED | COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS`합니다.</span><span class="sxs-lookup"><span data-stu-id="66506-121">Starting with the .NET Framework 4.7.2, its value changed from `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED` to `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED | COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS`.</span></span>   

<span data-ttu-id="66506-122">`COR_PRF_HIGH_MONITOR_IMMUTABLE` 초기화 하는 동안에 설정할 수 있는 모든 플래그를 나타내는 비트 마스크 여야 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="66506-122">`COR_PRF_HIGH_MONITOR_IMMUTABLE` is intended to be a bitmask that represents all flags that can only be set during initialization.</span></span> <span data-ttu-id="66506-123">다른 곳에서 발생 한 실패 한 이러한 플래그를 변경 하려고 `HRESULT`합니다.</span><span class="sxs-lookup"><span data-stu-id="66506-123">Trying to change any of these flags elsewhere results in a failed `HRESULT`.</span></span>

## <a name="requirements"></a><span data-ttu-id="66506-124">요구 사항</span><span class="sxs-lookup"><span data-stu-id="66506-124">Requirements</span></span>  
 <span data-ttu-id="66506-125">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="66506-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="66506-126">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="66506-126">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="66506-127">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="66506-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="66506-128">**.NET framework 버전:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="66506-128">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66506-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="66506-129">See Also</span></span>  
 [<span data-ttu-id="66506-130">프로파일링 열거형</span><span class="sxs-lookup"><span data-stu-id="66506-130">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)  
 [<span data-ttu-id="66506-131">COR_PRF_MONITOR 열거형</span><span class="sxs-lookup"><span data-stu-id="66506-131">COR_PRF_MONITOR Enumeration</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md)  
 [<span data-ttu-id="66506-132">ICorProfilerInfo5 인터페이스</span><span class="sxs-lookup"><span data-stu-id="66506-132">ICorProfilerInfo5 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md)
