---
title: CertFreeAuthenticodeSignerInfo 함수
ms.date: 03/30/2017
api_name:
- CertFreeAuthenticodeSignerInfo
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: 8029633c-b6e4-4665-a7c2-89607c3247ef
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 84f15dc49d14e781f69d0f9da8f314eb71d8c034
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33401618"
---
# <a name="certfreeauthenticodesignerinfo-function"></a><span data-ttu-id="54392-102">CertFreeAuthenticodeSignerInfo 함수</span><span class="sxs-lookup"><span data-stu-id="54392-102">CertFreeAuthenticodeSignerInfo Function</span></span>
<span data-ttu-id="54392-103">에 할당 된 리소스를 해제는 [AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md) 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="54392-103">Frees resources allocated for the [AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54392-104">구문</span><span class="sxs-lookup"><span data-stu-id="54392-104">Syntax</span></span>  
  
```  
HRESULT CertFreeAuthenticodeSignerInfo (  
    [in, out]  PAXL_AUTHENTICODE_SIGNER_INFO   pSignerInfo);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="54392-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="54392-105">Parameters</span></span>  
 `pSignerInfo`  
 <span data-ttu-id="54392-106">[in, out] 해제할 서명자 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="54392-106">[in, out] Signer information to be released.</span></span> <span data-ttu-id="54392-107">참조는 [AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md) 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="54392-107">See the [AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md) structure.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="54392-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="54392-108">Return Value</span></span>  
 <span data-ttu-id="54392-109">함수가 정상적으로 실행되는 경우 `S_OK`입니다.</span><span class="sxs-lookup"><span data-stu-id="54392-109">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="54392-110">그러지 않으면 오류 코드가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="54392-110">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54392-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="54392-111">See Also</span></span>  
 [<span data-ttu-id="54392-112">Authenticode</span><span class="sxs-lookup"><span data-stu-id="54392-112">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
