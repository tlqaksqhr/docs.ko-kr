---
title: "StrongNameTokenFromAssemblyEx 함수"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: StrongNameTokenFromAssemblyEx
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: StrongNameTokenFromAssemblyEx
helpviewer_keywords: StrongNameTokenFromAssemblyEx function [.NET Framework strong naming]
ms.assetid: 67a8a9f2-dee3-44b2-a1c0-f307a3bdf90f
topic_type: apiref
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5c118455932fd6c0bf44a486effa90632745d0e0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="strongnametokenfromassemblyex-function"></a><span data-ttu-id="83e80-102">StrongNameTokenFromAssemblyEx 함수</span><span class="sxs-lookup"><span data-stu-id="83e80-102">StrongNameTokenFromAssemblyEx Function</span></span>
<span data-ttu-id="83e80-103">지정 된 어셈블리 파일에서 강력한 이름 토큰을 만들고 공개 키 토큰을 나타내는 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="83e80-103">Creates a strong name token from the specified assembly file, and returns the public key that the token represents.</span></span>  
  
 <span data-ttu-id="83e80-104">이 함수는 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="83e80-104">This function has been deprecated.</span></span> <span data-ttu-id="83e80-105">사용 하 여 [iclrstrongname:: Strongnametokenfromassemblyex](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassemblyex-method.md) 메서드 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="83e80-105">Use the [ICLRStrongName::StrongNameTokenFromAssemblyEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassemblyex-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83e80-106">구문</span><span class="sxs-lookup"><span data-stu-id="83e80-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameTokenFromAssemblyEx (  
    [in]  LPCWSTR   wszFilePath,  
    [out] BYTE      **ppbStrongNameToken,  
    [out] ULONG     *pcbStrongNameToken,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="83e80-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="83e80-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="83e80-108">[in] 경로 어셈블리에 대 한 이식 가능한 실행 (PE) 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="83e80-108">[in] The path to the portable executable (PE) file for the assembly.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="83e80-109">[out] 반환 된 강력한 이름 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="83e80-109">[out] The returned strong name token.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="83e80-110">[out] 강력한 이름 토큰의 바이트 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="83e80-110">[out] The size, in bytes, of the strong name token.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="83e80-111">[out] 반환 된 공개 키입니다.</span><span class="sxs-lookup"><span data-stu-id="83e80-111">[out] The returned public key.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="83e80-112">[out] 공개 키를 바이트 단위로 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="83e80-112">[out] The size, in bytes, of the public key.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="83e80-113">반환 값</span><span class="sxs-lookup"><span data-stu-id="83e80-113">Return Value</span></span>  
 <span data-ttu-id="83e80-114">`true`성공적으로 완료 됩니다. 그렇지 않으면 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="83e80-114">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="83e80-115">설명</span><span class="sxs-lookup"><span data-stu-id="83e80-115">Remarks</span></span>  
 <span data-ttu-id="83e80-116">강력한 이름 토큰에는 공개 키의 축약 된 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="83e80-116">A strong name token is the shortened form of a public key.</span></span> <span data-ttu-id="83e80-117">토큰은 어셈블리에 서명 하는 데 사용 되는 공개 키에서 생성 되는 64 비트 해시입니다.</span><span class="sxs-lookup"><span data-stu-id="83e80-117">The token is a 64-bit hash that is created from the public key used to sign the assembly.</span></span> <span data-ttu-id="83e80-118">어셈블리에 대 한 강력한 이름의 일부인 토큰과 어셈블리 메타 데이터에서 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83e80-118">The token is a part of the strong name for the assembly, and can be read from the assembly metadata.</span></span>  
  
 <span data-ttu-id="83e80-119">호출 해야 키를 검색 한 후 토큰이 생성 됩니다는 [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) 함수 할당 된 메모리를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="83e80-119">After the key is retrieved and the token is created, you should call the [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) function to release the allocated memory.</span></span>  
  
 <span data-ttu-id="83e80-120">경우는 `StrongNameTokenFromAssemblyEx` 함수는 성공적으로 완료를 호출 하지는 [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) 함수를 마지막으로 생성 된 오류를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="83e80-120">If the `StrongNameTokenFromAssemblyEx` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83e80-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="83e80-121">Requirements</span></span>  
 <span data-ttu-id="83e80-122">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="83e80-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83e80-123">**헤더:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="83e80-123">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="83e80-124">**라이브러리:** mscoree.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="83e80-124">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="83e80-125">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="83e80-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83e80-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="83e80-126">See Also</span></span>  
 [<span data-ttu-id="83e80-127">StrongNameTokenFromAssemblyEx 메서드</span><span class="sxs-lookup"><span data-stu-id="83e80-127">StrongNameTokenFromAssemblyEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassemblyex-method.md)  
 [<span data-ttu-id="83e80-128">StrongNameTokenFromAssembly 메서드</span><span class="sxs-lookup"><span data-stu-id="83e80-128">StrongNameTokenFromAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassembly-method.md)  
 [<span data-ttu-id="83e80-129">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="83e80-129">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
