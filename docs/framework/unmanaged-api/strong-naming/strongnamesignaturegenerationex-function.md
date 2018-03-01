---
title: "StrongNameSignatureGenerationEx 함수"
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
- StrongNameSignatureGenerationEx
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureGenerationEx
helpviewer_keywords:
- StrongNameSignatureGenerationEx function [.NET Framework strong naming]
ms.assetid: 9a75469e-aa49-4e32-ad48-3bafd5202f09
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4f68befd145649e6d8921e160d302cdb81000a9a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="strongnamesignaturegenerationex-function"></a><span data-ttu-id="c3dc6-102">StrongNameSignatureGenerationEx 함수</span><span class="sxs-lookup"><span data-stu-id="c3dc6-102">StrongNameSignatureGenerationEx Function</span></span>
<span data-ttu-id="c3dc6-103">지정된 된 플래그에 따라 지정된 된 어셈블리에 대 한 강력한 이름 서명을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="c3dc6-103">Generates a strong name signature for the specified assembly, according to the specified flags.</span></span>  
  
 <span data-ttu-id="c3dc6-104">이 함수는 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c3dc6-104">This function has been deprecated.</span></span> <span data-ttu-id="c3dc6-105">사용 하 여 [iclrstrongname:: Strongnamesignaturegenerationex](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegenerationex-method.md) 메서드 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3dc6-105">Use the [ICLRStrongName::StrongNameSignatureGenerationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegenerationex-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3dc6-106">구문</span><span class="sxs-lookup"><span data-stu-id="c3dc6-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameSignatureGenerationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbSignatureBlob,  
    [out] ULONG     *pcbSignatureBlob,  
    [in]  DWORD     dwFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c3dc6-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c3dc6-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="c3dc6-108">[in] 강력한 이름 서명을 생성 될 어셈블리의 매니페스트가 포함 된 파일 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="c3dc6-108">[in] The path to the file that contains the manifest of the assembly for which the strong name signature will be generated.</span></span>  
  
 `wszKeyContainer`  
 <span data-ttu-id="c3dc6-109">[in] 공개/개인 키 쌍을 포함 하는 키 컨테이너의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c3dc6-109">[in] The name of the key container that contains the public/private key pair.</span></span>  
  
 <span data-ttu-id="c3dc6-110">경우 `pbKeyBlob` 매개 변수가 null 이면 `wszKeyContainer` 암호화 서비스 공급자 (CSP) 내에서 유효한 컨테이너를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3dc6-110">If `pbKeyBlob` is null, `wszKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="c3dc6-111">이 경우에 컨테이너에 저장 된 키 쌍 파일에 서명 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c3dc6-111">In this case, the key pair stored in the container is used to sign the file.</span></span>  
  
 <span data-ttu-id="c3dc6-112">경우 `pbKeyBlob` null이 아니면 키 쌍 가정 키 binary large object (BLOB)에 포함 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3dc6-112">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="c3dc6-113">[in] 공개/개인 키 쌍에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c3dc6-113">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="c3dc6-114">이 쌍은 win32 만든 형식 `CryptExportKey` 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="c3dc6-114">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="c3dc6-115">경우 `pbKeyBlob` 가 null 이면에서 지정한 키 컨테이너 `wszKeyContainer` 키 쌍을 포함 하는로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c3dc6-115">If `pbKeyBlob` is null, the key container specified by `wszKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="c3dc6-116">[in] 를 바이트 단위로 크기의 `pbKeyBlob`합니다.</span><span class="sxs-lookup"><span data-stu-id="c3dc6-116">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbSignatureBlob`  
 <span data-ttu-id="c3dc6-117">[out] 공용 언어 런타임 시그니처를 반환 하는 위치에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c3dc6-117">[out] A pointer to the location to which the common language runtime returns the signature.</span></span> <span data-ttu-id="c3dc6-118">경우 `ppbSignatureBlob` 가 null 이면 런타임에 서명을 저장 하 여 지정 된 파일에 `wszFilePath`합니다.</span><span class="sxs-lookup"><span data-stu-id="c3dc6-118">If `ppbSignatureBlob` is null, the runtime stores the signature in the file specified by `wszFilePath`.</span></span>  
  
 <span data-ttu-id="c3dc6-119">경우 `ppbSignatureBlob` 은 null이 아닌 공용 언어 런타임 시그니처를 반환 하는 공간을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3dc6-119">If `ppbSignatureBlob` is not null, the common language runtime allocates space in which to return the signature.</span></span> <span data-ttu-id="c3dc6-120">호출자에 게 사용 하 여이 공간을 해제 해야 합니다는 [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="c3dc6-120">The caller must free this space using the [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) function.</span></span>  
  
 `pcbSignatureBlob`  
 <span data-ttu-id="c3dc6-121">[out] 반환 된 서명의 바이트 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="c3dc6-121">[out] The size, in bytes, of the returned signature.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="c3dc6-122">[in] 하나 이상의 다음 값 중:</span><span class="sxs-lookup"><span data-stu-id="c3dc6-122">[in] One or more of the following values:</span></span>  
  
-   <span data-ttu-id="c3dc6-123">`SN_SIGN_ALL_FILES`(0x00000001)-연결 된 모듈에 대 한 모든 해시를 다시 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3dc6-123">`SN_SIGN_ALL_FILES` (0x00000001) - Recompute all hashes for linked modules.</span></span>  
  
-   <span data-ttu-id="c3dc6-124">`SN_TEST_SIGN`(0x00000002)-테스트 어셈블리를 서명 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3dc6-124">`SN_TEST_SIGN` (0x00000002) - Test-sign the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c3dc6-125">반환 값</span><span class="sxs-lookup"><span data-stu-id="c3dc6-125">Return Value</span></span>  
 <span data-ttu-id="c3dc6-126">`true`성공적으로 완료 됩니다. 그렇지 않으면 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="c3dc6-126">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c3dc6-127">설명</span><span class="sxs-lookup"><span data-stu-id="c3dc6-127">Remarks</span></span>  
 <span data-ttu-id="c3dc6-128">Null을 지정 `wszFilePath` 시그니처를 만들지 않고 서명 크기를 계산 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3dc6-128">Specify null for `wszFilePath` to calculate the size of the signature without creating the signature.</span></span>  
  
 <span data-ttu-id="c3dc6-129">서명은 수는 파일에 직접 저장 하거나 호출자에 게 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3dc6-129">The signature can be either stored directly in the file, or returned to the caller.</span></span>  
  
 <span data-ttu-id="c3dc6-130">경우 `SN_SIGN_ALL_FILES` 지정 되어 있지만 공개 키 포함 되지 않습니다 (둘 다 `pbKeyBlob` 및 `wszFilePath` null), 링크 된 모듈에 대 한 해시를 다시 계산할지 있지만 어셈블리 다시 서명 되지 않은 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3dc6-130">If `SN_SIGN_ALL_FILES` is specified but a public key is not included (both `pbKeyBlob` and `wszFilePath` are null), hashes for linked modules are recomputed, but the assembly is not re-signed.</span></span>  
  
 <span data-ttu-id="c3dc6-131">경우 `SN_TEST_SIGN` 지정, 공용 언어 런타임 헤더 어셈블리가 강력한 이름으로 서명 되었음을 나타내도록 수정 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c3dc6-131">If `SN_TEST_SIGN` is specified, the common language runtime header is not modified to indicate that the assembly is signed with a strong name.</span></span>  
  
 <span data-ttu-id="c3dc6-132">경우는 `StrongNameSignatureGenerationEx` 함수는 성공적으로 완료를 호출 하지는 [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) 함수를 마지막으로 생성 된 오류를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3dc6-132">If the `StrongNameSignatureGenerationEx` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c3dc6-133">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c3dc6-133">Requirements</span></span>  
 <span data-ttu-id="c3dc6-134">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c3dc6-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c3dc6-135">**헤더:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="c3dc6-135">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="c3dc6-136">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="c3dc6-136">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c3dc6-137">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c3dc6-137">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3dc6-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c3dc6-138">See Also</span></span>  
 [<span data-ttu-id="c3dc6-139">StrongNameSignatureGenerationEx 메서드</span><span class="sxs-lookup"><span data-stu-id="c3dc6-139">StrongNameSignatureGenerationEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)  
 [<span data-ttu-id="c3dc6-140">StrongNameSignatureGeneration 메서드</span><span class="sxs-lookup"><span data-stu-id="c3dc6-140">StrongNameSignatureGeneration Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md)  
 [<span data-ttu-id="c3dc6-141">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c3dc6-141">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
