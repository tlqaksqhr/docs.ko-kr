---
title: "ICLRStrongName::StrongNameHashSize 메서드"
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
- ICLRStrongName.StrongNameHashSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameHashSize
helpviewer_keywords:
- ICLRStrongName::StrongNameHashSize method [.NET Framework hosting]
- StrongNameHashSize method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 4a05ee56-08e4-4f3a-86a9-9b52083d5c0f
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: acc2812567ce2d47d3f06c000fc387708c2e8acb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="iclrstrongnamestrongnamehashsize-method"></a><span data-ttu-id="bf0ab-102">ICLRStrongName::StrongNameHashSize 메서드</span><span class="sxs-lookup"><span data-stu-id="bf0ab-102">ICLRStrongName::StrongNameHashSize Method</span></span>
<span data-ttu-id="bf0ab-103">지정된 된 해시 알고리즘을 사용 하 여 해시에 필요한 버퍼 크기를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="bf0ab-103">Gets the buffer size required for a hash, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf0ab-104">구문</span><span class="sxs-lookup"><span data-stu-id="bf0ab-104">Syntax</span></span>  
  
```  
HRESULT StrongNameHashSize (  
    [in]  ULONG   ulHashAlg,  
    [out] DWORD   *pcbSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bf0ab-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="bf0ab-105">Parameters</span></span>  
 `ulHashAlg`  
 <span data-ttu-id="bf0ab-106">[in] 버퍼 크기를 계산 하는 데 사용 되는 해시 알고리즘입니다.</span><span class="sxs-lookup"><span data-stu-id="bf0ab-106">[in] The hash algorithm used to compute the buffer size.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="bf0ab-107">[out] 반환 된 버퍼 크기 (바이트)에서입니다.</span><span class="sxs-lookup"><span data-stu-id="bf0ab-107">[out] The returned buffer size, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bf0ab-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="bf0ab-108">Return Value</span></span>  
 <span data-ttu-id="bf0ab-109">`S_OK`메서드가 성공적으로 완료 하는 경우 그렇지 않으면 실패를 나타내는 HRESULT 값 (참조 [일반적인 HRESULT 값](http://go.microsoft.com/fwlink/?LinkId=213878) 목록에 대 한).</span><span class="sxs-lookup"><span data-stu-id="bf0ab-109">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bf0ab-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bf0ab-110">Requirements</span></span>  
 <span data-ttu-id="bf0ab-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="bf0ab-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bf0ab-112">**헤더:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="bf0ab-112">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="bf0ab-113">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="bf0ab-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bf0ab-114">**.NET framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bf0ab-114">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf0ab-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bf0ab-115">See Also</span></span>  
 [<span data-ttu-id="bf0ab-116">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bf0ab-116">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
