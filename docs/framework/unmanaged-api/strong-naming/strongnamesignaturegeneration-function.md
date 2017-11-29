---
title: "StrongNameSignatureGeneration 함수"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: StrongNameSignatureGeneration
api_location:
- mscoree.dll
- mscorsn.dll
api_type: DLLExport
f1_keywords: StrongNameSignatureGeneration
helpviewer_keywords: StrongNameSignatureGeneration function [.NET Framework strong naming]
ms.assetid: 839b765c-3e41-44ce-bf1b-dc10453db18e
caps.latest.revision: "19"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 26900b73e4c0b8b7501a59c3706966df5cf46120
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="strongnamesignaturegeneration-function"></a><span data-ttu-id="eeca8-102">StrongNameSignatureGeneration 함수</span><span class="sxs-lookup"><span data-stu-id="eeca8-102">StrongNameSignatureGeneration Function</span></span>
<span data-ttu-id="eeca8-103">지정된 된 어셈블리에 대 한 강력한 이름 서명을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="eeca8-103">Generates a strong name signature for the specified assembly.</span></span>  
  
 <span data-ttu-id="eeca8-104">이 함수는 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="eeca8-104">This function has been deprecated.</span></span> <span data-ttu-id="eeca8-105">사용 하 여 [iclrstrongname:: Strongnamesignaturegeneration](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md) 메서드 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="eeca8-105">Use the [ICLRStrongName::StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eeca8-106">구문</span><span class="sxs-lookup"><span data-stu-id="eeca8-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameSignatureGeneration (   
    [in]  LPCWSTR   wszFilePath,  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbSignatureBlob,  
    [out] ULONG     *pcbSignatureBlob  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="eeca8-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="eeca8-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="eeca8-108">[in] 강력한 이름 서명을 생성 될 어셈블리의 매니페스트가 포함 된 파일 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="eeca8-108">[in] The path to the file that contains the manifest of the assembly for which the strong name signature will be generated.</span></span>  
  
 `wszKeyContainer`  
 <span data-ttu-id="eeca8-109">[in] 공개/개인 키 쌍을 포함 하는 키 컨테이너의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="eeca8-109">[in] The name of the key container that contains the public/private key pair.</span></span>  
  
 <span data-ttu-id="eeca8-110">경우 `pbKeyBlob` 매개 변수가 null 이면 `wszKeyContainer` 암호화 서비스 공급자 (CSP) 내에서 유효한 컨테이너를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eeca8-110">If `pbKeyBlob` is null, `wszKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="eeca8-111">이 경우에 컨테이너에 저장 된 키 쌍 파일에 서명 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eeca8-111">In this case, the key pair stored in the container is used to sign the file.</span></span>  
  
 <span data-ttu-id="eeca8-112">경우 `pbKeyBlob` null이 아니면 키 쌍 가정 키 binary large object (BLOB)에 포함 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eeca8-112">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="eeca8-113">키 서명 키 1024 비트 Rivest-Shamir-Adleman (RSA) 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eeca8-113">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="eeca8-114">다른 형식의 키이 이번에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eeca8-114">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="eeca8-115">[in] 공개/개인 키 쌍에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="eeca8-115">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="eeca8-116">이 쌍은 win32 만든 형식 `CryptExportKey` 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="eeca8-116">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="eeca8-117">경우 `pbKeyBlob` 가 null 이면에서 지정한 키 컨테이너 `wszKeyContainer` 키 쌍을 포함 하는로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eeca8-117">If `pbKeyBlob` is null, the key container specified by `wszKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="eeca8-118">[in] 를 바이트 단위로 크기의 `pbKeyBlob`합니다.</span><span class="sxs-lookup"><span data-stu-id="eeca8-118">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbSignatureBlob`  
 <span data-ttu-id="eeca8-119">[out] 공용 언어 런타임 시그니처를 반환 하는 위치에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="eeca8-119">[out] A pointer to the location to which the common language runtime returns the signature.</span></span> <span data-ttu-id="eeca8-120">경우 `ppbSignatureBlob` 가 null 이면 런타임에 서명을 저장 하 여 지정 된 파일에 `wszFilePath`합니다.</span><span class="sxs-lookup"><span data-stu-id="eeca8-120">If `ppbSignatureBlob` is null, the runtime stores the signature in the file specified by `wszFilePath`.</span></span>  
  
 <span data-ttu-id="eeca8-121">경우 `ppbSignatureBlob` 은 null이 아닌 공용 언어 런타임 시그니처를 반환 하는 공간을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="eeca8-121">If `ppbSignatureBlob` is not null, the common language runtime allocates space in which to return the signature.</span></span> <span data-ttu-id="eeca8-122">호출자에 게 사용 하 여이 공간을 해제 해야 합니다는 [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="eeca8-122">The caller must free this space using the [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) function.</span></span>  
  
 `pcbSignatureBlob`  
 <span data-ttu-id="eeca8-123">[out] 반환 된 서명의 바이트 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="eeca8-123">[out] The size, in bytes, of the returned signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="eeca8-124">반환 값</span><span class="sxs-lookup"><span data-stu-id="eeca8-124">Return Value</span></span>  
 <span data-ttu-id="eeca8-125">`true`성공적으로 완료 됩니다. 그렇지 않으면 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="eeca8-125">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eeca8-126">설명</span><span class="sxs-lookup"><span data-stu-id="eeca8-126">Remarks</span></span>  
 <span data-ttu-id="eeca8-127">Null을 지정 `wszFilePath` 시그니처를 만들지 않고 서명 크기를 계산 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="eeca8-127">Specify null for `wszFilePath` to calculate the size of the signature without creating the signature.</span></span>  
  
 <span data-ttu-id="eeca8-128">서명을 수 파일에 직접 저장 하거나 또는 호출자에 게 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="eeca8-128">The signature can be stored either directly in the file, or returned to the caller.</span></span>  
  
 <span data-ttu-id="eeca8-129">경우는 `StrongNameSignatureGeneration` 함수는 성공적으로 완료를 호출 하지는 [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) 함수를 마지막으로 생성 된 오류를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="eeca8-129">If the `StrongNameSignatureGeneration` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eeca8-130">요구 사항</span><span class="sxs-lookup"><span data-stu-id="eeca8-130">Requirements</span></span>  
 <span data-ttu-id="eeca8-131">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="eeca8-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eeca8-132">**헤더:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="eeca8-132">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="eeca8-133">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="eeca8-133">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="eeca8-134">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eeca8-134">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eeca8-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="eeca8-135">See Also</span></span>  
 [<span data-ttu-id="eeca8-136">StrongNameSignatureGeneration 메서드</span><span class="sxs-lookup"><span data-stu-id="eeca8-136">StrongNameSignatureGeneration Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md)  
 [<span data-ttu-id="eeca8-137">StrongNameSignatureGenerationEx 메서드</span><span class="sxs-lookup"><span data-stu-id="eeca8-137">StrongNameSignatureGenerationEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)  
 [<span data-ttu-id="eeca8-138">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="eeca8-138">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
