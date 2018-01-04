---
title: "DestroyICeeFileGen 함수"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: DestroyICeeFileGen
api_location:
- mscoree.dll
- mscorpehost.dll
- mscorpe.dll
api_type: COM
f1_keywords: DestroyICeeFileGen
helpviewer_keywords: DestroyICeeFileGen function [.NET Framework hosting]
ms.assetid: dc1e2235-e721-4cb2-a0b8-6b0c030d7bab
topic_type: apiref
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d6c3e326aa71adc1bc9abe350cfc0528c88905cf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="destroyiceefilegen-function"></a><span data-ttu-id="842df-102">DestroyICeeFileGen 함수</span><span class="sxs-lookup"><span data-stu-id="842df-102">DestroyICeeFileGen Function</span></span>
<span data-ttu-id="842df-103">제거 프로그램 [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="842df-103">Destroys an [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) object.</span></span>  
  
 <span data-ttu-id="842df-104">이 함수에 더 이상 사용 되지는 [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="842df-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="842df-105">구문</span><span class="sxs-lookup"><span data-stu-id="842df-105">Syntax</span></span>  
  
```  
HRESULT DestroyICeeFileGen (  
    [in] ICeeFileGen  **ceeFileGen  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="842df-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="842df-106">Parameters</span></span>  
 `ceeFileGen`  
 <span data-ttu-id="842df-107">[in] `ICeeFileGen` 소멸 시킬 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="842df-107">[in] The `ICeeFileGen` object to destroy.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="842df-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="842df-108">Return Value</span></span>  
 <span data-ttu-id="842df-109">이 메서드는 표준 COM 오류 코드를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="842df-109">This method returns standard COM error codes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="842df-110">설명</span><span class="sxs-lookup"><span data-stu-id="842df-110">Remarks</span></span>  
 <span data-ttu-id="842df-111">`DestroyICeeFileGen`소멸 된 `ICeeFileGen` 하 여 만든 개체는 [CreateICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/createiceefilegen-function.md) 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="842df-111">`DestroyICeeFileGen` destroys the `ICeeFileGen` object created by the [CreateICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/createiceefilegen-function.md) function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="842df-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="842df-112">Requirements</span></span>  
 <span data-ttu-id="842df-113">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="842df-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="842df-114">**헤더:** ICeeFileGen.h</span><span class="sxs-lookup"><span data-stu-id="842df-114">**Header:** ICeeFileGen.h</span></span>  
  
 <span data-ttu-id="842df-115">**라이브러리:** MSCorPE.dll</span><span class="sxs-lookup"><span data-stu-id="842df-115">**Library:** MSCorPE.dll</span></span>  
  
 <span data-ttu-id="842df-116">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="842df-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="842df-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="842df-117">See Also</span></span>  
 [<span data-ttu-id="842df-118">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="842df-118">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
