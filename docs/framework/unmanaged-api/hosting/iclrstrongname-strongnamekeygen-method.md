---
title: "ICLRStrongName::StrongNameKeyGen 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRStrongName.StrongNameKeyGen
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRStrongName::StrongNameKeyGen
helpviewer_keywords:
- StrongNameKeyGen method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameKeyGen method [.NET Framework hosting]
ms.assetid: ac5c1245-9acf-4271-9c08-3d9b7c670df3
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3b434783d7537c5f6a3127183f66d4b0b3f77534
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="iclrstrongnamestrongnamekeygen-method"></a><span data-ttu-id="f0a1b-102">ICLRStrongName::StrongNameKeyGen 메서드</span><span class="sxs-lookup"><span data-stu-id="f0a1b-102">ICLRStrongName::StrongNameKeyGen Method</span></span>
<span data-ttu-id="f0a1b-103">강력한 이름 사용 하기 위해 새 공개/개인 키 쌍을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f0a1b-103">Creates a new public/private key pair for strong name use.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0a1b-104">구문</span><span class="sxs-lookup"><span data-stu-id="f0a1b-104">Syntax</span></span>  
  
```  
HRESULT StrongNameKeyGen (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f0a1b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f0a1b-105">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="f0a1b-106">[in] 요청 된 키 컨테이너 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="f0a1b-106">[in] The requested key container name.</span></span> <span data-ttu-id="f0a1b-107">`wszKeyContainer`비어 있지 않은 문자열 또는 임시 이름을 생성 하는 null 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0a1b-107">`wszKeyContainer` must either be a non-empty string or null to generate a temporary name.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="f0a1b-108">[in] 등록 키를 유지 여부를 지정 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="f0a1b-108">[in] A value that specifies whether to leave the key registered.</span></span> <span data-ttu-id="f0a1b-109">다음 값이 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0a1b-109">The following values are supported:</span></span>  
  
-   <span data-ttu-id="f0a1b-110">때에 사용 되는 0x00000000- `wszKeyContainer` 임시 키 컨테이너 이름을 생성 하는 null입니다.</span><span class="sxs-lookup"><span data-stu-id="f0a1b-110">0x00000000 - Used when `wszKeyContainer` is null to generate a temporary key container name.</span></span>  
  
-   <span data-ttu-id="f0a1b-111">0x00000001 (`SN_LEAVE_KEY`)-키 왼쪽 등록 해야 함을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0a1b-111">0x00000001 (`SN_LEAVE_KEY`) - Specifies that the key should be left registered.</span></span>  
  
 `ppbKeyBlob`  
 <span data-ttu-id="f0a1b-112">[out] 반환 된 공개/개인 키 쌍입니다.</span><span class="sxs-lookup"><span data-stu-id="f0a1b-112">[out] The returned public/private key pair.</span></span>  
  
 `pcbKeyBlob`  
 <span data-ttu-id="f0a1b-113">[out] 를 바이트 단위로 크기의 `ppbKeyBlob`합니다.</span><span class="sxs-lookup"><span data-stu-id="f0a1b-113">[out] The size, in bytes, of `ppbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f0a1b-114">반환 값</span><span class="sxs-lookup"><span data-stu-id="f0a1b-114">Return Value</span></span>  
 <span data-ttu-id="f0a1b-115">`S_OK`메서드가 성공적으로 완료 하는 경우 그렇지 않으면 실패를 나타내는 HRESULT 값 (참조 [일반적인 HRESULT 값](http://go.microsoft.com/fwlink/?LinkId=213878) 목록에 대 한).</span><span class="sxs-lookup"><span data-stu-id="f0a1b-115">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f0a1b-116">설명</span><span class="sxs-lookup"><span data-stu-id="f0a1b-116">Remarks</span></span>  
 <span data-ttu-id="f0a1b-117">[iclrstrongname:: Strongnamekeygen](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md) 메서드는 1024 비트 키를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f0a1b-117">The [ICLRStrongName::StrongNameKeyGen](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md) method creates a 1024-bit key.</span></span> <span data-ttu-id="f0a1b-118">호출 해야 키를 검색 한 후의 [iclrstrongname:: Strongnamefreebuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) 메서드 할당 된 메모리를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0a1b-118">After the key is retrieved, you should call the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method to release the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0a1b-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f0a1b-119">Requirements</span></span>  
 <span data-ttu-id="f0a1b-120">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f0a1b-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0a1b-121">**헤더:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="f0a1b-121">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="f0a1b-122">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="f0a1b-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f0a1b-123">**.NET framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0a1b-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0a1b-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f0a1b-124">See Also</span></span>  
 [<span data-ttu-id="f0a1b-125">StrongNameKeyGenEx 메서드</span><span class="sxs-lookup"><span data-stu-id="f0a1b-125">StrongNameKeyGenEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygenex-method.md)  
 [<span data-ttu-id="f0a1b-126">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f0a1b-126">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
