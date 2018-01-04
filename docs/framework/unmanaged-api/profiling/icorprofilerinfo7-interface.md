---
title: "ICorProfilerInfo7 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cf37c462-73c5-412a-a7f8-bb26ca746313
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 13282bec74df5e6159148aa4fbe92a84d035e044
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo7-interface"></a><span data-ttu-id="3c3d7-102">ICorProfilerInfo7 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3c3d7-102">ICorProfilerInfo7 Interface</span></span>
<span data-ttu-id="3c3d7-103">[[!INCLUDE[net_v461](../../../../includes/net-v461-md.md)] 이상 버전에서 지원됨]</span><span class="sxs-lookup"><span data-stu-id="3c3d7-103">[Supported in the [!INCLUDE[net_v461](../../../../includes/net-v461-md.md)] and later versions]</span></span>  
  
 <span data-ttu-id="3c3d7-104">서브 클래스 [ICorProfilerInfo6](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-interface.md) 를 제공 하는 모듈에 정의 된 메타 데이터가 새로 적용할 방법을 메모리 기호 스트림에 대 한 액세스를 제공 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c3d7-104">A subclass of [ICorProfilerInfo6](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-interface.md) that provides a method to apply newly defined metadata to a module and that provides access to an in-memory symbol stream.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3c3d7-105">메서드</span><span class="sxs-lookup"><span data-stu-id="3c3d7-105">Methods</span></span>  
  
|<span data-ttu-id="3c3d7-106">메서드</span><span class="sxs-lookup"><span data-stu-id="3c3d7-106">Method</span></span>|<span data-ttu-id="3c3d7-107">설명</span><span class="sxs-lookup"><span data-stu-id="3c3d7-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3c3d7-108">ApplyMetaData 메서드</span><span class="sxs-lookup"><span data-stu-id="3c3d7-108">ApplyMetaData Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-applymetadata-method.md)|<span data-ttu-id="3c3d7-109">새로 정의한 메타 데이터에 적용 되는 `IMetadataEmit::Define*` 메서드를 지정된 된 모듈입니다.</span><span class="sxs-lookup"><span data-stu-id="3c3d7-109">Applies the metadata newly defined by the `IMetadataEmit::Define*` methods to a specified module.</span></span>|  
|[<span data-ttu-id="3c3d7-110">GetInMemorySymbolsLength 메서드</span><span class="sxs-lookup"><span data-stu-id="3c3d7-110">GetInMemorySymbolsLength Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-getinmemorysymbolslength-method.md)|<span data-ttu-id="3c3d7-111">메모리 내 기호 스트림의 길이 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="3c3d7-111">Returns the length of an in-memory symbol stream.</span></span>|  
|[<span data-ttu-id="3c3d7-112">ReadInMemorySymbols</span><span class="sxs-lookup"><span data-stu-id="3c3d7-112">ReadInMemorySymbols</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-readinmemorysymbols.md)|<span data-ttu-id="3c3d7-113">메모리 내 기호 스트림에서 바이트를 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="3c3d7-113">Reads bytes from an in-memory symbol stream.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3c3d7-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3c3d7-114">Requirements</span></span>  
 <span data-ttu-id="3c3d7-115">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3c3d7-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c3d7-116">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3c3d7-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3c3d7-117">**.NET Framework 버전:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c3d7-117">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c3d7-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3c3d7-118">See Also</span></span>  
 [<span data-ttu-id="3c3d7-119">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3c3d7-119">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
