---
title: "StrongNameGetPublicKeyEx 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRStrongName2.StrongNameGetPublicKeyEx
api_location: mscoree.dll
api_type: COM
f1_keywords: StrongNameGetPublicKeyEx
helpviewer_keywords:
- StrongNameGetPublicKeyEx method, ICLRStrongName2 interface [.NET Framework hosting]
- ICLRStrongName2::StrongNameGetPublicKeyEx method [.NET Framework hosting]
ms.assetid: 63d8260c-fb32-4f8f-a357-768afd570f68
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f39c5c948d43fd0e9387c1cc0319a46d25ec86ec
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="strongnamegetpublickeyex-method"></a><span data-ttu-id="9ae8c-102">StrongNameGetPublicKeyEx 메서드</span><span class="sxs-lookup"><span data-stu-id="9ae8c-102">StrongNameGetPublicKeyEx Method</span></span>
<span data-ttu-id="9ae8c-103">공개/개인 키 쌍에서 공개 키를 가져옵니다 하 고는 해시 알고리즘 및 서명 알고리즘을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ae8c-103">Gets the public key from a public/private key pair, and specifies a hash algorithm and a signature algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ae8c-104">구문</span><span class="sxs-lookup"><span data-stu-id="9ae8c-104">Syntax</span></span>  
  
```  
HRESULT StrongNameGetPublicKey (   
    [in]  LPCWSTR   pwzKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
    [in]  ULONG     uHashAlgId,  
    [in]  ULONG     uReserved,  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9ae8c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9ae8c-105">Parameters</span></span>  
 `pwzKeyContainer`  
 <span data-ttu-id="9ae8c-106">[in] 공개/개인 키 쌍을 포함 하는 키 컨테이너의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="9ae8c-106">[in] The name of the key container that contains the public/private key pair.</span></span> <span data-ttu-id="9ae8c-107">경우 `pbKeyBlob` 매개 변수가 null 이면 `szKeyContainer` 암호화 서비스 공급자 (CSP) 내에서 유효한 컨테이너를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ae8c-107">If `pbKeyBlob` is null, `szKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="9ae8c-108">이 경우에 `StrongNameGetPublicKeyEx` 메서드 컨테이너에 저장 된 키 쌍에서 공개 키를 추출 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ae8c-108">In this case, the `StrongNameGetPublicKeyEx` method extracts the public key from the key pair stored in the container.</span></span>  
  
 <span data-ttu-id="9ae8c-109">경우 `pbKeyBlob` null이 아니면 키 쌍 가정 키 binary large object (BLOB)에 포함 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ae8c-109">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="9ae8c-110">키 서명 키 1024 비트 Rivest-Shamir-Adleman (RSA) 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ae8c-110">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="9ae8c-111">다른 형식의 키이 이번에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ae8c-111">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="9ae8c-112">[in] 공개/개인 키 쌍에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="9ae8c-112">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="9ae8c-113">이 쌍은 win32 만든 형식 `CryptExportKey` 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="9ae8c-113">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="9ae8c-114">경우 `pbKeyBlob` 가 null 이면에서 지정한 키 컨테이너 `szKeyContainer` 키 쌍을 포함 하는로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ae8c-114">If `pbKeyBlob` is null, the key container specified by `szKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="9ae8c-115">[in] 를 바이트 단위로 크기의 `pbKeyBlob`합니다.</span><span class="sxs-lookup"><span data-stu-id="9ae8c-115">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="9ae8c-116">[out] 반환 된 공개 키 BLOB입니다.</span><span class="sxs-lookup"><span data-stu-id="9ae8c-116">[out] The returned public key BLOB.</span></span> <span data-ttu-id="9ae8c-117">`ppbPublicKeyBlob` 매개 변수는 공용 언어 런타임에 의해 할당 되 고 호출자에 게 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ae8c-117">The `ppbPublicKeyBlob` parameter is allocated by the common language runtime and returned to the caller.</span></span> <span data-ttu-id="9ae8c-118">호출자에 게 사용 하 여 메모리를 해제 해야는 [iclrstrongname:: Strongnamefreebuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="9ae8c-118">The caller must free the memory by using the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="9ae8c-119">[out] 반환 된 공개 키 BLOB의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="9ae8c-119">[out] The size of the returned public key BLOB.</span></span>  
  
 `uHashAlgId`  
 <span data-ttu-id="9ae8c-120">[in] 어셈블리 해시 알고리즘입니다.</span><span class="sxs-lookup"><span data-stu-id="9ae8c-120">[in] The assembly hash algorithm.</span></span> <span data-ttu-id="9ae8c-121">허용 되는 값의 목록은 설명 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9ae8c-121">See the Remarks section for a list of accepted values.</span></span>  
  
 `uReserved`  
 <span data-ttu-id="9ae8c-122">[in] 나중에 사용 됩니다. 기본값은 null입니다.</span><span class="sxs-lookup"><span data-stu-id="9ae8c-122">[in] Reserved for future use; defaults to null.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9ae8c-123">반환 값</span><span class="sxs-lookup"><span data-stu-id="9ae8c-123">Return Value</span></span>  
 <span data-ttu-id="9ae8c-124">`S_OK`메서드가 성공적으로 완료 하는 경우 그렇지 않으면 실패를 나타내는 HRESULT 값 (참조 [일반적인 HRESULT 값](http://go.microsoft.com/fwlink/?LinkId=213878) 목록에 대 한).</span><span class="sxs-lookup"><span data-stu-id="9ae8c-124">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9ae8c-125">설명</span><span class="sxs-lookup"><span data-stu-id="9ae8c-125">Remarks</span></span>  
 <span data-ttu-id="9ae8c-126">공개 키에 포함 된 한 [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="9ae8c-126">The public key is contained in a [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9ae8c-127">설명</span><span class="sxs-lookup"><span data-stu-id="9ae8c-127">Remarks</span></span>  
 <span data-ttu-id="9ae8c-128">다음 표에서 허용 되는 값에 대 한 집합을 보여 줍니다.는 `uHashAlgId` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="9ae8c-128">The following table shows the set of accepted values for the `uHashAlgId` parameter.</span></span>  
  
|<span data-ttu-id="9ae8c-129">이름</span><span class="sxs-lookup"><span data-stu-id="9ae8c-129">Name</span></span>|<span data-ttu-id="9ae8c-130">값</span><span class="sxs-lookup"><span data-stu-id="9ae8c-130">Value</span></span>|  
|----------|-----------|  
|<span data-ttu-id="9ae8c-131">없음</span><span class="sxs-lookup"><span data-stu-id="9ae8c-131">None</span></span>|<span data-ttu-id="9ae8c-132">0</span><span class="sxs-lookup"><span data-stu-id="9ae8c-132">0</span></span>|  
|<span data-ttu-id="9ae8c-133">S H A-1</span><span class="sxs-lookup"><span data-stu-id="9ae8c-133">SHA-1</span></span>|<span data-ttu-id="9ae8c-134">0x8004</span><span class="sxs-lookup"><span data-stu-id="9ae8c-134">0x8004</span></span>|  
|<span data-ttu-id="9ae8c-135">S H A-256</span><span class="sxs-lookup"><span data-stu-id="9ae8c-135">SHA-256</span></span>|<span data-ttu-id="9ae8c-136">0x800c</span><span class="sxs-lookup"><span data-stu-id="9ae8c-136">0x800c</span></span>|  
|<span data-ttu-id="9ae8c-137">S H A-384</span><span class="sxs-lookup"><span data-stu-id="9ae8c-137">SHA-384</span></span>|<span data-ttu-id="9ae8c-138">0x800d</span><span class="sxs-lookup"><span data-stu-id="9ae8c-138">0x800d</span></span>|  
|<span data-ttu-id="9ae8c-139">S H A-512</span><span class="sxs-lookup"><span data-stu-id="9ae8c-139">SHA-512</span></span>|<span data-ttu-id="9ae8c-140">0x800e</span><span class="sxs-lookup"><span data-stu-id="9ae8c-140">0x800e</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9ae8c-141">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9ae8c-141">Requirements</span></span>  
 <span data-ttu-id="9ae8c-142">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9ae8c-142">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ae8c-143">**헤더:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="9ae8c-143">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="9ae8c-144">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="9ae8c-144">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9ae8c-145">**.NET framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ae8c-145">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ae8c-146">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9ae8c-146">See Also</span></span>  
 [<span data-ttu-id="9ae8c-147">StrongNameTokenFromPublicKey 메서드</span><span class="sxs-lookup"><span data-stu-id="9ae8c-147">StrongNameTokenFromPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)  
 [<span data-ttu-id="9ae8c-148">PublicKeyBlob 구조체</span><span class="sxs-lookup"><span data-stu-id="9ae8c-148">PublicKeyBlob Structure</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)  
 [<span data-ttu-id="9ae8c-149">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9ae8c-149">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)  
 [<span data-ttu-id="9ae8c-150">StrongNameGetPublicKey 메서드</span><span class="sxs-lookup"><span data-stu-id="9ae8c-150">StrongNameGetPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md)
