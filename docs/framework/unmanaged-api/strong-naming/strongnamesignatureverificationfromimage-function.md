---
title: "StrongNameSignatureVerificationFromImage 함수"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: StrongNameSignatureVerificationFromImage
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: StrongNameSignatureVerificationFromImage
helpviewer_keywords: StrongnameSignatureVerificationFromImage function [.NET Framework strong naming]
ms.assetid: 9fb144d2-07e0-4a0e-8e05-907bbb6c9e03
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 178dcbae4f8ec40ac9ef14fc00109c83ab87c21a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="strongnamesignatureverificationfromimage-function"></a><span data-ttu-id="8e6d9-102">StrongNameSignatureVerificationFromImage 함수</span><span class="sxs-lookup"><span data-stu-id="8e6d9-102">StrongNameSignatureVerificationFromImage Function</span></span>
<span data-ttu-id="8e6d9-103">연결된 된 공개 키가 이미 메모리에 매핑되어 있는 어셈블리가 올바른지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e6d9-103">Verifies that an assembly that has already been mapped to memory is valid for the associated public key.</span></span>  
  
 <span data-ttu-id="8e6d9-104">이 함수는 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8e6d9-104">This function has been deprecated.</span></span> <span data-ttu-id="8e6d9-105">사용 하 여 [ICLRStrongName::StrongNameVerificationFromImage](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationfromimage-method.md) 메서드 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e6d9-105">Use the [ICLRStrongName::StrongNameVerificationFromImage](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationfromimage-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e6d9-106">구문</span><span class="sxs-lookup"><span data-stu-id="8e6d9-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameSignatureVerificationFromImage (  
    [in]  BYTE    *pbBase,  
    [in]  DWORD   dwLength,  
    [in]  DWORD   dwInFlags,  
    [out] DWORD   *pdwOutFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8e6d9-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8e6d9-107">Parameters</span></span>  
 `pbBase`  
 <span data-ttu-id="8e6d9-108">[in] 매핑된 어셈블리 매니페스트의 상대 가상 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="8e6d9-108">[in] The relative virtual address of the mapped assembly manifest.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="8e6d9-109">[in] 매핑된 이미지를 바이트 단위로 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="8e6d9-109">[in] The size, in bytes, of the mapped image.</span></span>  
  
 `dwInFlags`  
 <span data-ttu-id="8e6d9-110">[in] 확인 동작에 영향을 주는 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="8e6d9-110">[in] Flags that influence verification behavior.</span></span> <span data-ttu-id="8e6d9-111">다음 값이 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e6d9-111">The following values are supported:</span></span>  
  
-   <span data-ttu-id="8e6d9-112">`SN_INFLAG_FORCE_VER`(0x00000001)-강제로 레지스트리 설정을 재정의 해야 하는 경우에 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e6d9-112">`SN_INFLAG_FORCE_VER` (0x00000001) - Forces verification even if it is necessary to override registry settings.</span></span>  
  
-   <span data-ttu-id="8e6d9-113">`SN_INFLAG_INSTALL`(0x00000002)-이 이미지에 수행 된 첫 번째 확인 임을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e6d9-113">`SN_INFLAG_INSTALL` (0x00000002) - Specifies that this is the first verification performed on this image.</span></span>  
  
-   <span data-ttu-id="8e6d9-114">`SN_INFLAG_ADMIN_ACCESS`(0x00000004)-캐시 관리 권한이 있는 사용자 에게만 액세스를 사용할 수 있음을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e6d9-114">`SN_INFLAG_ADMIN_ACCESS` (0x00000004) - Specifies that the cache will allow access only to users who have administrative privileges.</span></span>  
  
-   <span data-ttu-id="8e6d9-115">`SN_INFLAG_USER_ACCESS`(0x00000008)-어셈블리 현재 사용자에만 액세스할 수 있는지를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e6d9-115">`SN_INFLAG_USER_ACCESS` (0x00000008) - Specifies that the assembly will be accessible only to the current user.</span></span>  
  
-   <span data-ttu-id="8e6d9-116">`SN_INFLAG_ALL_ACCESS`(0x00000010)-캐시의 액세스 제한이 않음을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e6d9-116">`SN_INFLAG_ALL_ACCESS` (0x00000010) - Specifies that the cache will provide no guarantees of access restriction.</span></span>  
  
-   <span data-ttu-id="8e6d9-117">`SN_INFLAG_RUNTIME`(0x80000000)-내부 디버깅 하기 위해 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e6d9-117">`SN_INFLAG_RUNTIME` (0x80000000) - Reserved for internal debugging.</span></span>  
  
 `pdwOutFlags`  
 <span data-ttu-id="8e6d9-118">[out] 출력 추가 정보에 대 한 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="8e6d9-118">[out] A flag for additional output information.</span></span> <span data-ttu-id="8e6d9-119">다음 값이 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e6d9-119">The following value is supported:</span></span>  
  
-   <span data-ttu-id="8e6d9-120">`SN_OUTFLAG_WAS_VERIFIED`이 값은로 설정 (0x00000001)- `false` 확인 레지스트리 설정으로 인해 성공 했는지를 지정 하려면.</span><span class="sxs-lookup"><span data-stu-id="8e6d9-120">`SN_OUTFLAG_WAS_VERIFIED` (0x00000001) - This value is set to `false` to specify that the verification succeeded due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8e6d9-121">반환 값</span><span class="sxs-lookup"><span data-stu-id="8e6d9-121">Return Value</span></span>  
 <span data-ttu-id="8e6d9-122">`true`성공적으로 완료 됩니다. 그렇지 않으면 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="8e6d9-122">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8e6d9-123">설명</span><span class="sxs-lookup"><span data-stu-id="8e6d9-123">Remarks</span></span>  
 <span data-ttu-id="8e6d9-124">경우는 `StrongNameSignatureVerificationFromImage` 함수는 성공적으로 완료를 호출 하지는 [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) 함수를 마지막으로 생성 된 오류를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e6d9-124">If the `StrongNameSignatureVerificationFromImage` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8e6d9-125">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8e6d9-125">Requirements</span></span>  
 <span data-ttu-id="8e6d9-126">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8e6d9-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8e6d9-127">**헤더:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="8e6d9-127">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="8e6d9-128">**라이브러리:** mscoree.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="8e6d9-128">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="8e6d9-129">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8e6d9-129">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e6d9-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8e6d9-130">See Also</span></span>  
 [<span data-ttu-id="8e6d9-131">StrongNameSignatureVerificationFromImage 메서드</span><span class="sxs-lookup"><span data-stu-id="8e6d9-131">StrongNameSignatureVerificationFromImage Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationfromimage-method.md)  
 [<span data-ttu-id="8e6d9-132">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8e6d9-132">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
