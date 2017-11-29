---
title: "CorDebugJITCompilerFlags 열거형"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugJITCompilerFlags
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorDebugJITCompilerFlags
helpviewer_keywords: CorDebugJITCompilerFlags enumeration [.NET Framework debugging]
ms.assetid: c0774f70-5bed-45e8-9922-fdad778c4c33
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d7eb8421dcd68c67536e0de038f7038500556c47
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="cordebugjitcompilerflags-enumeration"></a><span data-ttu-id="1dc85-102">CorDebugJITCompilerFlags 열거형</span><span class="sxs-lookup"><span data-stu-id="1dc85-102">CorDebugJITCompilerFlags Enumeration</span></span>
<span data-ttu-id="1dc85-103">관리되는 JIT(Just-In-Time) 컴파일러의 동작에 영향을 주는 값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="1dc85-103">Contains values that influence the behavior of the managed just-in-time (JIT) compiler.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1dc85-104">구문</span><span class="sxs-lookup"><span data-stu-id="1dc85-104">Syntax</span></span>  
  
```  
typedef enum CorDebugJITCompilerFlags {  
  
    CORDEBUG_JIT_DEFAULT = 0x1,  
    CORDEBUG_JIT_DISABLE_OPTIMIZATION = 0x3,  
    CORDEBUG_JIT_ENABLE_ENC = 0x7  
  
} CorDebugJITCompilerFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="1dc85-105">멤버</span><span class="sxs-lookup"><span data-stu-id="1dc85-105">Members</span></span>  
  
|<span data-ttu-id="1dc85-106">멤버</span><span class="sxs-lookup"><span data-stu-id="1dc85-106">Member</span></span>|<span data-ttu-id="1dc85-107">설명</span><span class="sxs-lookup"><span data-stu-id="1dc85-107">Description</span></span>|  
|------------|-----------------|  
|`CORDEBUG_JIT_DEFAULT`|<span data-ttu-id="1dc85-108">컴파일러는 컴파일 데이터 문제를 추적 해야 하 고 최적화를 허용을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1dc85-108">Specifies that the compiler should track compilation data, and allows optimizations.</span></span>|  
|`CORDEBUG_JIT_DISABLE_OPTIMIZATION`|<span data-ttu-id="1dc85-109">컴파일러가 하지만 최적화는 비활성화 컴파일 데이터를 추적 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1dc85-109">Specifies that the compiler should track compilation data, but disables optimizations.</span></span>|  
|`CORDEBUG_JIT_ENABLE_ENC`|<span data-ttu-id="1dc85-110">컴파일러가 최적화를 비활성화 하는 컴파일 데이터를 추적 하도록 및 편집 하며 계속 하기 기술을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1dc85-110">Specifies that the compiler should track compilation data, disables optimizations, and enables Edit and Continue technologies.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1dc85-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1dc85-111">Requirements</span></span>  
 <span data-ttu-id="1dc85-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1dc85-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1dc85-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1dc85-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1dc85-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1dc85-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1dc85-115">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1dc85-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1dc85-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1dc85-116">See Also</span></span>  
 [<span data-ttu-id="1dc85-117">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="1dc85-117">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
