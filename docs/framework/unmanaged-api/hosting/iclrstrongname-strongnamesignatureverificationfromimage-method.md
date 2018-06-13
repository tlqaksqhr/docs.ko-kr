---
title: ICLRStrongName::StrongNameSignatureVerificationFromImage 메서드
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameSignatureVerificationFromImage
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameSignatureVerificationFromImage
helpviewer_keywords:
- ICLRStrongName::StrongNameSignatureVerificationFromImage method [.NET Framework hosting]
- StrongNameSignatureVerificationFromImage method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: da91c138-ee30-4fd4-a040-464d97d7e41a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 60dbb8d8461015c791a70d6c2617b1c81e5ba17f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33434270"
---
# <a name="iclrstrongnamestrongnamesignatureverificationfromimage-method"></a><span data-ttu-id="4d922-102">ICLRStrongName::StrongNameSignatureVerificationFromImage 메서드</span><span class="sxs-lookup"><span data-stu-id="4d922-102">ICLRStrongName::StrongNameSignatureVerificationFromImage Method</span></span>
<span data-ttu-id="4d922-103">연결된 된 공개 키가 이미 메모리에 매핑되어 있는 어셈블리가 올바른지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d922-103">Verifies that an assembly that has already been mapped to memory is valid for the associated public key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d922-104">구문</span><span class="sxs-lookup"><span data-stu-id="4d922-104">Syntax</span></span>  
  
```  
HRESULT StrongNameSignatureVerificationFromImage (  
    [in]  BYTE    *pbBase,  
    [in]  DWORD   dwLength,  
    [in]  DWORD   dwInFlags,  
    [out] DWORD   *pdwOutFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4d922-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4d922-105">Parameters</span></span>  
 `pbBase`  
 <span data-ttu-id="4d922-106">[in] 매핑된 어셈블리 매니페스트의 상대 가상 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="4d922-106">[in] The relative virtual address of the mapped assembly manifest.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="4d922-107">[in] 매핑된 이미지를 바이트 단위로 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="4d922-107">[in] The size, in bytes, of the mapped image.</span></span>  
  
 `dwInFlags`  
 <span data-ttu-id="4d922-108">[in] 확인 동작에 영향을 주는 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="4d922-108">[in] Flags that influence verification behavior.</span></span> <span data-ttu-id="4d922-109">다음 값이 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d922-109">The following values are supported:</span></span>  
  
-   <span data-ttu-id="4d922-110">`SN_INFLAG_FORCE_VER` (0x00000001)-강제로 레지스트리 설정을 재정의 해야 하는 경우에 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d922-110">`SN_INFLAG_FORCE_VER` (0x00000001) - Forces verification even if it is necessary to override registry settings.</span></span>  
  
-   <span data-ttu-id="4d922-111">`SN_INFLAG_INSTALL` (0x00000002)-이 이미지에 수행 된 첫 번째 확인 임을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d922-111">`SN_INFLAG_INSTALL` (0x00000002) - Specifies that this is the first verification performed on this image.</span></span>  
  
-   <span data-ttu-id="4d922-112">`SN_INFLAG_ADMIN_ACCESS` (0x00000004)-캐시 관리 권한이 있는 사용자 에게만 액세스를 사용할 수 있음을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d922-112">`SN_INFLAG_ADMIN_ACCESS` (0x00000004) - Specifies that the cache will allow access only to users who have administrative privileges.</span></span>  
  
-   <span data-ttu-id="4d922-113">`SN_INFLAG_USER_ACCESS` (0x00000008)-어셈블리 현재 사용자에만 액세스할 수 있는지를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d922-113">`SN_INFLAG_USER_ACCESS` (0x00000008) - Specifies that the assembly will be accessible only to the current user.</span></span>  
  
-   <span data-ttu-id="4d922-114">`SN_INFLAG_ALL_ACCESS` (0x00000010)-캐시의 액세스 제한이 않음을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d922-114">`SN_INFLAG_ALL_ACCESS` (0x00000010) - Specifies that the cache will provide no guarantees of access restriction.</span></span>  
  
-   <span data-ttu-id="4d922-115">`SN_INFLAG_RUNTIME` (0x80000000)-내부 디버깅 하기 위해 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d922-115">`SN_INFLAG_RUNTIME` (0x80000000) - Reserved for internal debugging.</span></span>  
  
 `pdwOutFlags`  
 <span data-ttu-id="4d922-116">[out] 출력 추가 정보에 대 한 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="4d922-116">[out] A flag for additional output information.</span></span> <span data-ttu-id="4d922-117">다음 값이 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d922-117">The following value is supported:</span></span>  
  
-   <span data-ttu-id="4d922-118">`SN_OUTFLAG_WAS_VERIFIED` 이 값은로 설정 (0x00000001)- `false` 확인 레지스트리 설정으로 인해 성공 했는지를 지정 하려면.</span><span class="sxs-lookup"><span data-stu-id="4d922-118">`SN_OUTFLAG_WAS_VERIFIED` (0x00000001) - This value is set to `false` to specify that the verification succeeded due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4d922-119">반환 값</span><span class="sxs-lookup"><span data-stu-id="4d922-119">Return Value</span></span>  
 <span data-ttu-id="4d922-120">`S_OK` 메서드가 성공적으로 완료 하는 경우 그렇지 않으면 실패를 나타내는 HRESULT 값 (참조 [일반적인 HRESULT 값](http://go.microsoft.com/fwlink/?LinkId=213878) 목록에 대 한).</span><span class="sxs-lookup"><span data-stu-id="4d922-120">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4d922-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4d922-121">Requirements</span></span>  
 <span data-ttu-id="4d922-122">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4d922-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4d922-123">**헤더:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="4d922-123">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="4d922-124">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="4d922-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4d922-125">**.NET framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4d922-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d922-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4d922-126">See Also</span></span>  
 [<span data-ttu-id="4d922-127">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4d922-127">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
