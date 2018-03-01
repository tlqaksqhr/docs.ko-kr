---
title: "StrongNameSignatureVerificationEx2 메서드"
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
- ICLRStrongName2.StrongNameSignatureVerificationEx2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- StrongNameSignatureVerificationEx2
helpviewer_keywords:
- StrongNameSignatureVerificationEx2 method, ICLRStrongName2 interface [.NET Framework hosting]
- ICLRStrongName2::StrongNameSignatureVerificationEx2 method [.NET Framework hosting]
ms.assetid: dfd4133f-a074-4db3-a7ee-4f250fe9ad3a
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b4faa7fee32d9cab5a75772f29d2014473e2bee0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="strongnamesignatureverificationex2-method"></a><span data-ttu-id="0f703-102">StrongNameSignatureVerificationEx2 메서드</span><span class="sxs-lookup"><span data-stu-id="0f703-102">StrongNameSignatureVerificationEx2 Method</span></span>
<span data-ttu-id="0f703-103">강력한 이름의 어셈블리의 서명을 확인 하 고 실제 키를 ECMA 키로의 매핑을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f703-103">Verifies the signature of a strongly named assembly, and provides a mapping from the ECMA key to a real key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f703-104">구문</span><span class="sxs-lookup"><span data-stu-id="0f703-104">Syntax</span></span>  
  
```  
HRESULT StrongNameSignatureVerificationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  BOOLEAN   fForceVerification,    [in]  BYTE      *pbEcmaPublicKey,  
    [in]  DWORD     cbEcmaPublicKey,  
    [out] BOOLEAN   *pfWasVerified  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0f703-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0f703-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="0f703-106">[in] 이식 가능한 실행 (.exe 또는.dll) 파일에 어셈블리를 확인할 수에 대 한 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="0f703-106">[in] The path to the portable executable (.exe or .dll) file for the assembly to be verified.</span></span>  
  
 `fForceVerification`  
 <span data-ttu-id="0f703-107">[in] `true` 고, 그렇지 않으면 레지스트리 설정을 재정의 하는 데 필요한 경우에 유효성 검사를 수행 하려면 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="0f703-107">[in] `true` to perform verification, even if it is necessary to override registry settings; otherwise, `false`.</span></span>  
  
 `pbEcmaPublicKey`  
 <span data-ttu-id="0f703-108">[in] 확인에 사용 된 실제 키를 ECMA 공개 키에서 매핑에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="0f703-108">[in] A pointer to the mapping from the ECMA public key to the real key used for verification.</span></span>  
  
 `cbEcmaPublicKey`  
 <span data-ttu-id="0f703-109">[in] 실제 ECMA 공개 키의 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="0f703-109">[in] The length of the real ECMA public key.</span></span>  
  
 `pfWasVerified`  
 <span data-ttu-id="0f703-110">[out] `true` 강력한 이름 서명을 했으면 확인 된, `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="0f703-110">[out] `true` if the strong name signature was verified; otherwise, `false`.</span></span> <span data-ttu-id="0f703-111">이 매개 변수는 또한 설정 `false` 레지스트리 설정으로 인해 확인 되 면 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f703-111">This parameter is also set to `false` if the verification was successful due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0f703-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="0f703-112">Return Value</span></span>  
 <span data-ttu-id="0f703-113">`S_OK`확인에 성공 하면 그렇지 않으면 실패를 나타내는 HRESULT 값 (참조 [일반적인 HRESULT 값](http://go.microsoft.com/fwlink/?LinkId=213878) 목록에 대 한).</span><span class="sxs-lookup"><span data-stu-id="0f703-113">`S_OK` if the verification was successful; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f703-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0f703-114">Requirements</span></span>  
 <span data-ttu-id="0f703-115">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0f703-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0f703-116">**헤더:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="0f703-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="0f703-117">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="0f703-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0f703-118">**.NET framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0f703-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f703-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0f703-119">See Also</span></span>  
 [<span data-ttu-id="0f703-120">StrongNameSignatureVerification 메서드</span><span class="sxs-lookup"><span data-stu-id="0f703-120">StrongNameSignatureVerification Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md)  
 [<span data-ttu-id="0f703-121">StrongNameSignatureVerificationEx 메서드</span><span class="sxs-lookup"><span data-stu-id="0f703-121">StrongNameSignatureVerificationEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)  
 [<span data-ttu-id="0f703-122">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0f703-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
