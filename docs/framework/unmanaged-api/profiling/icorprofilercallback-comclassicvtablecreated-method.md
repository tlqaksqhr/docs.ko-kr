---
title: "ICorProfilerCallback::COMClassicVTableCreated 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.COMClassicVTableCreated
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::COMClassicVTableCreated
helpviewer_keywords:
- COMClassicVTableCreated method [.NET Framework profiling]
- ICorProfilerCallback::COMClassicVTableCreated method [.NET Framework profiling]
ms.assetid: 6e1834ab-c359-498a-b10b-984ae23cdda4
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 39fa655065c2af10750b1285ef047678874723ac
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallbackcomclassicvtablecreated-method"></a><span data-ttu-id="38dcc-102">ICorProfilerCallback::COMClassicVTableCreated 메서드</span><span class="sxs-lookup"><span data-stu-id="38dcc-102">ICorProfilerCallback::COMClassicVTableCreated Method</span></span>
<span data-ttu-id="38dcc-103">지정 된 IID 및 클래스에 대 한 COM interop vtable을 만들었는지 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="38dcc-103">Notifies the profiler that a COM interop vtable for the specified IID and class has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38dcc-104">구문</span><span class="sxs-lookup"><span data-stu-id="38dcc-104">Syntax</span></span>  
  
```  
HRESULT COMClassicVTableCreated(  
    [in] ClassID wrappedClassId,  
    [in] REFGUID implementedIID,  
    [in] void    *pVTable,  
    [in] ULONG   cSlots);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="38dcc-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="38dcc-105">Parameters</span></span>  
 `wrappedClasId`  
 <span data-ttu-id="38dcc-106">[in] Vtable 생성 된 클래스의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="38dcc-106">[in] The ID of the class for which the vtable has been created.</span></span>  
  
 `implementedIID`  
 <span data-ttu-id="38dcc-107">[in] 클래스에서 구현 된 인터페이스의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="38dcc-107">[in] The ID of the interface implemented by the class.</span></span> <span data-ttu-id="38dcc-108">이 값이 인터페이스는 내부 에서만 경우 NULL이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38dcc-108">This value may be NULL if the interface is internal only.</span></span>  
  
 `pVTable`  
 <span data-ttu-id="38dcc-109">[in] Vtable의 시작 부분에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="38dcc-109">[in] A pointer to the start of the vtable.</span></span>  
  
 `cSlots`  
 <span data-ttu-id="38dcc-110">[in] Vtable에 있는 슬롯 수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="38dcc-110">[in] The number of slots that are in the vtable.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="38dcc-111">설명</span><span class="sxs-lookup"><span data-stu-id="38dcc-111">Remarks</span></span>  
 <span data-ttu-id="38dcc-112">스택 가비지 수집을 허용 하는 상태가 아닐 수 있습니다 때문에이 메서드의 구현에서 프로파일러 차단 하지 않아야 하 고 따라서 선점형 가비지 수집을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="38dcc-112">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="38dcc-113">이때 프로파일러가 차단 하는 경우 가비지 수집을 시도 하 고, 런타임이이 콜백이 반환 될 때까지 차단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38dcc-113">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="38dcc-114">이 메서드는 프로파일러 구현에는 관리 코드에 또는 관리 되는 메모리 할당에서 호출 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="38dcc-114">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="38dcc-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="38dcc-115">Requirements</span></span>  
 <span data-ttu-id="38dcc-116">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="38dcc-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38dcc-117">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="38dcc-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="38dcc-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="38dcc-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="38dcc-119">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="38dcc-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38dcc-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="38dcc-120">See Also</span></span>  
 [<span data-ttu-id="38dcc-121">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="38dcc-121">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="38dcc-122">COMClassicVTableDestroyed 메서드</span><span class="sxs-lookup"><span data-stu-id="38dcc-122">COMClassicVTableDestroyed Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-comclassicvtabledestroyed-method.md)
