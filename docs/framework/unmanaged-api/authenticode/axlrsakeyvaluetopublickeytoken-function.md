---
title: "_AxlRSAKeyValueToPublicKeyToken 함수"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: _AxlRSAKeyValueToPublicKeyToken
api_location: clr.dll
api_type: DLLExport
ms.assetid: d60f19fe-7bec-47ba-b60e-ba9ce66abf8c
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4af27a2abf1a0bcf4d79eda389c5f79f0ecb1eef
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="axlrsakeyvaluetopublickeytoken-function"></a><span data-ttu-id="b5388-102">_AxlRSAKeyValueToPublicKeyToken 함수</span><span class="sxs-lookup"><span data-stu-id="b5388-102">_AxlRSAKeyValueToPublicKeyToken Function</span></span>
<span data-ttu-id="b5388-103">모듈러스 및 지수를 강력한 이름 공개 키 토큰으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="b5388-103">Converts a Modulus and Exponent to a strong name public key token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5388-104">구문</span><span class="sxs-lookup"><span data-stu-id="b5388-104">Syntax</span></span>  
  
```  
HRESULT _AxlRSAKeyValueToPublicKeyToken (  
    [in]  PCRYPT_DATA_BLOB pModulusBlob,  
    [in]  PCRYPT_DATA_BLOB pExponentBlob,  
    [out] LPWSTR           *ppwszPublicKeyToken  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b5388-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b5388-105">Parameters</span></span>  
 `pModulusBlob`  
 <span data-ttu-id="b5388-106">[in] Base64 인코딩된 모듈러스 blob (에서 \<모듈러스 > 요소).</span><span class="sxs-lookup"><span data-stu-id="b5388-106">[in] The base64-encoded Modulus blob (from the \<Modulus> element).</span></span>  <span data-ttu-id="b5388-107">참조는 [CRYPTOAPI_BLOB](http://msdn.microsoft.com/library/windows/desktop/aa380238.aspx) 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="b5388-107">See the [CRYPTOAPI_BLOB](http://msdn.microsoft.com/library/windows/desktop/aa380238.aspx) structure.</span></span>  
  
 `pExponentBlob`  
 <span data-ttu-id="b5388-108">[in] Base64 인코딩된 지 수 blob (에서 \<지 수 > 요소).</span><span class="sxs-lookup"><span data-stu-id="b5388-108">[in] The base64-encoded Exponent blob (from the \<Exponent> element).</span></span> <span data-ttu-id="b5388-109">참조는 [CRYPTOAPI_BLOB](http://msdn.microsoft.com/library/windows/desktop/aa380238.aspx) 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="b5388-109">See the [CRYPTOAPI_BLOB](http://msdn.microsoft.com/library/windows/desktop/aa380238.aspx) structure.</span></span>  
  
 `ppwszPublicKeyToken`  
 <span data-ttu-id="b5388-110">[out] 16진수로 인코딩된 공개 키 토큰을 받는 WCHAR *에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b5388-110">[out] A pointer to WCHAR * to receive the hex-encoded public key token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b5388-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="b5388-111">Return Value</span></span>  
 <span data-ttu-id="b5388-112">함수가 정상적으로 실행되는 경우 `S_OK`입니다.</span><span class="sxs-lookup"><span data-stu-id="b5388-112">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="b5388-113">그러지 않으면 오류 코드가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="b5388-113">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5388-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b5388-114">See Also</span></span>  
 [<span data-ttu-id="b5388-115">Authenticode</span><span class="sxs-lookup"><span data-stu-id="b5388-115">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
