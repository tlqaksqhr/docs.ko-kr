---
title: "ICLRStrongName::StrongNameGetPublicKey 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRStrongName.StrongNameGetPublicKey
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRStrongName::StrongNameGetPublicKey
helpviewer_keywords:
- StrongNameGetPublicKey method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameGetPublicKey method [.NET Framework hosting]
ms.assetid: a31dcaa9-a404-4c1d-8cc7-081827c52935
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4b7ace87a5eff5235d85507bda649e55ea18fd93
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="iclrstrongnamestrongnamegetpublickey-method"></a><span data-ttu-id="cadc9-102">ICLRStrongName::StrongNameGetPublicKey 메서드</span><span class="sxs-lookup"><span data-stu-id="cadc9-102">ICLRStrongName::StrongNameGetPublicKey Method</span></span>
<span data-ttu-id="cadc9-103">공개/개인 키 쌍에서 공개 키를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="cadc9-103">Gets the public key from a public/private key pair.</span></span> <span data-ttu-id="cadc9-104">키 쌍 또는 원시 바이트 컬렉션으로 서 암호화 서비스 공급자 (CSP) 내에서 키 컨테이너 이름을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cadc9-104">The key pair can be supplied either as a key container name within a cryptographic service provider (CSP) or as a raw collection of bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cadc9-105">구문</span><span class="sxs-lookup"><span data-stu-id="cadc9-105">Syntax</span></span>  
  
```  
HRESULT StrongNameGetPublicKey (   
    [in]  LPCWSTR   szKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cadc9-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cadc9-106">Parameters</span></span>  
 `szKeyContainer`  
 <span data-ttu-id="cadc9-107">[in] 공개/개인 키 쌍을 포함 하는 키 컨테이너의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="cadc9-107">[in] The name of the key container that contains the public/private key pair.</span></span> <span data-ttu-id="cadc9-108">경우 `pbKeyBlob` 매개 변수가 null 이면 `szKeyContainer` 는 CSP 내 유효한 컨테이너를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cadc9-108">If `pbKeyBlob` is null, `szKeyContainer` must specify a valid container within the CSP.</span></span> <span data-ttu-id="cadc9-109">이 경우에 [iclrstrongname:: Strongnamegetpublickey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md) 메서드 컨테이너에 저장 된 키 쌍에서 공개 키를 추출 합니다.</span><span class="sxs-lookup"><span data-stu-id="cadc9-109">In this case, the [ICLRStrongName::StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md) method extracts the public key from the key pair stored in the container.</span></span>  
  
 <span data-ttu-id="cadc9-110">경우 `pbKeyBlob` null이 아니면 키 쌍 가정 키 binary large object (BLOB)에 포함 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cadc9-110">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="cadc9-111">키 서명 키 1024 비트 Rivest-Shamir-Adleman (RSA) 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cadc9-111">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="cadc9-112">다른 형식의 키이 이번에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cadc9-112">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="cadc9-113">[in] 공개/개인 키 쌍에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="cadc9-113">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="cadc9-114">이 쌍은 win32 만든 형식 `CryptExportKey` 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="cadc9-114">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="cadc9-115">경우 `pbKeyBlob` 가 null 이면에서 지정한 키 컨테이너 `szKeyContainer` 키 쌍을 포함 하는로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cadc9-115">If `pbKeyBlob` is null, the key container specified by `szKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="cadc9-116">[in] 를 바이트 단위로 크기의 `pbKeyBlob`합니다.</span><span class="sxs-lookup"><span data-stu-id="cadc9-116">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="cadc9-117">[out] 반환 된 공개 키 BLOB입니다.</span><span class="sxs-lookup"><span data-stu-id="cadc9-117">[out] The returned public key BLOB.</span></span> <span data-ttu-id="cadc9-118">`ppbPublicKeyBlob` 매개 변수는 공용 언어 런타임에 의해 할당 되 고 호출자에 게 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="cadc9-118">The `ppbPublicKeyBlob` parameter is allocated by the common language runtime and returned to the caller.</span></span> <span data-ttu-id="cadc9-119">호출자에 게 사용 하 여 메모리를 해제 해야는 [iclrstrongname:: Strongnamefreebuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="cadc9-119">The caller must free the memory by using the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="cadc9-120">[out] 반환 된 공개 키 BLOB의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="cadc9-120">[out] The size of the returned public key BLOB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cadc9-121">반환 값</span><span class="sxs-lookup"><span data-stu-id="cadc9-121">Return Value</span></span>  
 <span data-ttu-id="cadc9-122">`S_OK`메서드가 성공적으로 완료 하는 경우 그렇지 않으면 실패를 나타내는 HRESULT 값 (참조 [일반적인 HRESULT 값](http://go.microsoft.com/fwlink/?LinkId=213878) 목록에 대 한).</span><span class="sxs-lookup"><span data-stu-id="cadc9-122">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cadc9-123">설명</span><span class="sxs-lookup"><span data-stu-id="cadc9-123">Remarks</span></span>  
 <span data-ttu-id="cadc9-124">공개 키에 포함 된 한 [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="cadc9-124">The public key is contained in a [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cadc9-125">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cadc9-125">Requirements</span></span>  
 <span data-ttu-id="cadc9-126">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="cadc9-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cadc9-127">**헤더:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="cadc9-127">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="cadc9-128">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="cadc9-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cadc9-129">**.NET framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cadc9-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cadc9-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cadc9-130">See Also</span></span>  
 [<span data-ttu-id="cadc9-131">StrongNameTokenFromPublicKey 메서드</span><span class="sxs-lookup"><span data-stu-id="cadc9-131">StrongNameTokenFromPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)  
 [<span data-ttu-id="cadc9-132">PublicKeyBlob 구조체</span><span class="sxs-lookup"><span data-stu-id="cadc9-132">PublicKeyBlob Structure</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)  
 [<span data-ttu-id="cadc9-133">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cadc9-133">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
