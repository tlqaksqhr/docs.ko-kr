---
title: "IHostTask::Start 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostTask.Start
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostTask::Start
helpviewer_keywords:
- IHostTask::Start method [.NET Framework hosting]
- Start method, IHostTask interface [.NET Framework hosting]
ms.assetid: b18742b0-d8c4-401c-ae89-e6eccdaa81d0
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f1a289099245228b8806639cb98f579bc56317b0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ihosttaskstart-method"></a><span data-ttu-id="fbcb0-102">IHostTask::Start 메서드</span><span class="sxs-lookup"><span data-stu-id="fbcb0-102">IHostTask::Start Method</span></span>
<span data-ttu-id="fbcb0-103">호스트 작업 요청 현재 [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) 코드를 실행할 수 있는 라이브 상태로 인스턴스를 일시 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbcb0-103">Requests that the host move the task represented by the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance from a suspended to a live state, in which code can be executed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fbcb0-104">구문</span><span class="sxs-lookup"><span data-stu-id="fbcb0-104">Syntax</span></span>  
  
```  
HRESULT Start ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="fbcb0-105">반환 값</span><span class="sxs-lookup"><span data-stu-id="fbcb0-105">Return Value</span></span>  
  
|<span data-ttu-id="fbcb0-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fbcb0-106">HRESULT</span></span>|<span data-ttu-id="fbcb0-107">설명</span><span class="sxs-lookup"><span data-stu-id="fbcb0-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fbcb0-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="fbcb0-108">S_OK</span></span>|<span data-ttu-id="fbcb0-109">시작 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fbcb0-109">Start returned successfully.</span></span>|  
|<span data-ttu-id="fbcb0-110">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="fbcb0-110">E_FAIL</span></span>|<span data-ttu-id="fbcb0-111">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="fbcb0-111">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="fbcb0-112">메서드가 E_FAIL을 반환 하는 경우 공용 언어 런타임 (CLR)을 하는 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fbcb0-112">When a method returns E_FAIL, the common language runtime (CLR) is no longer usable within the process.</span></span> <span data-ttu-id="fbcb0-113">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbcb0-113">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fbcb0-114">설명</span><span class="sxs-lookup"><span data-stu-id="fbcb0-114">Remarks</span></span>  
 <span data-ttu-id="fbcb0-115">`Start`항상에 치명적인 오류가 발생 한 위치를 제외 하 고 s_ok이 고, HRESULT 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbcb0-115">`Start` always returns an HRESULT value of S_OK, except in cases where a catastrophic failure has occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fbcb0-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fbcb0-116">Requirements</span></span>  
 <span data-ttu-id="fbcb0-117">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fbcb0-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fbcb0-118">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="fbcb0-118">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fbcb0-119">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="fbcb0-119">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fbcb0-120">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fbcb0-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fbcb0-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fbcb0-121">See Also</span></span>  
 [<span data-ttu-id="fbcb0-122">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fbcb0-122">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="fbcb0-123">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fbcb0-123">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="fbcb0-124">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fbcb0-124">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="fbcb0-125">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fbcb0-125">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
