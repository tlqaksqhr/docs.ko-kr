---
title: "ICLRStrongName::StrongNameKeyGenEx 메서드"
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
- ICLRStrongName.StrongNameKeyGenEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameKeyGenEx
helpviewer_keywords:
- ICLRStrongName::StrongNameKeyGenEx method [.NET Framework hosting]
- StrongNameKeyGenEx method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 1f8b59d0-5b72-45b8-ab74-c2b43ffc806e
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 581f486a2def90f44c0fb3f1bcf9d3bbcc1fc317
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="iclrstrongnamestrongnamekeygenex-method"></a><span data-ttu-id="12bb0-102">ICLRStrongName::StrongNameKeyGenEx 메서드</span><span class="sxs-lookup"><span data-stu-id="12bb0-102">ICLRStrongName::StrongNameKeyGenEx Method</span></span>
<span data-ttu-id="12bb0-103">강력한 이름 사용 하기 위해 지정된 된 키 크기와 새 공개/개인 키 쌍을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="12bb0-103">Generates a new public/private key pair with the specified key size, for strong name use.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12bb0-104">구문</span><span class="sxs-lookup"><span data-stu-id="12bb0-104">Syntax</span></span>  
  
```  
HRESULT StrongNameKeyGenEx (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [in]  DWORD     dwKeySize,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="12bb0-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="12bb0-105">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="12bb0-106">[in] 요청 된 키 컨테이너 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="12bb0-106">[in] The requested key container name.</span></span> <span data-ttu-id="12bb0-107">`wszKeyContainer`비어 있지 않은 문자열 또는 임시 이름을 생성 하는 null 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="12bb0-107">`wszKeyContainer` must either be a non-empty string or null to generate a temporary name.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="12bb0-108">[in] 등록 키를 유지 여부를 지정 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="12bb0-108">[in] A value that specifies whether to leave the key registered.</span></span> <span data-ttu-id="12bb0-109">다음 값이 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="12bb0-109">The following values are supported:</span></span>  
  
-   <span data-ttu-id="12bb0-110">때에 사용 되는 0x00000000- `wszKeyContainer` 임시 키 컨테이너 이름을 생성 하는 null입니다.</span><span class="sxs-lookup"><span data-stu-id="12bb0-110">0x00000000 - Used when `wszKeyContainer` is null to generate a temporary key container name.</span></span>  
  
-   <span data-ttu-id="12bb0-111">0x00000001 (`SN_LEAVE_KEY`)-키 왼쪽 등록 해야 함을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="12bb0-111">0x00000001 (`SN_LEAVE_KEY`) - Specifies that the key should be left registered.</span></span>  
  
 `dwKeySize`  
 <span data-ttu-id="12bb0-112">[in] 요청 된 크기 비트에서 키입니다.</span><span class="sxs-lookup"><span data-stu-id="12bb0-112">[in] The requested size of the key, in bits.</span></span>  
  
 `ppbKeyBlob`  
 <span data-ttu-id="12bb0-113">[out] 반환 된 공개/개인 키 쌍입니다.</span><span class="sxs-lookup"><span data-stu-id="12bb0-113">[out] The returned public/private key pair.</span></span>  
  
 `pcbKeyBlob`  
 <span data-ttu-id="12bb0-114">[out] 를 바이트 단위로 크기의 `ppbKeyBlob`합니다.</span><span class="sxs-lookup"><span data-stu-id="12bb0-114">[out] The size, in bytes, of `ppbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="12bb0-115">반환 값</span><span class="sxs-lookup"><span data-stu-id="12bb0-115">Return Value</span></span>  
 <span data-ttu-id="12bb0-116">`S_OK`메서드가 성공적으로 완료 하는 경우 그렇지 않으면 실패를 나타내는 HRESULT 값 (참조 [일반적인 HRESULT 값](http://go.microsoft.com/fwlink/?LinkId=213878) 목록에 대 한).</span><span class="sxs-lookup"><span data-stu-id="12bb0-116">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="12bb0-117">설명</span><span class="sxs-lookup"><span data-stu-id="12bb0-117">Remarks</span></span>  
 <span data-ttu-id="12bb0-118">.NET Framework 버전 1.0 및 1.1에서는 `dwKeySize` ; 강력한 이름의 어셈블리에 서명 하는 1024 비트의 버전 2.0는 2048 비트 키에 대 한 지원 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="12bb0-118">The .NET Framework versions 1.0 and 1.1 require a `dwKeySize` of 1024 bits to sign an assembly with a strong name; version 2.0 adds supports for 2048-bit keys.</span></span>  
  
 <span data-ttu-id="12bb0-119">호출 해야 키를 검색 한 후의 [iclrstrongname:: Strongnamefreebuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) 메서드 할당 된 메모리를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="12bb0-119">After the key is retrieved, you should call the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method to release the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="12bb0-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="12bb0-120">Requirements</span></span>  
 <span data-ttu-id="12bb0-121">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="12bb0-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="12bb0-122">**헤더:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="12bb0-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="12bb0-123">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="12bb0-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="12bb0-124">**.NET framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="12bb0-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12bb0-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="12bb0-125">See Also</span></span>  
 [<span data-ttu-id="12bb0-126">StrongNameKeyGen 메서드</span><span class="sxs-lookup"><span data-stu-id="12bb0-126">StrongNameKeyGen Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md)  
 [<span data-ttu-id="12bb0-127">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="12bb0-127">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
