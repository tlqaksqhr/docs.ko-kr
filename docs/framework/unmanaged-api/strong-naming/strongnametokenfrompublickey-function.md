---
title: "StrongNameTokenFromPublicKey 함수"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: StrongNameTokenFromPublicKey
api_location:
- mscoree.dll
- mscorsn.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type: COM
f1_keywords: StrongNameTokenFromPublicKey
helpviewer_keywords: StrongNameTokenFromPublicKey function [.NET Framework strong naming]
ms.assetid: 997e9e57-abb2-4217-bf20-1df621a75add
topic_type: apiref
caps.latest.revision: "19"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: cfde09f6383646f24077c3bdc0efa4b31bc50ba0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="strongnametokenfrompublickey-function"></a><span data-ttu-id="5a777-102">StrongNameTokenFromPublicKey 함수</span><span class="sxs-lookup"><span data-stu-id="5a777-102">StrongNameTokenFromPublicKey Function</span></span>
<span data-ttu-id="5a777-103">공개 키를 나타내는 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5a777-103">Gets a token representing a public key.</span></span> <span data-ttu-id="5a777-104">강력한 이름 토큰에는 공개 키의 축약 된 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="5a777-104">A strong name token is the shortened form of a public key.</span></span>  
  
 <span data-ttu-id="5a777-105">이 함수는 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5a777-105">This function has been deprecated.</span></span> <span data-ttu-id="5a777-106">사용 하 여 [iclrstrongname:: Strongnametokenfrompublickey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md) 메서드 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a777-106">Use the [ICLRStrongName::StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a777-107">구문</span><span class="sxs-lookup"><span data-stu-id="5a777-107">Syntax</span></span>  
  
```  
BOOLEANStrongNameTokenFromPublicKey (   
    [in]  BYTE    *pbPublicKeyBlob,  
    [in]  ULONG   cbPublicKeyBlob,  
    [out] BYTE    **ppbStrongNameToken,  
    [out] ULONG   *pcbStrongNameToken  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5a777-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5a777-108">Parameters</span></span>  
 `pbPublicKeyBlob`  
 <span data-ttu-id="5a777-109">[in] 형식의 구조 [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) 강력한 이름 서명을 생성 하는 데 사용 되는 키 쌍의 공개 부분을 포함 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a777-109">[in] A structure of type [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="5a777-110">[in] 를 바이트 단위로 크기의 `pbPublicKeyBlob`합니다.</span><span class="sxs-lookup"><span data-stu-id="5a777-110">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="5a777-111">[out] 전달 된 키에 해당 하는 강력한 이름의 토큰 `pbPublicKeyBlob`합니다.</span><span class="sxs-lookup"><span data-stu-id="5a777-111">[out] The strong name token corresponding to the key passed in `pbPublicKeyBlob`.</span></span> <span data-ttu-id="5a777-112">공용 언어 런타임 토큰을 반환 하는 메모리를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a777-112">The common language runtime allocates the memory in which to return the token.</span></span> <span data-ttu-id="5a777-113">호출자에 게 사용 하 여이 메모리를 해제 해야 합니다는 [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="5a777-113">The caller must free this memory by using the [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) function.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="5a777-114">[out] 반환 된 강력한 이름 토큰의 바이트 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="5a777-114">[out] The size, in bytes, of the returned strong name token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5a777-115">반환 값</span><span class="sxs-lookup"><span data-stu-id="5a777-115">Return Value</span></span>  
 <span data-ttu-id="5a777-116">`true`성공적으로 완료 됩니다. 그렇지 않으면 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="5a777-116">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5a777-117">설명</span><span class="sxs-lookup"><span data-stu-id="5a777-117">Remarks</span></span>  
 <span data-ttu-id="5a777-118">강력한 이름 토큰에는 간단한 형식의 메타 데이터에 키 정보를 저장할 때 공간 절약을 위해 사용 되는 공개 키입니다.</span><span class="sxs-lookup"><span data-stu-id="5a777-118">A strong name token is the shortened form of a public key used to save space when storing key information in metadata.</span></span> <span data-ttu-id="5a777-119">특히, 강력한 이름 토큰 종속 어셈블리를 참조 하려면 어셈블리 참조에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a777-119">Specifically, strong name tokens are used in assembly references to refer to the dependent assembly.</span></span>  
  
 <span data-ttu-id="5a777-120">경우는 `StrongNameTokenFromPublicKey` 함수는 성공적으로 완료를 호출 하지는 [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) 함수를 마지막으로 생성 된 오류를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a777-120">If the `StrongNameTokenFromPublicKey` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5a777-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5a777-121">Requirements</span></span>  
 <span data-ttu-id="5a777-122">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5a777-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a777-123">**헤더:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="5a777-123">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="5a777-124">**라이브러리:** mscoree.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="5a777-124">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="5a777-125">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a777-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a777-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5a777-126">See Also</span></span>  
 [<span data-ttu-id="5a777-127">StrongNameTokenFromPublicKey 메서드</span><span class="sxs-lookup"><span data-stu-id="5a777-127">StrongNameTokenFromPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)  
 [<span data-ttu-id="5a777-128">StrongNameGetPublicKey 메서드</span><span class="sxs-lookup"><span data-stu-id="5a777-128">StrongNameGetPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md)  
 [<span data-ttu-id="5a777-129">PublicKeyBlob 구조체</span><span class="sxs-lookup"><span data-stu-id="5a777-129">PublicKeyBlob Structure</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)
