---
title: "_AxlPublicKeyBlobToPublicKeyToken 함수"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: _AxlPublicKeyBlobToPublicKeyToken
api_location: clr.dll
api_type: DLLExport
ms.assetid: 2d92a746-d68c-4f53-a16e-727f071a2d80
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 25a6a78fad95b894e82a75159458f25264f0ee0f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="axlpublickeyblobtopublickeytoken-function"></a><span data-ttu-id="9266c-102">_AxlPublicKeyBlobToPublicKeyToken 함수</span><span class="sxs-lookup"><span data-stu-id="9266c-102">_AxlPublicKeyBlobToPublicKeyToken Function</span></span>
<span data-ttu-id="9266c-103">CSP PUBLICKEYBLOB 형식에서 강력한 이름 공개 키 토큰을 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="9266c-103">Computes the strong name public key token from a CSP PUBLICKEYBLOB format.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9266c-104">구문</span><span class="sxs-lookup"><span data-stu-id="9266c-104">Syntax</span></span>  
  
```  
HRESULT _AxlPublicKeyBlobToPublicKeyToken (  
    [in]  PCCERT_CHAIN_CONTEXT   pCspPublicKeyBlob,  
    [out] LPWSTR                 *ppwszPublicKeyToken  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9266c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9266c-105">Parameters</span></span>  
 `pCspPublicKeyBlob`  
 <span data-ttu-id="9266c-106">[in] CSP 공개 키 Blob입니다.</span><span class="sxs-lookup"><span data-stu-id="9266c-106">[in] The CSP public key blob.</span></span>  
  
 `ppwszPublicKeyHash`  
 <span data-ttu-id="9266c-107">[out] 16진수로 인코딩된 공개 키 해시를 받는 WCHAR *에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="9266c-107">[out] A pointer to WCHAR * to receive the hex-encoded public key hash.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9266c-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="9266c-108">Return Value</span></span>  
 <span data-ttu-id="9266c-109">함수가 정상적으로 실행되는 경우 `S_OK`이고 그러지 않으면 `S_FALSE`입니다.</span><span class="sxs-lookup"><span data-stu-id="9266c-109">`S_OK` if the function succeeds; otherwise `S_FALSE`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9266c-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9266c-110">See Also</span></span>  
 [<span data-ttu-id="9266c-111">Authenticode</span><span class="sxs-lookup"><span data-stu-id="9266c-111">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
