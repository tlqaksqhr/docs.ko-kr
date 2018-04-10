---
title: Authenticode(관리되지 않는 API 참조)
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 7e8cc303-6e77-4116-aa8b-7ea297a3a467
caps.latest.revision: 4
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0b790064ef64ab44f3798a62d5dbf004f0f0bba6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="authenticode-unmanaged-api-reference"></a><span data-ttu-id="3ddd1-102">Authenticode(관리되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="3ddd1-102">Authenticode (Unmanaged API Reference)</span></span>
<span data-ttu-id="3ddd1-103">Authenticode XrML 라이센스 만들기 및 확인 모듈을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="3ddd1-103">Supports the Authenticode XrML license creation and verification module.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3ddd1-104">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="3ddd1-104">In This Section</span></span>  
 [<span data-ttu-id="3ddd1-105">_AxlGetIssuerPublicKeyHash 함수</span><span class="sxs-lookup"><span data-stu-id="3ddd1-105">_AxlGetIssuerPublicKeyHash Function</span></span>](../../../../docs/framework/unmanaged-api/authenticode/axlgetissuerpublickeyhash-function.md)  
 <span data-ttu-id="3ddd1-106">지정한 인증서에 서명하는 데 사용되는 개인 키에 연결된 공개 키의 SHA-1 해시를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="3ddd1-106">Retrieves the SHA-1 hash of the public key associated with the private key that is used to sign the specified certificate.</span></span>  
  
 [<span data-ttu-id="3ddd1-107">_AxlPublicKeyBlobToPublicKeyToken 함수</span><span class="sxs-lookup"><span data-stu-id="3ddd1-107">_AxlPublicKeyBlobToPublicKeyToken Function</span></span>](../../../../docs/framework/unmanaged-api/authenticode/axlpublickeyblobtopublickeytoken-function.md)  
 <span data-ttu-id="3ddd1-108">CSP PUBLICKEYBLOB 형식에서 강력한 이름 공개 키 토큰을 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="3ddd1-108">Computes the strong name public key token from a CSP PUBLICKEYBLOB format.</span></span>  
  
 [<span data-ttu-id="3ddd1-109">_AxlRSAKeyValueToPublicKeyToken 함수</span><span class="sxs-lookup"><span data-stu-id="3ddd1-109">_AxlRSAKeyValueToPublicKeyToken Function</span></span>](../../../../docs/framework/unmanaged-api/authenticode/axlrsakeyvaluetopublickeytoken-function.md)  
 <span data-ttu-id="3ddd1-110">모듈러스 및 지수를 강력한 이름 공개 키 토큰으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="3ddd1-110">Converts a Modulus and Exponent to a strong name public key token.</span></span>  
  
 [<span data-ttu-id="3ddd1-111">CertFreeAuthenticodeSignerInfo 함수</span><span class="sxs-lookup"><span data-stu-id="3ddd1-111">CertFreeAuthenticodeSignerInfo Function</span></span>](../../../../docs/framework/unmanaged-api/authenticode/certfreeauthenticodesignerinfo-function.md)  
 <span data-ttu-id="3ddd1-112">AXL_AUTHENTICODE_SIGNER_INFO 구조체에 할당된 리소스를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="3ddd1-112">Frees resources allocated for the AXL_AUTHENTICODE_SIGNER_INFO structure.</span></span>  
  
 [<span data-ttu-id="3ddd1-113">CertFreeAuthenticodeTimestamperInfo 함수</span><span class="sxs-lookup"><span data-stu-id="3ddd1-113">CertFreeAuthenticodeTimestamperInfo Function</span></span>](../../../../docs/framework/unmanaged-api/authenticode/certfreeauthenticodetimestamperinfo-function.md)  
 <span data-ttu-id="3ddd1-114">AXL_AUTHENTICODE_TIMESTAMPER_INFO 구조체에 할당된 리소스를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="3ddd1-114">Frees resources allocated for the AXL_AUTHENTICODE_TIMESTAMPER_INFO structure.</span></span>  
  
 [<span data-ttu-id="3ddd1-115">CertTimestampAuthenticodeLicense 함수</span><span class="sxs-lookup"><span data-stu-id="3ddd1-115">CertTimestampAuthenticodeLicense Function</span></span>](../../../../docs/framework/unmanaged-api/authenticode/certtimestampauthenticodelicense-function.md)  
 <span data-ttu-id="3ddd1-116">CertCreateAuthenticodeLicense에 의해 작성된 Authenticode XrML 라이선스에 타임스탬프를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="3ddd1-116">Time stamps an Authenticode XrML license created by CertCreateAuthenticodeLicense.</span></span>  
  
 [<span data-ttu-id="3ddd1-117">CertVerifyAuthenticodeLicense 함수</span><span class="sxs-lookup"><span data-stu-id="3ddd1-117">CertVerifyAuthenticodeLicense Function</span></span>](../../../../docs/framework/unmanaged-api/authenticode/certverifyauthenticodelicense-function.md)  
 <span data-ttu-id="3ddd1-118">Authenticode XrML 라이선스의 유효성을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="3ddd1-118">Verifies the validity of an Authenticode XrML license.</span></span>  
  
 [<span data-ttu-id="3ddd1-119">AXL_AUTHENTICODE_SIGNER_INFO 구조체</span><span class="sxs-lookup"><span data-stu-id="3ddd1-119">AXL_AUTHENTICODE_SIGNER_INFO Structure</span></span>](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md)  
 <span data-ttu-id="3ddd1-120">Authenticode 서명자 정보를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="3ddd1-120">Defines the Authenticode signer information.</span></span>  
  
 [<span data-ttu-id="3ddd1-121">AXL_AUTHENTICODE_TIMESTAMPER_INFO 구조체</span><span class="sxs-lookup"><span data-stu-id="3ddd1-121">AXL_AUTHENTICODE_TIMESTAMPER_INFO Structure</span></span>](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md)  
 <span data-ttu-id="3ddd1-122">Authenticode 타임스탬퍼 정보를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="3ddd1-122">Defines the Authenticode time stamper information.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ddd1-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3ddd1-123">See Also</span></span>  
 [<span data-ttu-id="3ddd1-124">관리되지 않는 API 참조</span><span class="sxs-lookup"><span data-stu-id="3ddd1-124">Unmanaged API Reference</span></span>](../../../../docs/framework/unmanaged-api/index.md)
