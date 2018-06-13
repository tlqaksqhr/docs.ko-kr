---
title: MALLOC_TYPE 열거형
ms.date: 03/30/2017
api_name:
- MALLOC_TYPE
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- MALLOC_TYPE
helpviewer_keywords:
- MALLOC_TYPE Enumeration
ms.assetid: c02476f9-23a2-4af7-9282-aa9c42c7429b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2c5e970a1677b1e43821cce9985e32ebd0726686
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33442542"
---
# <a name="malloctype-enumeration"></a><span data-ttu-id="98eee-102">MALLOC_TYPE 열거형</span><span class="sxs-lookup"><span data-stu-id="98eee-102">MALLOC_TYPE Enumeration</span></span>
<span data-ttu-id="98eee-103">할당 된 메모리의 특성을 지정 하는 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="98eee-103">Contains values that specify the characteristics of the memory that is being allocated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98eee-104">구문</span><span class="sxs-lookup"><span data-stu-id="98eee-104">Syntax</span></span>  
  
```  
typedef enum {  
    MALLOC_THREADSAFE = 0x1,  
    MALLOC_EXECUTABLE = 0x2,  
} MALLOC_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="98eee-105">멤버</span><span class="sxs-lookup"><span data-stu-id="98eee-105">Members</span></span>  
  
|<span data-ttu-id="98eee-106">멤버</span><span class="sxs-lookup"><span data-stu-id="98eee-106">Member</span></span>|<span data-ttu-id="98eee-107">설명</span><span class="sxs-lookup"><span data-stu-id="98eee-107">Description</span></span>|  
|------------|-----------------|  
|`MALLOC_EXECUTABLE`|<span data-ttu-id="98eee-108">할당 된 메모리는 실행 파일을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98eee-108">The allocated memory can contain an executable file.</span></span>|  
|`MALLOC_THREADSAFE`|<span data-ttu-id="98eee-109">할당 된 메모리는 스레드로부터 안전 합니다.</span><span class="sxs-lookup"><span data-stu-id="98eee-109">The allocated memory is thread-safe.</span></span> <span data-ttu-id="98eee-110">즉, 메모리 동기화 하지 않고도 여러 스레드에서 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98eee-110">That is, the memory can be accessed by multiple threads without any synchronization.</span></span><br /><br /> <span data-ttu-id="98eee-111">이 플래그를 설정 하지 않으면 개체에 대 한 호출이 직렬화 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="98eee-111">If this flag is not set, calls on the object must be serialized.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="98eee-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="98eee-112">Requirements</span></span>  
 <span data-ttu-id="98eee-113">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="98eee-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="98eee-114">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="98eee-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="98eee-115">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="98eee-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="98eee-116">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="98eee-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98eee-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="98eee-117">See Also</span></span>  
 [<span data-ttu-id="98eee-118">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="98eee-118">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
