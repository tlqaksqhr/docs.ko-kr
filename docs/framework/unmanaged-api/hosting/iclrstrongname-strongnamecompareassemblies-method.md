---
title: "ICLRStrongName::StrongNameCompareAssemblies 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRStrongName.StrongNameCompareAssemblies
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRStrongName::StrongNameCompareAssemblies
helpviewer_keywords:
- ICLRStrongName::StrongNameCompareAssemblies method [.NET Framework hosting]
- StrongNameCompareAssemblies method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: b1fb356c-72cf-4aa4-8376-f291a6d97c01
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 96fbeccf76de87a3582bf8c2084d0ca9ad7d27f4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="iclrstrongnamestrongnamecompareassemblies-method"></a><span data-ttu-id="5edfe-102">ICLRStrongName::StrongNameCompareAssemblies 메서드</span><span class="sxs-lookup"><span data-stu-id="5edfe-102">ICLRStrongName::StrongNameCompareAssemblies Method</span></span>
<span data-ttu-id="5edfe-103">두 어셈블리가 강력한 이름 서명만 다른 지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5edfe-103">Determines whether two assemblies differ only by their strong name signatures.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5edfe-104">구문</span><span class="sxs-lookup"><span data-stu-id="5edfe-104">Syntax</span></span>  
  
```  
HRESULT StrongNameCompareAssemblies (  
    [in]  LPCWSTR   wszAssembly1,  
    [in]  LPCWSTR   wszAssembly2,  
    [out] DWORD     *pdwResult  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5edfe-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5edfe-105">Parameters</span></span>  
 `wszAssembly1`  
 <span data-ttu-id="5edfe-106">[in] 첫 번째 어셈블리에 대 한 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="5edfe-106">[in] The path to the first assembly.</span></span>  
  
 `wszAssembly2`  
 <span data-ttu-id="5edfe-107">[in] 두 번째 어셈블리에 대 한 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="5edfe-107">[in] The path to the second assembly.</span></span>  
  
 `pdwResult`  
 <span data-ttu-id="5edfe-108">[out] 다음 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="5edfe-108">[out] One of the following values:</span></span>  
  
-   <span data-ttu-id="5edfe-109">`SN_CMP_DIFFERENT`(0)-어셈블리가 서로 다른 데이터를 포함 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5edfe-109">`SN_CMP_DIFFERENT` (0) - Specifies that the assemblies contain different data.</span></span>  
  
-   <span data-ttu-id="5edfe-110">`SN_CMP_IDENTICAL`(1)-어셈블리를 정확히 동일한 경우 해당 서명과 체크섬을 포함 하 여 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5edfe-110">`SN_CMP_IDENTICAL` (1) - Specifies that the assemblies are exactly the same, including their signatures and checksum.</span></span>  
  
-   <span data-ttu-id="5edfe-111">`SN_CMP_SIGONLY`(2)-서명 및 체크섬을 통해서만 어셈블리가 서명만 다른 지를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5edfe-111">`SN_CMP_SIGONLY` (2) - Specifies that the assemblies differ only by signature and checksum.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5edfe-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="5edfe-112">Return Value</span></span>  
 <span data-ttu-id="5edfe-113">`S_OK`메서드가 성공적으로 완료 하는 경우 그렇지 않으면 실패를 나타내는 HRESULT 값 (참조 [일반적인 HRESULT 값](http://go.microsoft.com/fwlink/?LinkId=213878) 목록에 대 한).</span><span class="sxs-lookup"><span data-stu-id="5edfe-113">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5edfe-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5edfe-114">Requirements</span></span>  
 <span data-ttu-id="5edfe-115">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5edfe-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5edfe-116">**헤더:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="5edfe-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="5edfe-117">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="5edfe-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5edfe-118">**.NET framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5edfe-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5edfe-119">설명</span><span class="sxs-lookup"><span data-stu-id="5edfe-119">Remarks</span></span>  
 <span data-ttu-id="5edfe-120">어셈블리의 강력한 이름 서명을 어셈블리의 텍스트 이름, 버전, 문화권 및 공개 키 토큰으로 이루어져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5edfe-120">The strong name signature of an assembly consists of the assembly's text name, version, culture, and public key token.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5edfe-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5edfe-121">See Also</span></span>  
 [<span data-ttu-id="5edfe-122">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5edfe-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
