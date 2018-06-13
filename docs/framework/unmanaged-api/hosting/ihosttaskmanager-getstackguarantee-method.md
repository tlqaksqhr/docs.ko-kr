---
title: IHostTaskManager::GetStackGuarantee 메서드
ms.date: 03/30/2017
api_name:
- IHostTaskManager.GetStackGuarantee
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::GetStackGuarantee
helpviewer_keywords:
- GetStackGuarantee method [.NET Framework hosting]
- IHostTaskManager::GetStackGuarantee method [.NET Framework hosting]
ms.assetid: 8176d732-c25c-4520-811d-e3310f339947
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 089aaf96a164be7eaa258dec65807bd75c998eb7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33440972"
---
# <a name="ihosttaskmanagergetstackguarantee-method"></a><span data-ttu-id="1ae3c-102">IHostTaskManager::GetStackGuarantee 메서드</span><span class="sxs-lookup"><span data-stu-id="1ae3c-102">IHostTaskManager::GetStackGuarantee Method</span></span>
<span data-ttu-id="1ae3c-103">스택 공간이 스택 작업이 완료 된 후 사용 가능 하도록 보장 하지만 프로세스의 닫기 전에 크기를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1ae3c-103">Gets the amount of stack space that is guaranteed to be available after a stack operation completes, but before the closing of a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ae3c-104">구문</span><span class="sxs-lookup"><span data-stu-id="1ae3c-104">Syntax</span></span>  
  
```  
HRESULT GetStackGuarantee(  
    [out] ULONG *pGuarantee  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1ae3c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1ae3c-105">Parameters</span></span>  
 `pGuarantee`  
 <span data-ttu-id="1ae3c-106">[out] 사용할 수 있는 바이트 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="1ae3c-106">[out] A pointer to the number of bytes that are available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1ae3c-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1ae3c-107">Requirements</span></span>  
 <span data-ttu-id="1ae3c-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1ae3c-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1ae3c-109">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1ae3c-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1ae3c-110">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="1ae3c-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1ae3c-111">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1ae3c-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ae3c-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1ae3c-112">See Also</span></span>  
 [<span data-ttu-id="1ae3c-113">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1ae3c-113">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
