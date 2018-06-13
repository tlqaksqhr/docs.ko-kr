---
title: CorDebugNGenPolicy 열거형
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- CorDebugNGenPolicy
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugNGenPolicy
helpviewer_keywords:
- CorDebugNgenPolicy enumeration [.NET Framework debugging]
ms.assetid: edb4e4d2-3166-44d4-8b17-bf302f7ea093
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cc5a06e6b3cc1e9338d860cdb110bf7d516080be
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33404026"
---
# <a name="cordebugngenpolicy-enumeration"></a><span data-ttu-id="25596-102">CorDebugNGenPolicy 열거형</span><span class="sxs-lookup"><span data-stu-id="25596-102">CorDebugNGenPolicy Enumeration</span></span>
<span data-ttu-id="25596-103">디버거가 네이티브 이미지 캐시에서 네이티브(NGen) 이미지를 로드하는지 여부를 결정하는 값을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="25596-103">Provides a value that determines whether a debugger loads native (NGen) images from the native image cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25596-104">구문</span><span class="sxs-lookup"><span data-stu-id="25596-104">Syntax</span></span>  
  
```cpp
enum CorDebugNGENPolicy {  
    DISABLE_LOCAL_NIC = 1  
} CorDebugNGENPolicy;  
```  
  
## <a name="members"></a><span data-ttu-id="25596-105">멤버</span><span class="sxs-lookup"><span data-stu-id="25596-105">Members</span></span>  
  
|<span data-ttu-id="25596-106">멤버 이름</span><span class="sxs-lookup"><span data-stu-id="25596-106">Member name</span></span>|<span data-ttu-id="25596-107">설명</span><span class="sxs-lookup"><span data-stu-id="25596-107">Description</span></span>|  
|-----------------|-----------------|  
|`DISABLE_LOCAL_NIC`|<span data-ttu-id="25596-108">에 [!INCLUDE[win8_appname_long](../../../../includes/win8-appname-long-md.md)] 로컬 네이티브 이미지 캐시에서 이미지를 사용 하는 응용 프로그램을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="25596-108">In a [!INCLUDE[win8_appname_long](../../../../includes/win8-appname-long-md.md)] app, the use of images from the local native image cache is disabled.</span></span> <span data-ttu-id="25596-109">데스크톱 앱에서이 설정은 효과가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="25596-109">In a desktop app, this setting has no effect.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="25596-110">설명</span><span class="sxs-lookup"><span data-stu-id="25596-110">Remarks</span></span>  
 <span data-ttu-id="25596-111">`CorDebugNGENPolicy` 열거형에서 사용 되는 [icordebugprocess5:: Enablengenpolicy](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enablengenpolicy-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="25596-111">The `CorDebugNGENPolicy` enumeration is used by the [ICorDebugProcess5::EnableNGENPolicy](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enablengenpolicy-method.md) method.</span></span> <span data-ttu-id="25596-112">로컬 네이티브 이미지 캐시에서 이미지를 사용할 수는 디버거가 네이티브 이미지를 최적화 하는 대신 디버깅 가능한 JIT 컴파일된 이미지를 로드 하 여 일관 된 디버깅 환경을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="25596-112">Disabling the use of images from the local native image cache provides for a consistent debugging experience by ensuring that the debugger loads debuggable JIT-compiled images instead of optimized native images.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="25596-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="25596-113">Requirements</span></span>  
 <span data-ttu-id="25596-114">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="25596-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="25596-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="25596-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="25596-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="25596-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="25596-117">**.NET framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="25596-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25596-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="25596-118">See Also</span></span>  
 [<span data-ttu-id="25596-119">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="25596-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
