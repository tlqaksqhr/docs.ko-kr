---
title: COR_PRF_MISC 열거형
ms.date: 03/30/2017
api_name:
- COR_PRF_MISC
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_MISC
helpviewer_keywords:
- COR_PRF_MISC enumeration [.NET Framework profiling]
ms.assetid: 619bb5de-e309-48b6-a3af-32d935a0ff46
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c8f4cffd718fffa9145e1082092ecec45b80a2ec
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33451061"
---
# <a name="corprfmisc-enumeration"></a><span data-ttu-id="2c9b7-102">COR_PRF_MISC 열거형</span><span class="sxs-lookup"><span data-stu-id="2c9b7-102">COR_PRF_MISC Enumeration</span></span>
<span data-ttu-id="2c9b7-103">특수 식별자를 지정하는 상수 값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="2c9b7-103">Contains constant values that specify special identifiers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c9b7-104">구문</span><span class="sxs-lookup"><span data-stu-id="2c9b7-104">Syntax</span></span>  
  
```  
typedef enum {  
    PROFILER_PARENT_UNKNOWN = 0xFFFFFFFD,  
    PROFILER_GLOBAL_CLASS   = 0xFFFFFFFE,  
    PROFILER_GLOBAL_MODULE  = 0xFFFFFFFF  
} COR_PRF_MISC;  
```  
  
## <a name="members"></a><span data-ttu-id="2c9b7-105">멤버</span><span class="sxs-lookup"><span data-stu-id="2c9b7-105">Members</span></span>  
  
|<span data-ttu-id="2c9b7-106">멤버</span><span class="sxs-lookup"><span data-stu-id="2c9b7-106">Member</span></span>|<span data-ttu-id="2c9b7-107">설명</span><span class="sxs-lookup"><span data-stu-id="2c9b7-107">Description</span></span>|  
|------------|-----------------|  
|`PROFILER_PARENT_UNKNOWN`|<span data-ttu-id="2c9b7-108">사용 되는 기본 식별자 [icorprofilerinfo:: Getmoduleinfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmoduleinfo-method.md) 어셈블리에 아직 연결 되지 않은 모듈에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c9b7-108">The default identifier used by [ICorProfilerInfo::GetModuleInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmoduleinfo-method.md) for a module that has not yet been attached to an assembly.</span></span>|  
|`PROFILER_GLOBAL_CLASS`|<span data-ttu-id="2c9b7-109">클래스에 속해 있지 않은 전역 상수에 대 한 기본 클래스 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="2c9b7-109">The default class identifier for global constants that do not belong to a class.</span></span>|  
|`PROFILER_GLOBAL_MODULE`|<span data-ttu-id="2c9b7-110">모듈에 속해 있지 않은 전역 개체에 대 한 기본 모듈 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="2c9b7-110">The default module identifier for global objects that do not belong to a module.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2c9b7-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2c9b7-111">Requirements</span></span>  
 <span data-ttu-id="2c9b7-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2c9b7-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c9b7-113">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2c9b7-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2c9b7-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2c9b7-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2c9b7-115">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2c9b7-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c9b7-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2c9b7-116">See Also</span></span>  
 [<span data-ttu-id="2c9b7-117">프로파일링 열거형</span><span class="sxs-lookup"><span data-stu-id="2c9b7-117">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
