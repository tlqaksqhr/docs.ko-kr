---
title: "CertVerifyAuthenticodeLicense 함수"
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
- CertVerifyAuthenticodeLicense
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: 00118de7-33c6-41c4-8e1f-5d5e35e0da83
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: bab3a3bcee52a302345ccdcfad81e7f67efdd8d5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="certverifyauthenticodelicense-function"></a><span data-ttu-id="82ae9-102">CertVerifyAuthenticodeLicense 함수</span><span class="sxs-lookup"><span data-stu-id="82ae9-102">CertVerifyAuthenticodeLicense Function</span></span>
<span data-ttu-id="82ae9-103">Authenticode XrML 라이선스의 유효성을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="82ae9-103">Verifies the validity of an Authenticode XrML license.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82ae9-104">구문</span><span class="sxs-lookup"><span data-stu-id="82ae9-104">Syntax</span></span>  
  
```  
HRESULT CertVerifyAuthenticodeLicense (  
    [in]   PCRYPT_DATA_BLOB                   pLicenseBlob,  
    [in]   OPTIONAL DWORD                     dwFlags,  
    [out]  PAXL_AUTHENTICODE_SIGNER_INFO      pSignerInfo,  
    [out]  PAXL_AUTHENTICODE_TIMESTAMPER_INFO pTimestamperInfo  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="82ae9-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="82ae9-105">Parameters</span></span>  
 `pLicenseBlob`  
 <span data-ttu-id="82ae9-106">[in] 확인할 Authenticode XrML 라이선스입니다.</span><span class="sxs-lookup"><span data-stu-id="82ae9-106">[in] The Authenticode XrML license to be verified.</span></span>  
  
 <span data-ttu-id="82ae9-107">참조는 [CRYPTOAPI_BLOB](http://msdn.microsoft.com/library/windows/desktop/aa380238.aspx) 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="82ae9-107">See the [CRYPTOAPI_BLOB](http://msdn.microsoft.com/library/windows/desktop/aa380238.aspx) structure.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="82ae9-108">[in] 선택적 항목으로,</span><span class="sxs-lookup"><span data-stu-id="82ae9-108">[in] Optional.</span></span> <span data-ttu-id="82ae9-109">다음 값의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="82ae9-109">A combination of following values:</span></span>  
  
-   <span data-ttu-id="82ae9-110">AXL_REVOCATION_NO_CHECK</span><span class="sxs-lookup"><span data-stu-id="82ae9-110">AXL_REVOCATION_NO_CHECK</span></span>  
  
-   <span data-ttu-id="82ae9-111">AXL_REVOCATION_CHECK_END_CERT_ONLY</span><span class="sxs-lookup"><span data-stu-id="82ae9-111">AXL_REVOCATION_CHECK_END_CERT_ONLY</span></span>  
  
-   <span data-ttu-id="82ae9-112">AXL_REVOCATION_CHECK_ENTIRE_CHAIN</span><span class="sxs-lookup"><span data-stu-id="82ae9-112">AXL_REVOCATION_CHECK_ENTIRE_CHAIN</span></span>  
  
-   <span data-ttu-id="82ae9-113">AXL_URL_CACHE_ONLY_RETRIEVAL</span><span class="sxs-lookup"><span data-stu-id="82ae9-113">AXL_URL_CACHE_ONLY_RETRIEVAL</span></span>  
  
-   <span data-ttu-id="82ae9-114">AXL_LIFETIME_SIGNING</span><span class="sxs-lookup"><span data-stu-id="82ae9-114">AXL_LIFETIME_SIGNING</span></span>  
  
-   <span data-ttu-id="82ae9-115">AXL_TRUST_MICROSOFT_ROOT_ONLY</span><span class="sxs-lookup"><span data-stu-id="82ae9-115">AXL_TRUST_MICROSOFT_ROOT_ONLY</span></span>  
  
 `pSignerInfo`  
 <span data-ttu-id="82ae9-116">[out] 서명자의 정보를 받는 데 사용되는 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="82ae9-116">[out] To receive the signer's information.</span></span> <span data-ttu-id="82ae9-117">라이선스가 서명되지 않은 경우에는 `dwError` 가 TRUST_E_NOSIGNATURE로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="82ae9-117">If the license wasn't signed, `dwError` is set to TRUST_E_NOSIGNATURE.</span></span> <span data-ttu-id="82ae9-118">사용 하 여 리소스를 해제 해야 하는 호출자의는 [CertFreeAuthenticodeSignerInfo](../../../../docs/framework/unmanaged-api/authenticode/certfreeauthenticodesignerinfo-function.md) 함수 후 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="82ae9-118">It is the caller's responsibility to free resources by using the [CertFreeAuthenticodeSignerInfo](../../../../docs/framework/unmanaged-api/authenticode/certfreeauthenticodesignerinfo-function.md) function after use.</span></span>  
  
 <span data-ttu-id="82ae9-119">참조 [AXL_AUTHENTICODE_SIGNER_INFO 구조](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="82ae9-119">See [AXL_AUTHENTICODE_SIGNER_INFO Structure](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md).</span></span>  
  
 `pTimestamperInfo`  
 <span data-ttu-id="82ae9-120">[out] 타임스탬퍼 정보(있는 경우)를 받으려는 경우 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="82ae9-120">[out] To receive time stamper's information, if available.</span></span> <span data-ttu-id="82ae9-121">라이선스에 타임스탬프가 적용되지 않은 경우에는 `dwError` 가 TRUST_E_NOSIGNATURE로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="82ae9-121">If the license was not time-stamped, `dwError` is set to TRUST_E_NOSIGNATURE.</span></span> <span data-ttu-id="82ae9-122">사용 하 여 리소스를 해제 해야 하는 호출자의는 [CertFreeAuthenticodeTimestamperInfo](../../../../docs/framework/unmanaged-api/authenticode/certfreeauthenticodetimestamperinfo-function.md) 함수 후 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="82ae9-122">It is the caller's responsibility to free resources by using the [CertFreeAuthenticodeTimestamperInfo](../../../../docs/framework/unmanaged-api/authenticode/certfreeauthenticodetimestamperinfo-function.md) function after use.</span></span>  
  
 <span data-ttu-id="82ae9-123">참조 [AXL_AUTHENTICODE_TIMESTAMPER_INFO 구조](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="82ae9-123">See [AXL_AUTHENTICODE_TIMESTAMPER_INFO Structure](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="82ae9-124">반환 값</span><span class="sxs-lookup"><span data-stu-id="82ae9-124">Return Value</span></span>  
 <span data-ttu-id="82ae9-125">성공하는 경우 `S_OK`가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="82ae9-125">Returns `S_OK` if successful.</span></span> <span data-ttu-id="82ae9-126">그러지 않으면 오류 코드가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="82ae9-126">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82ae9-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="82ae9-127">See Also</span></span>  
 [<span data-ttu-id="82ae9-128">Authenticode</span><span class="sxs-lookup"><span data-stu-id="82ae9-128">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)  
 [<span data-ttu-id="82ae9-129">GetHashFromHandle 메서드</span><span class="sxs-lookup"><span data-stu-id="82ae9-129">GetHashFromHandle Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromhandle-method.md)  
 [<span data-ttu-id="82ae9-130">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="82ae9-130">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
