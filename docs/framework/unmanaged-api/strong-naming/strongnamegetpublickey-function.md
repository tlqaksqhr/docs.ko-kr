---
title: "StrongNameGetPublicKey 함수"
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
- StrongNameGetPublicKey
api_location:
- mscoree.dll
- mscorsn.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameGetPublicKey
helpviewer_keywords:
- StrongNameGetPublicKey function [.NET Framework strong naming]
ms.assetid: 5b58c87f-3f72-40df-9b9a-291076931cc3
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: cec7c1edac24d43924abb2bf8784d45ed6372129
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="strongnamegetpublickey-function"></a><span data-ttu-id="1d4e5-102">StrongNameGetPublicKey 함수</span><span class="sxs-lookup"><span data-stu-id="1d4e5-102">StrongNameGetPublicKey Function</span></span>
<span data-ttu-id="1d4e5-103">개인/공개 키 쌍에서 공개 키를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1d4e5-103">Gets the public key from a private/public key pair.</span></span> <span data-ttu-id="1d4e5-104">키 쌍 또는 원시 바이트 컬렉션으로 서 암호화 서비스 공급자 (CSP) 내에서 키 컨테이너 이름을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d4e5-104">The key pair can be supplied either as a key container name within a cryptographic service provider (CSP) or as a raw collection of bytes.</span></span>  
  
 <span data-ttu-id="1d4e5-105">이 함수는 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1d4e5-105">This function has been deprecated.</span></span> <span data-ttu-id="1d4e5-106">사용 하 여 [iclrstrongname:: Strongnamegetpublickey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md) 메서드 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d4e5-106">Use the [ICLRStrongName::StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d4e5-107">구문</span><span class="sxs-lookup"><span data-stu-id="1d4e5-107">Syntax</span></span>  
  
```  
BOOLEAN StrongNameGetPublicKey (   
    [in]  LPCWSTR   szKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1d4e5-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1d4e5-108">Parameters</span></span>  
 `szKeyContainer`  
 <span data-ttu-id="1d4e5-109">[in] 공개/개인 키 쌍을 포함 하는 키 컨테이너의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="1d4e5-109">[in] The name of the key container that contains the public/private key pair.</span></span> <span data-ttu-id="1d4e5-110">경우 `pbKeyBlob` 매개 변수가 null 이면 `szKeyContainer` 는 CSP 내 유효한 컨테이너를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d4e5-110">If `pbKeyBlob` is null, `szKeyContainer` must specify a valid container within the CSP.</span></span> <span data-ttu-id="1d4e5-111">이 경우 `StrongNameGetPublicKey` 컨테이너에 저장 된 키 쌍에서 공개 키를 추출 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d4e5-111">In this case, `StrongNameGetPublicKey` extracts the public key from the key pair stored in the container.</span></span>  
  
 <span data-ttu-id="1d4e5-112">경우 `pbKeyBlob` null이 아니면 키 쌍 가정 키 binary large object (BLOB)에 포함 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d4e5-112">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="1d4e5-113">키 서명 키 1024 비트 Rivest-Shamir-Adleman (RSA) 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d4e5-113">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="1d4e5-114">다른 형식의 키이 이번에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d4e5-114">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="1d4e5-115">[in] 공개/개인 키 쌍에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="1d4e5-115">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="1d4e5-116">이 쌍은 win32 만든 형식 `CryptExportKey` 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="1d4e5-116">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="1d4e5-117">경우 `pbKeyBlob` 가 null 이면에서 지정한 키 컨테이너 `szKeyContainer` 키 쌍을 포함 하는로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d4e5-117">If `pbKeyBlob` is null, the key container specified by `szKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="1d4e5-118">[in] 를 바이트 단위로 크기의 `pbKeyBlob`합니다.</span><span class="sxs-lookup"><span data-stu-id="1d4e5-118">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="1d4e5-119">[out] 반환 된 공개 키 BLOB입니다.</span><span class="sxs-lookup"><span data-stu-id="1d4e5-119">[out] The returned public key BLOB.</span></span> <span data-ttu-id="1d4e5-120">`ppbPublicKeyBlob` 매개 변수는 공용 언어 런타임에 의해 할당 되 고 호출자에 게 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d4e5-120">The `ppbPublicKeyBlob` parameter is allocated by the common language runtime and returned to the caller.</span></span> <span data-ttu-id="1d4e5-121">호출자에 게 사용 하 여 메모리를 해제 해야는 [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="1d4e5-121">The caller must free the memory by using the [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) function.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="1d4e5-122">[out] 반환 된 공개 키 BLOB의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="1d4e5-122">[out] The size of the returned public key BLOB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1d4e5-123">반환 값</span><span class="sxs-lookup"><span data-stu-id="1d4e5-123">Return Value</span></span>  
 <span data-ttu-id="1d4e5-124">`true`성공적으로 완료 됩니다. 그렇지 않으면 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="1d4e5-124">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1d4e5-125">설명</span><span class="sxs-lookup"><span data-stu-id="1d4e5-125">Remarks</span></span>  
 <span data-ttu-id="1d4e5-126">공개 키에 포함 된 한 [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="1d4e5-126">The public key is contained in a [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) structure.</span></span>  
  
 <span data-ttu-id="1d4e5-127">경우는 `StrongNameGetPublicKey` 함수는 성공적으로 완료를 호출 하지는 [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) 함수를 마지막으로 생성 된 오류를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d4e5-127">If the `StrongNameGetPublicKey` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1d4e5-128">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1d4e5-128">Requirements</span></span>  
 <span data-ttu-id="1d4e5-129">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1d4e5-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d4e5-130">**헤더:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="1d4e5-130">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="1d4e5-131">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="1d4e5-131">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1d4e5-132">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d4e5-132">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d4e5-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1d4e5-133">See Also</span></span>  
 [<span data-ttu-id="1d4e5-134">StrongNameGetPublicKey 메서드</span><span class="sxs-lookup"><span data-stu-id="1d4e5-134">StrongNameGetPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md)  
 [<span data-ttu-id="1d4e5-135">StrongNameTokenFromPublicKey 메서드</span><span class="sxs-lookup"><span data-stu-id="1d4e5-135">StrongNameTokenFromPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)  
 [<span data-ttu-id="1d4e5-136">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1d4e5-136">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)  
 [<span data-ttu-id="1d4e5-137">PublicKeyBlob 구조체</span><span class="sxs-lookup"><span data-stu-id="1d4e5-137">PublicKeyBlob Structure</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)
