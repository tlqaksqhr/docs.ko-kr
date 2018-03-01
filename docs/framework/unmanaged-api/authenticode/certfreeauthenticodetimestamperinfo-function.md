---
title: "CertFreeAuthenticodeTimestamperInfo 함수"
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
- CertFreeAuthenticodeTimestamperInfo
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: 3eb14c49-68c2-4516-ac89-e5bd7473831c
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 353bba880cfa8a5ecf9ed826fbb529e31f790a12
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="certfreeauthenticodetimestamperinfo-function"></a><span data-ttu-id="b5e0b-102">CertFreeAuthenticodeTimestamperInfo 함수</span><span class="sxs-lookup"><span data-stu-id="b5e0b-102">CertFreeAuthenticodeTimestamperInfo Function</span></span>
<span data-ttu-id="b5e0b-103">에 할당 된 리소스를 해제는 [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="b5e0b-103">Frees resources allocated for the [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5e0b-104">구문</span><span class="sxs-lookup"><span data-stu-id="b5e0b-104">Syntax</span></span>  
  
```  
HRESULT CertFreeAuthenticodeTimestamperInfo (  
    [in, out]  PAXL_AUTHENTICODE_TIMESTAMPER_INFO   pTimestamperInfo  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b5e0b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b5e0b-105">Parameters</span></span>  
 `pTimestamperInfo`  
 <span data-ttu-id="b5e0b-106">[in, out] 해제할 타임스탬퍼 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="b5e0b-106">[in, out] The time stamper information to be released.</span></span> <span data-ttu-id="b5e0b-107">참조는 [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="b5e0b-107">See the [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) structure.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b5e0b-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="b5e0b-108">Return Value</span></span>  
 <span data-ttu-id="b5e0b-109">함수가 정상적으로 실행되는 경우 `S_OK`입니다.</span><span class="sxs-lookup"><span data-stu-id="b5e0b-109">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="b5e0b-110">그러지 않으면 오류 코드가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="b5e0b-110">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5e0b-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b5e0b-111">See Also</span></span>  
 [<span data-ttu-id="b5e0b-112">Authenticode</span><span class="sxs-lookup"><span data-stu-id="b5e0b-112">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
