---
title: "ICorProfilerObjectEnum::GetCount 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorProfilerObjectEnum.GetCount
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerObjectEnum::GetCount
helpviewer_keywords:
- ICorProfilerObjectEnum::GetCount method [.NET Framework profiling]
- GetCount method, ICorProfilerObjectEnum interface [.NET Framework profiling]
ms.assetid: 166b0761-ed80-4ccd-9973-dc20e61bf8fa
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b7675749a132cffe284d73bab3dba91f6ff7a3fc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerobjectenumgetcount-method"></a><span data-ttu-id="e0a21-102">ICorProfilerObjectEnum::GetCount 메서드</span><span class="sxs-lookup"><span data-stu-id="e0a21-102">ICorProfilerObjectEnum::GetCount Method</span></span>
<span data-ttu-id="e0a21-103">컬렉션에서 고정된 개체의 총 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e0a21-103">Gets the total number of frozen objects in the collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0a21-104">구문</span><span class="sxs-lookup"><span data-stu-id="e0a21-104">Syntax</span></span>  
  
```  
HRESULT GetCount (  
    [out] ULONG   *pcelt  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e0a21-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e0a21-105">Parameters</span></span>  
 `pcelt`  
 <span data-ttu-id="e0a21-106">[out] 컬렉션에서 고정 된 개체 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e0a21-106">[out] A pointer to the number of frozen objects in the collection.</span></span>  
  
 <span data-ttu-id="e0a21-107">이 메서드는.NET Framework 버전 3.5에서에서 0이 항상 반환 서비스 팩 1 (SP1) 및 이상 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="e0a21-107">This method will always return zero in the .NET Framework version 3.5 Service Pack 1 (SP1) and later versions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0a21-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e0a21-108">Requirements</span></span>  
 <span data-ttu-id="e0a21-109">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e0a21-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e0a21-110">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e0a21-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e0a21-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e0a21-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e0a21-112">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e0a21-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0a21-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e0a21-113">See Also</span></span>  
 [<span data-ttu-id="e0a21-114">ICorProfilerObjectEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e0a21-114">ICorProfilerObjectEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md)
