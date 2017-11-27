---
title: "CertFreeAuthenticodeSignerInfo 함수"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CertFreeAuthenticodeSignerInfo
api_location: clr.dll
api_type: DLLExport
ms.assetid: 8029633c-b6e4-4665-a7c2-89607c3247ef
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f922cdba8bcfce6c9ff4543f6aea5bacfdc60ab0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="certfreeauthenticodesignerinfo-function"></a><span data-ttu-id="1af98-102">CertFreeAuthenticodeSignerInfo 함수</span><span class="sxs-lookup"><span data-stu-id="1af98-102">CertFreeAuthenticodeSignerInfo Function</span></span>
<span data-ttu-id="1af98-103">에 할당 된 리소스를 해제는 [AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md) 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="1af98-103">Frees resources allocated for the [AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1af98-104">구문</span><span class="sxs-lookup"><span data-stu-id="1af98-104">Syntax</span></span>  
  
```  
HRESULT CertFreeAuthenticodeSignerInfo (  
    [in, out]  PAXL_AUTHENTICODE_SIGNER_INFO   pSignerInfo);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1af98-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1af98-105">Parameters</span></span>  
 `pSignerInfo`  
 <span data-ttu-id="1af98-106">[in, out] 해제할 서명자 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="1af98-106">[in, out] Signer information to be released.</span></span> <span data-ttu-id="1af98-107">참조는 [AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md) 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="1af98-107">See the [AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md) structure.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1af98-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="1af98-108">Return Value</span></span>  
 <span data-ttu-id="1af98-109">함수가 정상적으로 실행되는 경우 `S_OK`입니다.</span><span class="sxs-lookup"><span data-stu-id="1af98-109">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="1af98-110">그러지 않으면 오류 코드가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="1af98-110">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1af98-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1af98-111">See Also</span></span>  
 [<span data-ttu-id="1af98-112">Authenticode</span><span class="sxs-lookup"><span data-stu-id="1af98-112">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
