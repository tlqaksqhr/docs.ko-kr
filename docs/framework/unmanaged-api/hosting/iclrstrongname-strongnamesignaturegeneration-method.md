---
title: "ICLRStrongName::StrongNameSignatureGeneration 메서드"
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
- ICLRStrongName.StrongNameSignatureGeneration
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameSignatureGeneration
helpviewer_keywords:
- StrongNameSignatureGeneration method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameSignatureGeneration method [.NET Framework hosting]
ms.assetid: 4cdb1284-947a-4ed4-94c1-c5ff5cdfce56
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: fcf872dcd1de34aaade06cf26914a75ae971b85b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="iclrstrongnamestrongnamesignaturegeneration-method"></a><span data-ttu-id="9bb99-102">ICLRStrongName::StrongNameSignatureGeneration 메서드</span><span class="sxs-lookup"><span data-stu-id="9bb99-102">ICLRStrongName::StrongNameSignatureGeneration Method</span></span>
<span data-ttu-id="9bb99-103">지정된 된 어셈블리에 대 한 강력한 이름 서명을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="9bb99-103">Generates a strong name signature for the specified assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9bb99-104">구문</span><span class="sxs-lookup"><span data-stu-id="9bb99-104">Syntax</span></span>  
  
```  
HRESULT StrongNameSignatureGeneration (   
    [in]  LPCWSTR   wszFilePath,  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbSignatureBlob,  
    [out] ULONG     *pcbSignatureBlob  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9bb99-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9bb99-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="9bb99-106">[in] 강력한 이름 서명을 생성 될 어셈블리의 매니페스트가 포함 된 파일 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="9bb99-106">[in] The path to the file that contains the manifest of the assembly for which the strong name signature will be generated.</span></span>  
  
 `wszKeyContainer`  
 <span data-ttu-id="9bb99-107">[in] 공개/개인 키 쌍을 포함 하는 키 컨테이너의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="9bb99-107">[in] The name of the key container that contains the public/private key pair.</span></span>  
  
 <span data-ttu-id="9bb99-108">경우 `pbKeyBlob` 매개 변수가 null 이면 `wszKeyContainer` 암호화 서비스 공급자 (CSP) 내에서 유효한 컨테이너를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bb99-108">If `pbKeyBlob` is null, `wszKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="9bb99-109">이 경우에 컨테이너에 저장 된 키 쌍 파일에 서명 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bb99-109">In this case, the key pair stored in the container is used to sign the file.</span></span>  
  
 <span data-ttu-id="9bb99-110">경우 `pbKeyBlob` null이 아니면 키 쌍 가정 키 binary large object (BLOB)에 포함 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bb99-110">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="9bb99-111">키 서명 키 1024 비트 Rivest-Shamir-Adleman (RSA) 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bb99-111">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="9bb99-112">다른 형식의 키이 이번에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bb99-112">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="9bb99-113">[in] 공개/개인 키 쌍에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="9bb99-113">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="9bb99-114">이 쌍은 win32 만든 형식 `CryptExportKey` 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="9bb99-114">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="9bb99-115">경우 `pbKeyBlob` 가 null 이면에서 지정한 키 컨테이너 `wszKeyContainer` 키 쌍을 포함 하는로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bb99-115">If `pbKeyBlob` is null, the key container specified by `wszKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="9bb99-116">[in] 를 바이트 단위로 크기의 `pbKeyBlob`합니다.</span><span class="sxs-lookup"><span data-stu-id="9bb99-116">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbSignatureBlob`  
 <span data-ttu-id="9bb99-117">[out] 공용 언어 런타임 시그니처를 반환 하는 위치에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="9bb99-117">[out] A pointer to the location to which the common language runtime returns the signature.</span></span> <span data-ttu-id="9bb99-118">경우 `ppbSignatureBlob` 가 null 이면 런타임에 서명을 저장 하 여 지정 된 파일에 `wszFilePath`합니다.</span><span class="sxs-lookup"><span data-stu-id="9bb99-118">If `ppbSignatureBlob` is null, the runtime stores the signature in the file specified by `wszFilePath`.</span></span>  
  
 <span data-ttu-id="9bb99-119">경우 `ppbSignatureBlob` 은 null이 아닌 공용 언어 런타임 시그니처를 반환 하는 공간을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bb99-119">If `ppbSignatureBlob` is not null, the common language runtime allocates space in which to return the signature.</span></span> <span data-ttu-id="9bb99-120">호출자에 게 사용 하 여이 공간을 해제 해야 합니다는 [iclrstrongname:: Strongnamefreebuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="9bb99-120">The caller must free this space by using the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbSignatureBlob`  
 <span data-ttu-id="9bb99-121">[out] 반환 된 서명의 바이트 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="9bb99-121">[out] The size, in bytes, of the returned signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9bb99-122">반환 값</span><span class="sxs-lookup"><span data-stu-id="9bb99-122">Return Value</span></span>  
 <span data-ttu-id="9bb99-123">`S_OK`메서드가 성공적으로 완료 하는 경우 그렇지 않으면 실패를 나타내는 HRESULT 값 (참조 [일반적인 HRESULT 값](http://go.microsoft.com/fwlink/?LinkId=213878) 목록에 대 한).</span><span class="sxs-lookup"><span data-stu-id="9bb99-123">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9bb99-124">설명</span><span class="sxs-lookup"><span data-stu-id="9bb99-124">Remarks</span></span>  
 <span data-ttu-id="9bb99-125">Null을 지정 `wszFilePath` 시그니처를 만들지 않고 서명 크기를 계산 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bb99-125">Specify null for `wszFilePath` to calculate the size of the signature without creating the signature.</span></span>  
  
 <span data-ttu-id="9bb99-126">서명을 수 파일에 직접 저장 하거나 또는 호출자에 게 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bb99-126">The signature can be stored either directly in the file, or returned to the caller.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9bb99-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9bb99-127">Requirements</span></span>  
 <span data-ttu-id="9bb99-128">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9bb99-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9bb99-129">**헤더:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="9bb99-129">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="9bb99-130">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="9bb99-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9bb99-131">**.NET framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9bb99-131">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9bb99-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9bb99-132">See Also</span></span>  
 [<span data-ttu-id="9bb99-133">StrongNameSignatureGenerationEx 메서드</span><span class="sxs-lookup"><span data-stu-id="9bb99-133">StrongNameSignatureGenerationEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)  
 [<span data-ttu-id="9bb99-134">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9bb99-134">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
