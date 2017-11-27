---
title: "CertTimestampAuthenticodeLicense 함수"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CertTimestampAuthenticodeLicense
api_location: clr.dll
api_type: DLLExport
ms.assetid: d468325a-21c5-43ce-8567-84e342b22308
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 42ec863e9accbd2156b6eeed5857ff86075cf0a5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="certtimestampauthenticodelicense-function"></a><span data-ttu-id="f164f-102">CertTimestampAuthenticodeLicense 함수</span><span class="sxs-lookup"><span data-stu-id="f164f-102">CertTimestampAuthenticodeLicense Function</span></span>
<span data-ttu-id="f164f-103">Authenticode XrML 라이선스에 타임스탬프를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="f164f-103">Time-stamps an Authenticode XrML license.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f164f-104">구문</span><span class="sxs-lookup"><span data-stu-id="f164f-104">Syntax</span></span>  
  
```  
HRESULT CertTimestampAuthenticodeLicense (  
    [in]  PCRYPT_DATA_BLOB   pSignedLicenseBlob,  
    [in]  LPCWSTR            pwszTimestampURI,  
    [out] PCRYPT_DATA_BLOB   pTimestampSignatureBlob  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f164f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f164f-105">Parameters</span></span>  
 `pSignedLicenseBlob`  
 <span data-ttu-id="f164f-106">[in] 타임스탬프를 적용할 서명된 Authenticode XrML 라이선스입니다.</span><span class="sxs-lookup"><span data-stu-id="f164f-106">[in] The signed Authenticode XrML license to be time-stamped.</span></span> <span data-ttu-id="f164f-107">참조는 [CRYPTOAPI_BLOB](http://msdn.microsoft.com/library/windows/desktop/aa380238.aspx) 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="f164f-107">See the [CRYPTOAPI_BLOB](http://msdn.microsoft.com/library/windows/desktop/aa380238.aspx) structure.</span></span>  
  
 `pwszTimestampURI`  
 <span data-ttu-id="f164f-108">[in] 타임스탬프 서버의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="f164f-108">[in] The time-stamp server's URI.</span></span>  
  
 `pTimestampSignatureBlob`  
 <span data-ttu-id="f164f-109">[out] base64로 인코딩된 타임스탬프 서명을 받을 CRYPT_DATA_BLOB에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f164f-109">[out] A pointer to CRYPT_DATA_BLOB to receive the base64-encoded time-stamp signature.</span></span> <span data-ttu-id="f164f-110">해제 해야 하는 호출자의 `pTimestampSignatureBlob` -> `pbData` 와 `HepFree()` 후 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f164f-110">It is the caller's responsibility to free `pTimestampSignatureBlob`->`pbData` with `HepFree()` after use.</span></span> <span data-ttu-id="f164f-111">참조는 [CRYPTOAPI_BLOB](http://msdn.microsoft.com/library/windows/desktop/aa380238.aspx) 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="f164f-111">See the [CRYPTOAPI_BLOB](http://msdn.microsoft.com/library/windows/desktop/aa380238.aspx) structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f164f-112">설명</span><span class="sxs-lookup"><span data-stu-id="f164f-112">Remarks</span></span>  
 <span data-ttu-id="f164f-113">타임스탬프 서명은 실제로는 해당 콘텐츠가 라이선스 서명에 있는 SignatureValue의 이진 형식인 PKCS #7 SignedData 메시지이며,</span><span class="sxs-lookup"><span data-stu-id="f164f-113">The time-stamp signature is actually a PKCS #7 SignedData message whose content is the binary form of the SignatureValue from the license's signature.</span></span> <span data-ttu-id="f164f-114">기본적으로 라이선스의 연대 서명으로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="f164f-114">Basically, this acts as a counter-signature of the license.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f164f-115">반환 값</span><span class="sxs-lookup"><span data-stu-id="f164f-115">Return Value</span></span>  
 <span data-ttu-id="f164f-116">함수가 정상적으로 실행되는 경우 `S_OK`입니다.</span><span class="sxs-lookup"><span data-stu-id="f164f-116">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="f164f-117">그러지 않으면 오류 코드가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="f164f-117">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f164f-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f164f-118">See Also</span></span>  
 [<span data-ttu-id="f164f-119">Authenticode</span><span class="sxs-lookup"><span data-stu-id="f164f-119">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
