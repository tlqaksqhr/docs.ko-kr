---
title: "ICLRStrongName::StrongNameTokenFromAssemblyEx 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRStrongName.StrongNameTokenFromAssemblyEx
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRStrongName::StrongNameTokenFromAssemblyEx
helpviewer_keywords:
- StrongNameTokenFromAssemblyEx method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameTokenFromAssemblyEx method [.NET Framework hosting]
ms.assetid: 648ea90e-5e60-40a0-a56a-3e61bf2fba7c
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5b8b3437d8c07cd57a4791995890cab1b06aafc6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="iclrstrongnamestrongnametokenfromassemblyex-method"></a><span data-ttu-id="64a8a-102">ICLRStrongName::StrongNameTokenFromAssemblyEx 메서드</span><span class="sxs-lookup"><span data-stu-id="64a8a-102">ICLRStrongName::StrongNameTokenFromAssemblyEx Method</span></span>
<span data-ttu-id="64a8a-103">지정 된 어셈블리 파일에서 강력한 이름 토큰을 만들고 공개 키 토큰을 나타내는 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="64a8a-103">Creates a strong name token from the specified assembly file, and returns the public key that the token represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64a8a-104">구문</span><span class="sxs-lookup"><span data-stu-id="64a8a-104">Syntax</span></span>  
  
```  
HRESULT StrongNameTokenFromAssemblyEx (  
    [in]  LPCWSTR   wszFilePath,  
    [out] BYTE      **ppbStrongNameToken,  
    [out] ULONG     *pcbStrongNameToken,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="64a8a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="64a8a-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="64a8a-106">[in] 경로 어셈블리에 대 한 이식 가능한 실행 (PE) 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="64a8a-106">[in] The path to the portable executable (PE) file for the assembly.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="64a8a-107">[out] 반환 된 강력한 이름 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="64a8a-107">[out] The returned strong name token.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="64a8a-108">[out] 강력한 이름 토큰의 바이트 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="64a8a-108">[out] The size, in bytes, of the strong name token.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="64a8a-109">[out] 반환 된 공개 키입니다.</span><span class="sxs-lookup"><span data-stu-id="64a8a-109">[out] The returned public key.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="64a8a-110">[out] 공개 키를 바이트 단위로 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="64a8a-110">[out] The size, in bytes, of the public key.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="64a8a-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="64a8a-111">Return Value</span></span>  
 <span data-ttu-id="64a8a-112">`S_OK`메서드가 성공적으로 완료 하는 경우 그렇지 않으면 실패를 나타내는 HRESULT 값 (참조 [일반적인 HRESULT 값](http://go.microsoft.com/fwlink/?LinkId=213878) 목록에 대 한).</span><span class="sxs-lookup"><span data-stu-id="64a8a-112">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="64a8a-113">설명</span><span class="sxs-lookup"><span data-stu-id="64a8a-113">Remarks</span></span>  
 <span data-ttu-id="64a8a-114">강력한 이름 토큰에는 공개 키의 축약 된 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="64a8a-114">A strong name token is the shortened form of a public key.</span></span> <span data-ttu-id="64a8a-115">토큰은 어셈블리에 서명 하는 데 사용 되는 공개 키에서 생성 되는 64 비트 해시입니다.</span><span class="sxs-lookup"><span data-stu-id="64a8a-115">The token is a 64-bit hash that is created from the public key used to sign the assembly.</span></span> <span data-ttu-id="64a8a-116">어셈블리에 대 한 강력한 이름의 일부인 토큰과 어셈블리 메타 데이터에서 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64a8a-116">The token is a part of the strong name for the assembly, and can be read from the assembly metadata.</span></span>  
  
 <span data-ttu-id="64a8a-117">호출 해야 키를 검색 한 후 토큰이 생성 됩니다는 [iclrstrongname:: Strongnamefreebuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) 메서드 할당 된 메모리를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="64a8a-117">After the key is retrieved and the token is created, you should call the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method to release the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="64a8a-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="64a8a-118">Requirements</span></span>  
 <span data-ttu-id="64a8a-119">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="64a8a-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="64a8a-120">**헤더:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="64a8a-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="64a8a-121">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="64a8a-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="64a8a-122">**.NET framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="64a8a-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64a8a-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="64a8a-123">See Also</span></span>  
 [<span data-ttu-id="64a8a-124">StrongNameTokenFromAssembly 메서드</span><span class="sxs-lookup"><span data-stu-id="64a8a-124">StrongNameTokenFromAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassembly-method.md)  
 [<span data-ttu-id="64a8a-125">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="64a8a-125">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
