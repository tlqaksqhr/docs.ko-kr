---
title: "ICLRDebugManager::SetSymbolReadingPolicy 메서드"
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
- ICLRDebugManager.SetSymbolReadingPolicy
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDebugManager::SetSymbolReadingPolicy
helpviewer_keywords:
- ICLRDebugManager, SetSymbolREadingPolicy method
- SetSymbolReadingPolicy method [.NET Framework hosting]
- ICLRDebugManager::SetSymbolReadingPolicy method [.NET Framework hosting]
ms.assetid: bd921fa2-d377-4d79-acfc-64c38d4dcae9
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 440bab97dc765438758abad3275bb2e4f8051da9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="iclrdebugmanagersetsymbolreadingpolicy-method"></a><span data-ttu-id="98405-102">ICLRDebugManager::SetSymbolReadingPolicy 메서드</span><span class="sxs-lookup"><span data-stu-id="98405-102">ICLRDebugManager::SetSymbolReadingPolicy Method</span></span>
<span data-ttu-id="98405-103">프로그램 데이터베이스 (PDB) 파일을 읽기 위한 정책을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="98405-103">Sets the policy for reading program database (PDB) files.</span></span> <span data-ttu-id="98405-104">정책을 호출 스택의 줄 번호와 파일에 대 한 정보 포함 되는지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="98405-104">The policy determines whether information about line numbers and files is included in call stacks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98405-105">구문</span><span class="sxs-lookup"><span data-stu-id="98405-105">Syntax</span></span>  
  
```  
HRESULT SetSymbolReadingPolicy (  
    [in] ESymbolReadingPolicy policy  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="98405-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="98405-106">Parameters</span></span>  
 `policy`  
 <span data-ttu-id="98405-107">[in] 멤버는 [ESymbolReadingPolicy](../../../../docs/framework/unmanaged-api/hosting/esymbolreadingpolicy-enumeration.md) 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="98405-107">[in] A member of the [ESymbolReadingPolicy](../../../../docs/framework/unmanaged-api/hosting/esymbolreadingpolicy-enumeration.md) enumeration.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="98405-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="98405-108">Return Value</span></span>  
  
|<span data-ttu-id="98405-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="98405-109">HRESULT</span></span>|<span data-ttu-id="98405-110">설명</span><span class="sxs-lookup"><span data-stu-id="98405-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="98405-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="98405-111">S_OK</span></span>|<span data-ttu-id="98405-112">`SetSymbolReadingPolicy`성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="98405-112">`SetSymbolReadingPolicy` returned successfully.</span></span>|  
|<span data-ttu-id="98405-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="98405-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="98405-114">공용 언어 런타임 (CLR) 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="98405-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="98405-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="98405-115">E_FAIL</span></span>|<span data-ttu-id="98405-116">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="98405-116">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="98405-117">E_FAIL을 반환 하는 메서드 후 CLR을 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="98405-117">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="98405-118">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="98405-118">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="98405-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="98405-119">Requirements</span></span>  
 <span data-ttu-id="98405-120">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="98405-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="98405-121">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="98405-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="98405-122">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="98405-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="98405-123">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="98405-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98405-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="98405-124">See Also</span></span>  
 [<span data-ttu-id="98405-125">ICLRDebugManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="98405-125">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)
