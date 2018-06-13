---
title: ICorProfilerInfo6 인터페이스
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo6
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: 6f2bb148-1e2b-4e45-a5a5-0ceddc40064b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: da1aab48e2eef229bb31e9443a5549c3f9fbc621
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33455304"
---
# <a name="icorprofilerinfo6-interface"></a><span data-ttu-id="a40a8-102">ICorProfilerInfo6 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a40a8-102">ICorProfilerInfo6 Interface</span></span>
<span data-ttu-id="a40a8-103">[.NET Framework 4.6 이상 버전에서 지원 됨]</span><span class="sxs-lookup"><span data-stu-id="a40a8-103">[Supported in the .NET Framework 4.6 and later versions]</span></span>  
  
 <span data-ttu-id="a40a8-104">서브 클래스 [ICorProfilerInfo5](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md) 주어진된 NGen 모듈 및 지정된 된 메서드에 인라인에 정의 된 모든 메서드에 대 한 열거자를 제공 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="a40a8-104">A subclass of [ICorProfilerInfo5](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md) that provides an enumerator for all methods that are defined in a given NGen module and inline a given method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a40a8-105">메서드</span><span class="sxs-lookup"><span data-stu-id="a40a8-105">Methods</span></span>  
  
|<span data-ttu-id="a40a8-106">메서드</span><span class="sxs-lookup"><span data-stu-id="a40a8-106">Method</span></span>|<span data-ttu-id="a40a8-107">설명</span><span class="sxs-lookup"><span data-stu-id="a40a8-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a40a8-108">ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="a40a8-108">ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-enumngenmodulemethodsinliningthismethod-method.md)|<span data-ttu-id="a40a8-109">지정 된 NGen 모듈에 속하고 지정 된 메서드의 본문에 인라인 처리 되지 않은 모든 방법에 대 한 열거자를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="a40a8-109">Returns an enumerator for all methods that belong to a given NGen module and that are inlined in the body of a given method.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a40a8-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a40a8-110">Requirements</span></span>  
 <span data-ttu-id="a40a8-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a40a8-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a40a8-112">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a40a8-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a40a8-113">**.NET framework 버전:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a40a8-113">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a40a8-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a40a8-114">See Also</span></span>  
 [<span data-ttu-id="a40a8-115">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a40a8-115">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
