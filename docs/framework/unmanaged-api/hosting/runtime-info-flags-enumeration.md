---
title: "RUNTIME_INFO_FLAGS 열거형"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: RUNTIME_INFO_FLAGS
api_location: mscoree.dll
api_type: COM
f1_keywords: RUNTIME_INFO_FLAGS
helpviewer_keywords: RUNTIME_INFO_FLAGS enumeration [.NET Framework hosting]
ms.assetid: adba37be-f775-4cdb-8919-5746ce694f33
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 697111efbb4e3f705c881ec677f781b6e3e6959d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="runtimeinfoflags-enumeration"></a><span data-ttu-id="cab39-102">RUNTIME_INFO_FLAGS 열거형</span><span class="sxs-lookup"><span data-stu-id="cab39-102">RUNTIME_INFO_FLAGS Enumeration</span></span>
<span data-ttu-id="cab39-103">공용 언어 런타임 (CLR)에 대 한 정보를 반환 하는지를 나타내는 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="cab39-103">Contains values that indicate what information about the common language runtime (CLR) should be returned.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cab39-104">구문</span><span class="sxs-lookup"><span data-stu-id="cab39-104">Syntax</span></span>  
  
```  
typedef enum {  
  
    RUNTIME_INFO_UPGRADE_VERSION             = 0x01,  
    RUNTIME_INFO_REQUEST_IA64                = 0x02,  
    RUNTIME_INFO_REQUEST_AMD64               = 0x04,  
    RUNTIME_INFO_REQUEST_X86                 = 0x08,  
    RUNTIME_INFO_DONT_RETURN_DIRECTORY       = 0x10,  
    RUNTIME_INFO_DONT_RETURN_VERSION         = 0x20,  
    RUNTIME_INFO_DONT_SHOW_ERROR_DIALOG      = 0x40,  
    RUNTIME_INFO_IGNORE_ERROR_MODE           = 0x1000  
  
} RUNTIME_INFO_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="cab39-105">멤버</span><span class="sxs-lookup"><span data-stu-id="cab39-105">Members</span></span>  
  
|<span data-ttu-id="cab39-106">멤버</span><span class="sxs-lookup"><span data-stu-id="cab39-106">Member</span></span>|<span data-ttu-id="cab39-107">설명</span><span class="sxs-lookup"><span data-stu-id="cab39-107">Description</span></span>|  
|------------|-----------------|  
|`RUNTIME_INFO_DONT_RETURN_DIRECTORY`|<span data-ttu-id="cab39-108">디렉터리 정보를 포함 하지 않아야 있는지 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="cab39-108">Indicates that directory information should not be included.</span></span>|  
|`RUNTIME_INFO_DONT_RETURN_VERSION`|<span data-ttu-id="cab39-109">버전 정보를 포함 하지 않아야 있는지 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="cab39-109">Indicates that version information should not be included.</span></span>|  
|`RUNTIME_INFO_DONT_SHOW_ERROR_DIALOG`|<span data-ttu-id="cab39-110">실패 시 오류 대화 상자를 표시 되지 않음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="cab39-110">Indicates that an error dialog box should not be shown upon failure.</span></span>|  
|`RUNTIME_INFO_IGNORE_ERROR_MODE`|<span data-ttu-id="cab39-111">나타냅니다 호출의 효과 [SetErrorMode](http://go.microsoft.com/fwlink/p/?LinkId=255242) SEM_FAILCRITICALERRORS 플래그로 함수를 재정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cab39-111">Indicates that the effects of calling the [SetErrorMode](http://go.microsoft.com/fwlink/p/?LinkId=255242) function with the SEM_FAILCRITICALERRORS flag should be overridden.</span></span> <span data-ttu-id="cab39-112">즉, 설치 대화 상자가 표시 되지 않고 오류 발생 시 표시 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cab39-112">That is, an installation dialog box should be shown upon failure, instead of being suppressed.</span></span>|  
|`RUNTIME_INFO_REQUEST_AMD64`|<span data-ttu-id="cab39-113">런타임의 AMD 호환 버전에 대 한 정보에 대 한 요청을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="cab39-113">Indicates a request for information about an AMD-64-compatible version of the runtime.</span></span>|  
|`RUNTIME_INFO_REQUEST_IA64`|<span data-ttu-id="cab39-114">런타임의 IA 호환 버전에 대 한 정보에 대 한 요청을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="cab39-114">Indicates a request for information about an IA-64-compatible version of the runtime.</span></span>|  
|`RUNTIME_INFO_REQUEST_X86`|<span data-ttu-id="cab39-115">런타임의 x86 호환 버전에 대 한 정보에 대 한 요청을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="cab39-115">Indicates a request for information about an x86-compatible version of the runtime.</span></span>|  
|`RUNTIME_INFO_UPGRADE_VERSION`|<span data-ttu-id="cab39-116">버전 업그레이드 정보를 포함 해야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="cab39-116">Indicates that version upgrade information should be included.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cab39-117">설명</span><span class="sxs-lookup"><span data-stu-id="cab39-117">Remarks</span></span>  
 <span data-ttu-id="cab39-118">다음 플랫폼 아키텍처 플래그 한 번에 하나만 지정된 될 수 있습니다 및 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cab39-118">The following platform architecture flags can be specified only one at a time and cannot be combined:</span></span>  
  
-   <span data-ttu-id="cab39-119">RUNTIME_INFO_REQUEST_IA64</span><span class="sxs-lookup"><span data-stu-id="cab39-119">RUNTIME_INFO_REQUEST_IA64</span></span>  
  
-   <span data-ttu-id="cab39-120">RUNTIME_INFO_REQUEST_AMD64</span><span class="sxs-lookup"><span data-stu-id="cab39-120">RUNTIME_INFO_REQUEST_AMD64</span></span>  
  
-   <span data-ttu-id="cab39-121">RUNTIME_INFO_REQUEST_X86</span><span class="sxs-lookup"><span data-stu-id="cab39-121">RUNTIME_INFO_REQUEST_X86</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cab39-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cab39-122">Requirements</span></span>  
 <span data-ttu-id="cab39-123">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="cab39-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cab39-124">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="cab39-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cab39-125">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="cab39-125">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cab39-126">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cab39-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cab39-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cab39-127">See Also</span></span>  
 [<span data-ttu-id="cab39-128">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="cab39-128">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
