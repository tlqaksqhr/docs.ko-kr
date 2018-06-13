---
title: CorDebugPlatform 열거형
ms.date: 03/30/2017
api_name:
- CorDebugPlatformEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugPlatformEnum
helpviewer_keywords:
- CorDebugPlatformEnum enumeration [.NET Framework debugging]
ms.assetid: c5444816-7378-4521-afd3-bf5e4b5303d5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7d3b8f1e869e90fd3388cc0844e608b7ff40fc89
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33407094"
---
# <a name="cordebugplatform-enumeration"></a><span data-ttu-id="8b81f-102">CorDebugPlatform 열거형</span><span class="sxs-lookup"><span data-stu-id="8b81f-102">CorDebugPlatform Enumeration</span></span>
<span data-ttu-id="8b81f-103">사용 되는 대상 플랫폼 값을 제공 된 [icordebugdatatarget:: Getplatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="8b81f-103">Provides target platform values that are used by the [ICorDebugDataTarget::GetPlatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b81f-104">구문</span><span class="sxs-lookup"><span data-stu-id="8b81f-104">Syntax</span></span>  
  
```  
typedef enum CorDebugPlatform  
{  
    CORDB_PLATFORM_WINDOWS_X86,    // Windows on Intel x86  
    CORDB_PLATFORM_WINDOWS_AMD64,  // Windows x64 (AMD64, Intel EM64T)  
    CORDB_PLATFORM_WINDOWS_IA64,   // Windows on Intel IA-64  
    CORDB_PLATFORM_MAC_PPC,        // Macintosh OS on PowerPC  
    CORDB_PLATFORM_MAC_X86,        // Macintosh OS on Intel x86  
    CORDB_PLATFORM_WINDOWS_ARM,    // Windows on ARM  
    CORDB_PLATFORM_MAC_AMD64       // MacOS on Intel x64  
} CorDebugPlatform;  
```  
  
## <a name="members"></a><span data-ttu-id="8b81f-105">멤버</span><span class="sxs-lookup"><span data-stu-id="8b81f-105">Members</span></span>  
  
|<span data-ttu-id="8b81f-106">멤버</span><span class="sxs-lookup"><span data-stu-id="8b81f-106">Member</span></span>|<span data-ttu-id="8b81f-107">설명</span><span class="sxs-lookup"><span data-stu-id="8b81f-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="8b81f-108">CORDB_PLATFORM_WINDOWS_X86</span><span class="sxs-lookup"><span data-stu-id="8b81f-108">CORDB_PLATFORM_WINDOWS_X86</span></span>|<span data-ttu-id="8b81f-109">대상 플랫폼이 Intel x86 하드웨어에서 실행되는 Windows입니다.</span><span class="sxs-lookup"><span data-stu-id="8b81f-109">The target platform is Windows running on Intel x86 hardware.</span></span>|  
|<span data-ttu-id="8b81f-110">CORDB_PLATFORM_WINDOWS_AMD64</span><span class="sxs-lookup"><span data-stu-id="8b81f-110">CORDB_PLATFORM_WINDOWS_AMD64</span></span>|<span data-ttu-id="8b81f-111">대상 플랫폼이 AMD64 또는 Intel EM64T 하드웨어에서 실행되는 64비트 Windows입니다.</span><span class="sxs-lookup"><span data-stu-id="8b81f-111">The target platform is 64 bit Windows running on AMD64 or Intel EM64T hardware.</span></span>|  
|<span data-ttu-id="8b81f-112">CORDB_PLATFORM_WINDOWS_IA64</span><span class="sxs-lookup"><span data-stu-id="8b81f-112">CORDB_PLATFORM_WINDOWS_IA64</span></span>|<span data-ttu-id="8b81f-113">대상 플랫폼이 Intel IA-64 하드웨어에서 실행되는 32비트 Windows입니다.</span><span class="sxs-lookup"><span data-stu-id="8b81f-113">The target platform is 32 bit Windows running on Intel IA-64 hardware.</span></span>|  
|<span data-ttu-id="8b81f-114">CORDB_PLATFORM_MAC_PPC</span><span class="sxs-lookup"><span data-stu-id="8b81f-114">CORDB_PLATFORM_MAC_PPC</span></span>|<span data-ttu-id="8b81f-115">대상 플랫폼이 PowerPC 하드웨어에서 실행 되는 Macintosh 운영 체제는입니다.</span><span class="sxs-lookup"><span data-stu-id="8b81f-115">The target platform is the Macintosh operating system running on PowerPC hardware.</span></span>|  
|<span data-ttu-id="8b81f-116">CORDB_PLATFORM_MAC_X86</span><span class="sxs-lookup"><span data-stu-id="8b81f-116">CORDB_PLATFORM_MAC_X86</span></span>|<span data-ttu-id="8b81f-117">대상 플랫폼이 Intel x86 하드웨어에서 실행 되는 Macintosh 운영 체제는입니다.</span><span class="sxs-lookup"><span data-stu-id="8b81f-117">The target platform is the Macintosh operating system running on Intel x86 hardware.</span></span>|  
|<span data-ttu-id="8b81f-118">CORDB_PLATFORM_WINDOWS_ARM</span><span class="sxs-lookup"><span data-stu-id="8b81f-118">CORDB_PLATFORM_WINDOWS_ARM</span></span>|<span data-ttu-id="8b81f-119">대상 플랫폼이 Windows ARM 하드웨어에서 실행 되는 Macintosh 운영 체제는입니다.</span><span class="sxs-lookup"><span data-stu-id="8b81f-119">The target platform is the Macintosh operating system running on Windows ARM hardware.</span></span>|  
|<span data-ttu-id="8b81f-120">CORDB_PLATFORM_MAC_AMD64</span><span class="sxs-lookup"><span data-stu-id="8b81f-120">CORDB_PLATFORM_MAC_AMD64</span></span>|<span data-ttu-id="8b81f-121">대상 플랫폼이 AMD64 하드웨어에서 실행 되는 Macintosh 운영 체제는입니다.</span><span class="sxs-lookup"><span data-stu-id="8b81f-121">The target platform is the Macintosh operating system running on AMD64 hardware.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8b81f-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8b81f-122">Requirements</span></span>  
 <span data-ttu-id="8b81f-123">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8b81f-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b81f-124">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8b81f-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8b81f-125">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8b81f-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8b81f-126">**.NET framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8b81f-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
 <span data-ttu-id="8b81f-127">`CORDB_PLATFORM_WINDOWS_ARM` 및 `CORDB_PLATFORM_MAC_AMD64` 멤버는 .NET Framework 4.5.2 이상 버전에서 사용 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="8b81f-127">The `CORDB_PLATFORM_WINDOWS_ARM` and `CORDB_PLATFORM_MAC_AMD64` members are available in the .NET Framework 4.5.2 and later versions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b81f-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8b81f-128">See Also</span></span>  
 [<span data-ttu-id="8b81f-129">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="8b81f-129">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
