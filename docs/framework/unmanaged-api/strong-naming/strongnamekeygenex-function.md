---
title: "StrongNameKeyGenEx 함수"
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
- StrongNameKeyGenEx
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameKeyGenEx
helpviewer_keywords:
- StrongNameKeyGenEx function [.NET Framework strong naming]
ms.assetid: 36bd10b9-9857-45f3-8d3b-0da091d6169e
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ae564f7c4e8333e33b2f2f6229034c3a1396a687
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="strongnamekeygenex-function"></a><span data-ttu-id="97410-102">StrongNameKeyGenEx 함수</span><span class="sxs-lookup"><span data-stu-id="97410-102">StrongNameKeyGenEx Function</span></span>
<span data-ttu-id="97410-103">강력한 이름 사용 하기 위해 지정된 된 키 크기와 새 공개/개인 키 쌍을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="97410-103">Generates a new public/private key pair with the specified key size, for strong name use.</span></span>  
  
 <span data-ttu-id="97410-104">이 함수는 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="97410-104">This function has been deprecated.</span></span> <span data-ttu-id="97410-105">사용 하 여 [iclrstrongname:: Strongnamekeygenex](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygenex-method.md) 메서드 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="97410-105">Use the [ICLRStrongName::StrongNameKeyGenEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygenex-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97410-106">구문</span><span class="sxs-lookup"><span data-stu-id="97410-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameKeyGenEx (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [in]  DWORD     dwKeySize,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="97410-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="97410-107">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="97410-108">[in] 요청 된 키 컨테이너 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="97410-108">[in] The requested key container name.</span></span> <span data-ttu-id="97410-109">`wszKeyContainer`비어 있지 않은 문자열 이어야 하거나 임시 이름을 생성 하는 null 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="97410-109">`wszKeyContainer` must be a non-empty string, or null to generate a temporary name.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="97410-110">[in] 등록 키를 상태로 둘지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="97410-110">[in] Specifies whether to leave the key registered.</span></span> <span data-ttu-id="97410-111">다음 값이 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="97410-111">The following values are supported:</span></span>  
  
-   <span data-ttu-id="97410-112">때에 사용 되는 0x00000000- `wszKeyContainer` 임시 키 컨테이너 이름을 생성 하는 null입니다.</span><span class="sxs-lookup"><span data-stu-id="97410-112">0x00000000 - Used when `wszKeyContainer` is null to generate a temporary key container name.</span></span>  
  
-   <span data-ttu-id="97410-113">0x00000001 (`SN_LEAVE_KEY`)-키 왼쪽 등록 해야 함을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="97410-113">0x00000001 (`SN_LEAVE_KEY`) - Specifies that the key should be left registered.</span></span>  
  
 `dwKeySize`  
 <span data-ttu-id="97410-114">[in] 요청 된 크기 비트에서 키입니다.</span><span class="sxs-lookup"><span data-stu-id="97410-114">[in] The requested size of the key, in bits.</span></span>  
  
 `ppbKeyBlob`  
 <span data-ttu-id="97410-115">[out] 반환 된 공개/개인 키 쌍입니다.</span><span class="sxs-lookup"><span data-stu-id="97410-115">[out] The returned public/private key pair.</span></span>  
  
 `pcbKeyBlob`  
 <span data-ttu-id="97410-116">[out] 를 바이트 단위로 크기의 `ppbKeyBlob`합니다.</span><span class="sxs-lookup"><span data-stu-id="97410-116">[out] The size, in bytes, of `ppbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="97410-117">반환 값</span><span class="sxs-lookup"><span data-stu-id="97410-117">Return Value</span></span>  
 <span data-ttu-id="97410-118">`true`성공적으로 완료 됩니다. 그렇지 않으면 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="97410-118">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="97410-119">설명</span><span class="sxs-lookup"><span data-stu-id="97410-119">Remarks</span></span>  
 <span data-ttu-id="97410-120">.NET Framework 버전 1.0 및 1.1에서는 `dwKeySize` ; 강력한 이름의 어셈블리에 서명 하는 1024 비트의 버전 2.0는 2048 비트 키에 대 한 지원 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="97410-120">The .NET Framework versions 1.0 and 1.1 require a `dwKeySize` of 1024 bits to sign an assembly with a strong name; version 2.0 adds supports for 2048-bit keys.</span></span>  
  
 <span data-ttu-id="97410-121">호출 해야 키를 검색 한 후의 [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) 함수 할당 된 메모리를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="97410-121">After the key is retrieved, you should call the [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) function to release the allocated memory.</span></span>  
  
 <span data-ttu-id="97410-122">경우는 `StrongNameKeyGenEx` 함수는 성공적으로 완료를 호출 하지는 [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) 함수를 마지막으로 생성 된 오류를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="97410-122">If the `StrongNameKeyGenEx` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="97410-123">요구 사항</span><span class="sxs-lookup"><span data-stu-id="97410-123">Requirements</span></span>  
 <span data-ttu-id="97410-124">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="97410-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="97410-125">**헤더:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="97410-125">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="97410-126">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="97410-126">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="97410-127">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="97410-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97410-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="97410-128">See Also</span></span>  
 [<span data-ttu-id="97410-129">StrongNameKeyGenEx 메서드</span><span class="sxs-lookup"><span data-stu-id="97410-129">StrongNameKeyGenEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygenex-method.md)  
 [<span data-ttu-id="97410-130">StrongNameKeyGen 메서드</span><span class="sxs-lookup"><span data-stu-id="97410-130">StrongNameKeyGen Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md)  
 [<span data-ttu-id="97410-131">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="97410-131">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
