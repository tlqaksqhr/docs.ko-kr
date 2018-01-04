---
title: "MALLOC_TYPE 열거형"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: MALLOC_TYPE
api_location: mscoree.dll
api_type: COM
f1_keywords: MALLOC_TYPE
helpviewer_keywords: MALLOC_TYPE Enumeration
ms.assetid: c02476f9-23a2-4af7-9282-aa9c42c7429b
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b3f41f381266c76b267d5d3e366047fe5267c30b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="malloctype-enumeration"></a><span data-ttu-id="a8b46-102">MALLOC_TYPE 열거형</span><span class="sxs-lookup"><span data-stu-id="a8b46-102">MALLOC_TYPE Enumeration</span></span>
<span data-ttu-id="a8b46-103">할당 된 메모리의 특성을 지정 하는 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8b46-103">Contains values that specify the characteristics of the memory that is being allocated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8b46-104">구문</span><span class="sxs-lookup"><span data-stu-id="a8b46-104">Syntax</span></span>  
  
```  
typedef enum {  
    MALLOC_THREADSAFE = 0x1,  
    MALLOC_EXECUTABLE = 0x2,  
} MALLOC_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="a8b46-105">멤버</span><span class="sxs-lookup"><span data-stu-id="a8b46-105">Members</span></span>  
  
|<span data-ttu-id="a8b46-106">멤버</span><span class="sxs-lookup"><span data-stu-id="a8b46-106">Member</span></span>|<span data-ttu-id="a8b46-107">설명</span><span class="sxs-lookup"><span data-stu-id="a8b46-107">Description</span></span>|  
|------------|-----------------|  
|`MALLOC_EXECUTABLE`|<span data-ttu-id="a8b46-108">할당 된 메모리는 실행 파일을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8b46-108">The allocated memory can contain an executable file.</span></span>|  
|`MALLOC_THREADSAFE`|<span data-ttu-id="a8b46-109">할당 된 메모리는 스레드로부터 안전 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8b46-109">The allocated memory is thread-safe.</span></span> <span data-ttu-id="a8b46-110">즉, 메모리 동기화 하지 않고도 여러 스레드에서 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8b46-110">That is, the memory can be accessed by multiple threads without any synchronization.</span></span><br /><br /> <span data-ttu-id="a8b46-111">이 플래그를 설정 하지 않으면 개체에 대 한 호출이 직렬화 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8b46-111">If this flag is not set, calls on the object must be serialized.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a8b46-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a8b46-112">Requirements</span></span>  
 <span data-ttu-id="a8b46-113">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a8b46-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a8b46-114">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a8b46-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a8b46-115">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a8b46-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a8b46-116">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a8b46-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8b46-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a8b46-117">See Also</span></span>  
 [<span data-ttu-id="a8b46-118">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="a8b46-118">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
