---
title: "_AxlRSAKeyValueToPublicKeyToken 함수"
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
- _AxlRSAKeyValueToPublicKeyToken
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: d60f19fe-7bec-47ba-b60e-ba9ce66abf8c
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b1380f658d9c154d9ea41228cace5f9a3eed39b5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="axlrsakeyvaluetopublickeytoken-function"></a><span data-ttu-id="d1c0e-102">_AxlRSAKeyValueToPublicKeyToken 함수</span><span class="sxs-lookup"><span data-stu-id="d1c0e-102">_AxlRSAKeyValueToPublicKeyToken Function</span></span>
<span data-ttu-id="d1c0e-103">모듈러스 및 지수를 강력한 이름 공개 키 토큰으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="d1c0e-103">Converts a Modulus and Exponent to a strong name public key token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1c0e-104">구문</span><span class="sxs-lookup"><span data-stu-id="d1c0e-104">Syntax</span></span>  
  
```  
HRESULT _AxlRSAKeyValueToPublicKeyToken (  
    [in]  PCRYPT_DATA_BLOB pModulusBlob,  
    [in]  PCRYPT_DATA_BLOB pExponentBlob,  
    [out] LPWSTR           *ppwszPublicKeyToken  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d1c0e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d1c0e-105">Parameters</span></span>  
 `pModulusBlob`  
 <span data-ttu-id="d1c0e-106">[in] Base64 인코딩된 모듈러스 blob (에서 \<모듈러스 > 요소).</span><span class="sxs-lookup"><span data-stu-id="d1c0e-106">[in] The base64-encoded Modulus blob (from the \<Modulus> element).</span></span>  <span data-ttu-id="d1c0e-107">참조는 [CRYPTOAPI_BLOB](http://msdn.microsoft.com/library/windows/desktop/aa380238.aspx) 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="d1c0e-107">See the [CRYPTOAPI_BLOB](http://msdn.microsoft.com/library/windows/desktop/aa380238.aspx) structure.</span></span>  
  
 `pExponentBlob`  
 <span data-ttu-id="d1c0e-108">[in] Base64 인코딩된 지 수 blob (에서 \<지 수 > 요소).</span><span class="sxs-lookup"><span data-stu-id="d1c0e-108">[in] The base64-encoded Exponent blob (from the \<Exponent> element).</span></span> <span data-ttu-id="d1c0e-109">참조는 [CRYPTOAPI_BLOB](http://msdn.microsoft.com/library/windows/desktop/aa380238.aspx) 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="d1c0e-109">See the [CRYPTOAPI_BLOB](http://msdn.microsoft.com/library/windows/desktop/aa380238.aspx) structure.</span></span>  
  
 `ppwszPublicKeyToken`  
 <span data-ttu-id="d1c0e-110">[out] 16진수로 인코딩된 공개 키 토큰을 받는 WCHAR \*에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d1c0e-110">[out] A pointer to WCHAR \* to receive the hex-encoded public key token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d1c0e-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="d1c0e-111">Return Value</span></span>  
 <span data-ttu-id="d1c0e-112">함수가 정상적으로 실행되는 경우 `S_OK`입니다.</span><span class="sxs-lookup"><span data-stu-id="d1c0e-112">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="d1c0e-113">그러지 않으면 오류 코드가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1c0e-113">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1c0e-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d1c0e-114">See Also</span></span>  
 [<span data-ttu-id="d1c0e-115">Authenticode</span><span class="sxs-lookup"><span data-stu-id="d1c0e-115">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
