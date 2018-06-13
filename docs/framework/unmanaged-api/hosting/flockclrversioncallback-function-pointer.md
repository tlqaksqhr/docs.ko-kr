---
title: FLockClrVersionCallback 함수 포인터
ms.date: 03/30/2017
api_name:
- FLockClrVersionCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- FLockClrVersionCallback
helpviewer_keywords:
- FLockClrVersionCallback function pointer [.NET Framework hosting]
ms.assetid: 98a4762d-9ad2-45bd-9d03-39064a028b44
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5c884d07fa35c053b1a3b65c04426ac0e3712621
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33429675"
---
# <a name="flockclrversioncallback-function-pointer"></a><span data-ttu-id="9ea5b-102">FLockClrVersionCallback 함수 포인터</span><span class="sxs-lookup"><span data-stu-id="9ea5b-102">FLockClrVersionCallback Function Pointer</span></span>
<span data-ttu-id="9ea5b-103">해당 초기화를 나타내기 위해 공용 언어 런타임 (CLR) 호출 시작 또는 완료 하는 함수를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="9ea5b-103">Points to a function that the common language runtime (CLR) calls to indicate that initialization has either started or completed.</span></span>  
  
 <span data-ttu-id="9ea5b-104">이 함수 포인터에서 더 이상 사용 되지는 [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="9ea5b-104">This function pointer has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ea5b-105">구문</span><span class="sxs-lookup"><span data-stu-id="9ea5b-105">Syntax</span></span>  
  
```  
typedef HRESULT (__stdcall *FLockClrVersionCallback) ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="9ea5b-106">설명</span><span class="sxs-lookup"><span data-stu-id="9ea5b-106">Remarks</span></span>  
 <span data-ttu-id="9ea5b-107">이 함수는 호스트에 의해 구현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ea5b-107">This function is implemented by the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ea5b-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9ea5b-108">Requirements</span></span>  
 <span data-ttu-id="9ea5b-109">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9ea5b-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ea5b-110">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9ea5b-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9ea5b-111">**라이브러리:** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="9ea5b-111">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="9ea5b-112">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ea5b-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ea5b-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9ea5b-113">See Also</span></span>  
 [<span data-ttu-id="9ea5b-114">LockClrVersion 함수</span><span class="sxs-lookup"><span data-stu-id="9ea5b-114">LockClrVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md)  
 [<span data-ttu-id="9ea5b-115">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="9ea5b-115">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
