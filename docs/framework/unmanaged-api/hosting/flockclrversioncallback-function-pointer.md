---
title: "FLockClrVersionCallback 함수 포인터"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: FLockClrVersionCallback
api_location: mscoree.dll
api_type: COM
f1_keywords: FLockClrVersionCallback
helpviewer_keywords: FLockClrVersionCallback function pointer [.NET Framework hosting]
ms.assetid: 98a4762d-9ad2-45bd-9d03-39064a028b44
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ca1b97c509ea8ed2c43c30cab278048aeb4170a7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="flockclrversioncallback-function-pointer"></a><span data-ttu-id="223e9-102">FLockClrVersionCallback 함수 포인터</span><span class="sxs-lookup"><span data-stu-id="223e9-102">FLockClrVersionCallback Function Pointer</span></span>
<span data-ttu-id="223e9-103">해당 초기화를 나타내기 위해 공용 언어 런타임 (CLR) 호출 시작 또는 완료 하는 함수를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="223e9-103">Points to a function that the common language runtime (CLR) calls to indicate that initialization has either started or completed.</span></span>  
  
 <span data-ttu-id="223e9-104">이 함수 포인터에서 더 이상 사용 되지는 [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="223e9-104">This function pointer has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="223e9-105">구문</span><span class="sxs-lookup"><span data-stu-id="223e9-105">Syntax</span></span>  
  
```  
typedef HRESULT (__stdcall *FLockClrVersionCallback) ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="223e9-106">설명</span><span class="sxs-lookup"><span data-stu-id="223e9-106">Remarks</span></span>  
 <span data-ttu-id="223e9-107">이 함수는 호스트에 의해 구현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="223e9-107">This function is implemented by the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="223e9-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="223e9-108">Requirements</span></span>  
 <span data-ttu-id="223e9-109">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="223e9-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="223e9-110">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="223e9-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="223e9-111">**라이브러리:** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="223e9-111">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="223e9-112">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="223e9-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="223e9-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="223e9-113">See Also</span></span>  
 [<span data-ttu-id="223e9-114">LockClrVersion 함수</span><span class="sxs-lookup"><span data-stu-id="223e9-114">LockClrVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md)  
 [<span data-ttu-id="223e9-115">사용 되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="223e9-115">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
