---
title: "IHostTaskManager::GetStackGuarantee 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostTaskManager.GetStackGuarantee
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostTaskManager::GetStackGuarantee
helpviewer_keywords:
- GetStackGuarantee method [.NET Framework hosting]
- IHostTaskManager::GetStackGuarantee method [.NET Framework hosting]
ms.assetid: 8176d732-c25c-4520-811d-e3310f339947
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 691eaa2bd462af5fff0b222e991c13032ddb1af1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="ihosttaskmanagergetstackguarantee-method"></a><span data-ttu-id="c67f4-102">IHostTaskManager::GetStackGuarantee 메서드</span><span class="sxs-lookup"><span data-stu-id="c67f4-102">IHostTaskManager::GetStackGuarantee Method</span></span>
<span data-ttu-id="c67f4-103">스택 공간이 스택 작업이 완료 된 후 사용 가능 하도록 보장 하지만 프로세스의 닫기 전에 크기를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c67f4-103">Gets the amount of stack space that is guaranteed to be available after a stack operation completes, but before the closing of a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c67f4-104">구문</span><span class="sxs-lookup"><span data-stu-id="c67f4-104">Syntax</span></span>  
  
```  
HRESULT GetStackGuarantee(  
    [out] ULONG *pGuarantee  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c67f4-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c67f4-105">Parameters</span></span>  
 `pGuarantee`  
 <span data-ttu-id="c67f4-106">[out] 사용할 수 있는 바이트 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c67f4-106">[out] A pointer to the number of bytes that are available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c67f4-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c67f4-107">Requirements</span></span>  
 <span data-ttu-id="c67f4-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c67f4-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c67f4-109">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c67f4-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c67f4-110">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="c67f4-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c67f4-111">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c67f4-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c67f4-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c67f4-112">See Also</span></span>  
 [<span data-ttu-id="c67f4-113">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c67f4-113">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
