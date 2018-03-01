---
title: "EMemoryAvailable 열거형"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- EMemoryAvailable
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EMemoryAvailable
helpviewer_keywords:
- EMemoryAvailable enumeration [.NET Framework hosting]
ms.assetid: 38e72a06-dbed-473b-a59b-7e0b3ea4f2af
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 596b174fa4ebac7e54e2f6b5f3ed044686fa515f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ememoryavailable-enumeration"></a><span data-ttu-id="20e5b-102">EMemoryAvailable 열거형</span><span class="sxs-lookup"><span data-stu-id="20e5b-102">EMemoryAvailable Enumeration</span></span>
<span data-ttu-id="20e5b-103">컴퓨터에서 사용 가능한 실제 메모리의 양을 나타내는 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="20e5b-103">Contains values that indicate the amount of free physical memory on the computer.</span></span> <span data-ttu-id="20e5b-104">이러한 값은 이벤트에 메모리에서 반환 되 고가 및 저가 대 한 논리적으로 매핑하는 `CreateMemoryResourceNotification` Win32 api에서 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="20e5b-104">These values logically map to the events for high and low memory returned from the `CreateMemoryResourceNotification` function in the Win32 API.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20e5b-105">구문</span><span class="sxs-lookup"><span data-stu-id="20e5b-105">Syntax</span></span>  
  
```  
typedef enum {  
    eMemoryAvailableLow     = 1,  
    eMemoryAvailableNeutral = 2,  
    eMemoryAvailableHigh    = 3   
} EMemoryAvailable;  
```  
  
## <a name="members"></a><span data-ttu-id="20e5b-106">멤버</span><span class="sxs-lookup"><span data-stu-id="20e5b-106">Members</span></span>  
  
|<span data-ttu-id="20e5b-107">멤버</span><span class="sxs-lookup"><span data-stu-id="20e5b-107">Member</span></span>|<span data-ttu-id="20e5b-108">설명</span><span class="sxs-lookup"><span data-stu-id="20e5b-108">Description</span></span>|  
|------------|-----------------|  
|`eMemoryAvailableHigh`|<span data-ttu-id="20e5b-109">충분 한 실제 메모리를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20e5b-109">Plenty of physical memory is available.</span></span>|  
|`eMemoryAvailableLow`|<span data-ttu-id="20e5b-110">매우 적은 양의 실제 메모리를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20e5b-110">Very little physical memory is available.</span></span>|  
|`eMemoryAvailableNeutral`|<span data-ttu-id="20e5b-111">사용 가능한 실제 메모리가 보통 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="20e5b-111">The available physical memory is neutral.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="20e5b-112">설명</span><span class="sxs-lookup"><span data-stu-id="20e5b-112">Remarks</span></span>  
 <span data-ttu-id="20e5b-113">에 대 한 호출을 사용 하 여 공용 언어 런타임 (CLR)를 호스트에 의해이 값은 전달 된 [iclrmemorynotificationcallback:: Onmemorynotification](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="20e5b-113">This value is passed by the host to the common language runtime (CLR) by using a call to the [ICLRMemoryNotificationCallback::OnMemoryNotification](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="20e5b-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="20e5b-114">Requirements</span></span>  
 <span data-ttu-id="20e5b-115">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="20e5b-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="20e5b-116">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="20e5b-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="20e5b-117">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="20e5b-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="20e5b-118">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="20e5b-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20e5b-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="20e5b-119">See Also</span></span>  
 [<span data-ttu-id="20e5b-120">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="20e5b-120">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
