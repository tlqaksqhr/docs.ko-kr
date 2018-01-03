---
title: "CorDebugNGenPolicy 열거형"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: cpp
api_name: CorDebugNGenPolicy
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorDebugNGenPolicy
helpviewer_keywords: CorDebugNgenPolicy enumeration [.NET Framework debugging]
ms.assetid: edb4e4d2-3166-44d4-8b17-bf302f7ea093
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 89767da7178319ed1add3dda0620062893487bfd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="cordebugngenpolicy-enumeration"></a><span data-ttu-id="ffdcf-102">CorDebugNGenPolicy 열거형</span><span class="sxs-lookup"><span data-stu-id="ffdcf-102">CorDebugNGenPolicy Enumeration</span></span>
<span data-ttu-id="ffdcf-103">디버거가 네이티브 이미지 캐시에서 네이티브(NGen) 이미지를 로드하는지 여부를 결정하는 값을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcf-103">Provides a value that determines whether a debugger loads native (NGen) images from the native image cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ffdcf-104">구문</span><span class="sxs-lookup"><span data-stu-id="ffdcf-104">Syntax</span></span>  
  
```cpp
enum CorDebugNGENPolicy {  
    DISABLE_LOCAL_NIC = 1  
} CorDebugNGENPolicy;  
```  
  
## <a name="members"></a><span data-ttu-id="ffdcf-105">멤버</span><span class="sxs-lookup"><span data-stu-id="ffdcf-105">Members</span></span>  
  
|<span data-ttu-id="ffdcf-106">멤버 이름</span><span class="sxs-lookup"><span data-stu-id="ffdcf-106">Member name</span></span>|<span data-ttu-id="ffdcf-107">설명</span><span class="sxs-lookup"><span data-stu-id="ffdcf-107">Description</span></span>|  
|-----------------|-----------------|  
|`DISABLE_LOCAL_NIC`|<span data-ttu-id="ffdcf-108">에 [!INCLUDE[win8_appname_long](../../../../includes/win8-appname-long-md.md)] 로컬 네이티브 이미지 캐시에서 이미지를 사용 하는 응용 프로그램을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcf-108">In a [!INCLUDE[win8_appname_long](../../../../includes/win8-appname-long-md.md)] app, the use of images from the local native image cache is disabled.</span></span> <span data-ttu-id="ffdcf-109">데스크톱 앱에서이 설정은 효과가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcf-109">In a desktop app, this setting has no effect.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ffdcf-110">설명</span><span class="sxs-lookup"><span data-stu-id="ffdcf-110">Remarks</span></span>  
 <span data-ttu-id="ffdcf-111">`CorDebugNGENPolicy` 열거형에서 사용 되는 [icordebugprocess5:: Enablengenpolicy](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enablengenpolicy-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="ffdcf-111">The `CorDebugNGENPolicy` enumeration is used by the [ICorDebugProcess5::EnableNGENPolicy](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enablengenpolicy-method.md) method.</span></span> <span data-ttu-id="ffdcf-112">로컬 네이티브 이미지 캐시에서 이미지를 사용할 수는 디버거가 네이티브 이미지를 최적화 하는 대신 디버깅 가능한 JIT 컴파일된 이미지를 로드 하 여 일관 된 디버깅 환경을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcf-112">Disabling the use of images from the local native image cache provides for a consistent debugging experience by ensuring that the debugger loads debuggable JIT-compiled images instead of optimized native images.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ffdcf-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ffdcf-113">Requirements</span></span>  
 <span data-ttu-id="ffdcf-114">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcf-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ffdcf-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ffdcf-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ffdcf-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ffdcf-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ffdcf-117">**.NET framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ffdcf-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffdcf-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ffdcf-118">See Also</span></span>  
 [<span data-ttu-id="ffdcf-119">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="ffdcf-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
