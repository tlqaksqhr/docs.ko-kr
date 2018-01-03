---
title: "_AxlGetIssuerPublicKeyHash 함수"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: _AxlGetIssuerPublicKeyHash
api_location: clr.dll
api_type: DLLExport
ms.assetid: fb626b41-b888-4625-84c3-2c02b5e3866f
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fee2b3e0e74ec13009a9b02d226c6a99b0e2f34b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="axlgetissuerpublickeyhash-function"></a><span data-ttu-id="c2420-102">_AxlGetIssuerPublicKeyHash 함수</span><span class="sxs-lookup"><span data-stu-id="c2420-102">_AxlGetIssuerPublicKeyHash Function</span></span>
<span data-ttu-id="c2420-103">지정한 인증서에 서명하는 데 사용되는 개인 키에 연결된 공개 키의 SHA-1 해시를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="c2420-103">Retrieves the SHA-1 hash of the public key associated with the private key that is used to sign the specified certificate.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2420-104">구문</span><span class="sxs-lookup"><span data-stu-id="c2420-104">Syntax</span></span>  
  
```  
HRESULT _AxlGetIssuerPublicKeyHash (  
    [in]  IN PCRYPT_DATA_BLOB   pChainContext,  
    [out] LPWSTR                *ppwszPublicKeyHash  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c2420-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c2420-105">Parameters</span></span>  
 `pChainContext`  
 <span data-ttu-id="c2420-106">[in] CSP 공개 키 Blob입니다.</span><span class="sxs-lookup"><span data-stu-id="c2420-106">[in] The CSP public key blob.</span></span> <span data-ttu-id="c2420-107">참조는 [CRYPTOAPI_BLOB](http://msdn.microsoft.com/library/windows/desktop/aa380238.aspx) 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="c2420-107">See the [CRYPTOAPI_BLOB](http://msdn.microsoft.com/library/windows/desktop/aa380238.aspx) structure.</span></span>  
  
 `ppwszPublicKeyHash`  
 <span data-ttu-id="c2420-108">[out] 16진수로 인코딩된 공개 키 토큰을 받는 WCHAR *에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c2420-108">[out] A pointer to WCHAR * to receive the hex-encoded public key token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c2420-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="c2420-109">Return Value</span></span>  
 <span data-ttu-id="c2420-110">함수가 정상적으로 실행되는 경우 `S_OK`이고 그러지 않으면 `S_FALSE`입니다.</span><span class="sxs-lookup"><span data-stu-id="c2420-110">`S_OK` if the function succeeds; otherwise `S_FALSE`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2420-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c2420-111">See Also</span></span>  
 [<span data-ttu-id="c2420-112">Authenticode</span><span class="sxs-lookup"><span data-stu-id="c2420-112">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
