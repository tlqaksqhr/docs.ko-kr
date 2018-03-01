---
title: "ICLRStrongName::StrongNameSignatureGenerationEx 메서드"
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
- ICLRStrongName.StrongNameSignatureGenerationEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameSignatureGenerationEx
helpviewer_keywords:
- ICLRStrongName::StrongNameSignatureGenerationEx method [.NET Framework hosting]
- StrongNameSignatureGenerationEx method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: c3f34584-c6e2-41fd-bb44-e44da8546309
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 247bcfa3c9f7a02dea331ff14948a00812fb06e5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="iclrstrongnamestrongnamesignaturegenerationex-method"></a><span data-ttu-id="373df-102">ICLRStrongName::StrongNameSignatureGenerationEx 메서드</span><span class="sxs-lookup"><span data-stu-id="373df-102">ICLRStrongName::StrongNameSignatureGenerationEx Method</span></span>
<span data-ttu-id="373df-103">지정된 된 플래그에 따라 지정된 된 어셈블리에 대 한 강력한 이름 서명을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="373df-103">Generates a strong name signature for the specified assembly, according to the specified flags.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="373df-104">구문</span><span class="sxs-lookup"><span data-stu-id="373df-104">Syntax</span></span>  
  
```  
HRESULT StrongNameSignatureGenerationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbSignatureBlob,  
    [out] ULONG     *pcbSignatureBlob,  
    [in]  DWORD     dwFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="373df-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="373df-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="373df-106">[in] 강력한 이름 서명을 생성 될 어셈블리의 매니페스트가 포함 된 파일 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="373df-106">[in] The path to the file that contains the manifest of the assembly for which the strong name signature will be generated.</span></span>  
  
 `wszKeyContainer`  
 <span data-ttu-id="373df-107">[in] 공개/개인 키 쌍을 포함 하는 키 컨테이너의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="373df-107">[in] The name of the key container that contains the public/private key pair.</span></span>  
  
 <span data-ttu-id="373df-108">경우 `pbKeyBlob` 매개 변수가 null 이면 `wszKeyContainer` 암호화 서비스 공급자 (CSP) 내에서 유효한 컨테이너를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="373df-108">If `pbKeyBlob` is null, `wszKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="373df-109">이 경우에 컨테이너에 저장 된 키 쌍 파일에 서명 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="373df-109">In this case, the key pair stored in the container is used to sign the file.</span></span>  
  
 <span data-ttu-id="373df-110">경우 `pbKeyBlob` null이 아니면 키 쌍 가정 키 binary large object (BLOB)에 포함 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="373df-110">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="373df-111">[in] 공개/개인 키 쌍에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="373df-111">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="373df-112">이 쌍은 win32 만든 형식 `CryptExportKey` 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="373df-112">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="373df-113">경우 `pbKeyBlob` 가 null 이면에서 지정한 키 컨테이너 `wszKeyContainer` 키 쌍을 포함 하는로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="373df-113">If `pbKeyBlob` is null, the key container specified by `wszKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="373df-114">[in] 를 바이트 단위로 크기의 `pbKeyBlob`합니다.</span><span class="sxs-lookup"><span data-stu-id="373df-114">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbSignatureBlob`  
 <span data-ttu-id="373df-115">[out] 공용 언어 런타임 시그니처를 반환 하는 위치에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="373df-115">[out] A pointer to the location to which the common language runtime returns the signature.</span></span> <span data-ttu-id="373df-116">경우 `ppbSignatureBlob` 가 null 이면 런타임에 서명을 저장 하 여 지정 된 파일에 `wszFilePath`합니다.</span><span class="sxs-lookup"><span data-stu-id="373df-116">If `ppbSignatureBlob` is null, the runtime stores the signature in the file specified by `wszFilePath`.</span></span>  
  
 <span data-ttu-id="373df-117">경우 `ppbSignatureBlob` 은 null이 아닌 공용 언어 런타임 시그니처를 반환 하는 공간을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="373df-117">If `ppbSignatureBlob` is not null, the common language runtime allocates space in which to return the signature.</span></span> <span data-ttu-id="373df-118">호출자에 게 사용 하 여이 공간을 해제 해야 합니다는 [iclrstrongname:: Strongnamefreebuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="373df-118">The caller must free this space using the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbSignatureBlob`  
 <span data-ttu-id="373df-119">[out] 반환 된 서명의 바이트 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="373df-119">[out] The size, in bytes, of the returned signature.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="373df-120">[in] 하나 이상의 다음 값 중:</span><span class="sxs-lookup"><span data-stu-id="373df-120">[in] One or more of the following values:</span></span>  
  
-   <span data-ttu-id="373df-121">`SN_SIGN_ALL_FILES`(0x00000001)-연결 된 모듈에 대 한 모든 해시를 다시 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="373df-121">`SN_SIGN_ALL_FILES` (0x00000001) - Recompute all hashes for linked modules.</span></span>  
  
-   <span data-ttu-id="373df-122">`SN_TEST_SIGN`(0x00000002)-테스트 어셈블리를 서명 합니다.</span><span class="sxs-lookup"><span data-stu-id="373df-122">`SN_TEST_SIGN` (0x00000002) - Test-sign the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="373df-123">반환 값</span><span class="sxs-lookup"><span data-stu-id="373df-123">Return Value</span></span>  
 <span data-ttu-id="373df-124">`S_OK`메서드가 성공적으로 완료 하는 경우 그렇지 않으면 실패를 나타내는 HRESULT 값 (참조 [일반적인 HRESULT 값](http://go.microsoft.com/fwlink/?LinkId=213878) 목록에 대 한).</span><span class="sxs-lookup"><span data-stu-id="373df-124">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="373df-125">설명</span><span class="sxs-lookup"><span data-stu-id="373df-125">Remarks</span></span>  
 <span data-ttu-id="373df-126">Null을 지정 `wszFilePath` 시그니처를 만들지 않고 서명 크기를 계산 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="373df-126">Specify null for `wszFilePath` to calculate the size of the signature without creating the signature.</span></span>  
  
 <span data-ttu-id="373df-127">서명은 수는 파일에 직접 저장 하거나 호출자에 게 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="373df-127">The signature can be either stored directly in the file, or returned to the caller.</span></span>  
  
 <span data-ttu-id="373df-128">경우 `SN_SIGN_ALL_FILES` 지정 되어 있지만 공개 키 포함 되지 않습니다 (둘 다 `pbKeyBlob` 및 `wszFilePath` null), 링크 된 모듈에 대 한 해시를 다시 계산할지 있지만 어셈블리 다시 서명 되지 않은 합니다.</span><span class="sxs-lookup"><span data-stu-id="373df-128">If `SN_SIGN_ALL_FILES` is specified but a public key is not included (both `pbKeyBlob` and `wszFilePath` are null), hashes for linked modules are recomputed, but the assembly is not re-signed.</span></span>  
  
 <span data-ttu-id="373df-129">경우 `SN_TEST_SIGN` 지정, 공용 언어 런타임 헤더 어셈블리가 강력한 이름으로 서명 되었음을 나타내도록 수정 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="373df-129">If `SN_TEST_SIGN` is specified, the common language runtime header is not modified to indicate that the assembly is signed with a strong name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="373df-130">요구 사항</span><span class="sxs-lookup"><span data-stu-id="373df-130">Requirements</span></span>  
 <span data-ttu-id="373df-131">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="373df-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="373df-132">**헤더:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="373df-132">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="373df-133">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="373df-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="373df-134">**.NET framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="373df-134">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="373df-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="373df-135">See Also</span></span>  
 [<span data-ttu-id="373df-136">StrongNameSignatureGeneration 메서드</span><span class="sxs-lookup"><span data-stu-id="373df-136">StrongNameSignatureGeneration Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md)  
 [<span data-ttu-id="373df-137">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="373df-137">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
