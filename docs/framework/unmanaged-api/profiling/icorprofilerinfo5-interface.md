---
title: ICorProfilerInfo5 인터페이스
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo5
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: 7bd48c34-37ed-4230-9eec-39a17280f05d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4ba082182ec7e2f639ef94baeb29203ee792fba0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33455330"
---
# <a name="icorprofilerinfo5-interface"></a><span data-ttu-id="22d7f-102">ICorProfilerInfo5 인터페이스</span><span class="sxs-lookup"><span data-stu-id="22d7f-102">ICorProfilerInfo5 Interface</span></span>
<span data-ttu-id="22d7f-103">[.NET Framework 4.5.2 이상 버전에서 지원됨]</span><span class="sxs-lookup"><span data-stu-id="22d7f-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="22d7f-104">서브 클래스 [ICorProfilerInfo4](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md) 코드 프로파일러가 공용 언어 런타임 (CLR) 이벤트 모니터링을 제어 하려면와 통신 하 여 사용할 메서드를 제공 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="22d7f-104">A subclass of [ICorProfilerInfo4](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md) that provides methods for use by code profilers to communicate with the common language runtime (CLR) to control event monitoring.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="22d7f-105">메서드</span><span class="sxs-lookup"><span data-stu-id="22d7f-105">Methods</span></span>  
  
|<span data-ttu-id="22d7f-106">메서드</span><span class="sxs-lookup"><span data-stu-id="22d7f-106">Method</span></span>|<span data-ttu-id="22d7f-107">설명</span><span class="sxs-lookup"><span data-stu-id="22d7f-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="22d7f-108">GetEventMask2 메서드</span><span class="sxs-lookup"><span data-stu-id="22d7f-108">GetEventMask2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md)|<span data-ttu-id="22d7f-109">프로파일러가 CLR에서 알림을 받으려는 현재 이벤트 범주를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="22d7f-109">Gets the current event categories for which the profiler wants to receive notifications from the CLR.</span></span>|  
|[<span data-ttu-id="22d7f-110">SetEventMask2 메서드</span><span class="sxs-lookup"><span data-stu-id="22d7f-110">SetEventMask2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md)|<span data-ttu-id="22d7f-111">프로파일러가 CLR에서 이벤트 알림을 받으려는 이벤트 형식을 지정하는 값을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="22d7f-111">Sets a value that specifies the types of events for which the profiler wants to receive event notifications from the CLR.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="22d7f-112">설명</span><span class="sxs-lookup"><span data-stu-id="22d7f-112">Remarks</span></span>  
 <span data-ttu-id="22d7f-113">이 인터페이스에서 사용할 수 있는 방법을 대체 하기 위한 됩니다는 [icorprofilerinfo:: Geteventmask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md) 및 [icorprofilerinfo:: Seteventmask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="22d7f-113">The methods available on this interface are intended to replace the [ICorProfilerInfo::GetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md) and [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="22d7f-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="22d7f-114">Requirements</span></span>  
 <span data-ttu-id="22d7f-115">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="22d7f-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="22d7f-116">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="22d7f-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="22d7f-117">**.NET framework 버전:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="22d7f-117">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22d7f-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="22d7f-118">See Also</span></span>  
 [<span data-ttu-id="22d7f-119">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="22d7f-119">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
