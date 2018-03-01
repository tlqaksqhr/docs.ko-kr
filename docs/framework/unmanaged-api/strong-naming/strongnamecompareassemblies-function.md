---
title: "StrongNameCompareAssemblies 함수"
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
- StrongNameCompareAssemblies
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameCompareAssemblies
helpviewer_keywords:
- StrongNameCompareAssemblies function [.NET Framework strong naming]
ms.assetid: 763f2375-efc6-4219-8806-a3b0567ef72b
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1ed98b1713427a71c73c30ddd64188f61d51045c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="strongnamecompareassemblies-function"></a><span data-ttu-id="07e56-102">StrongNameCompareAssemblies 함수</span><span class="sxs-lookup"><span data-stu-id="07e56-102">StrongNameCompareAssemblies Function</span></span>
<span data-ttu-id="07e56-103">두 어셈블리가 강력한 이름 서명만 다른 지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="07e56-103">Determines whether two assemblies differ only by their strong name signatures.</span></span>  
  
 <span data-ttu-id="07e56-104">이 함수는 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="07e56-104">This function has been deprecated.</span></span> <span data-ttu-id="07e56-105">사용 하 여 [iclrstrongname:: Strongnamecompareassemblies](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamecompareassemblies-method.md) 메서드 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="07e56-105">Use the [ICLRStrongName::StrongNameCompareAssemblies](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamecompareassemblies-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07e56-106">구문</span><span class="sxs-lookup"><span data-stu-id="07e56-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameCompareAssemblies (  
    [in]  LPCWSTR   wszAssembly1,  
    [in]  LPCWSTR   wszAssembly2,  
    [out] DWORD     *pdwResult  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="07e56-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="07e56-107">Parameters</span></span>  
 `wszAssembly1`  
 <span data-ttu-id="07e56-108">[in] 첫 번째 어셈블리에 대 한 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="07e56-108">[in] The path to the first assembly.</span></span>  
  
 `wszAssembly2`  
 <span data-ttu-id="07e56-109">[in] 두 번째 어셈블리에 대 한 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="07e56-109">[in] The path to the second assembly.</span></span>  
  
 `pdwResult`  
 <span data-ttu-id="07e56-110">[out] 다음 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="07e56-110">[out] One of the following values:</span></span>  
  
-   <span data-ttu-id="07e56-111">`SN_CMP_DIFFERENT`(0)-어셈블리가 서로 다른 데이터를 포함 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="07e56-111">`SN_CMP_DIFFERENT` (0) - Specifies that the assemblies contain different data.</span></span>  
  
-   <span data-ttu-id="07e56-112">`SN_CMP_IDENTICAL`(1)-어셈블리를 정확히 동일한 경우 해당 서명과 체크섬을 포함 하 여 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="07e56-112">`SN_CMP_IDENTICAL` (1) - Specifies that the assemblies are exactly the same, including their signatures and checksum.</span></span>  
  
-   <span data-ttu-id="07e56-113">`SN_CMP_SIGONLY`(2)-서명 및 체크섬을 통해서만 어셈블리가 서명만 다른 지를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="07e56-113">`SN_CMP_SIGONLY` (2) - Specifies that the assemblies differ only by signature and checksum.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="07e56-114">반환 값</span><span class="sxs-lookup"><span data-stu-id="07e56-114">Return Value</span></span>  
 <span data-ttu-id="07e56-115">`true`성공적으로 완료 됩니다. 그렇지 않으면 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="07e56-115">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="07e56-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="07e56-116">Requirements</span></span>  
 <span data-ttu-id="07e56-117">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="07e56-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="07e56-118">**헤더:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="07e56-118">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="07e56-119">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="07e56-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="07e56-120">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="07e56-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="07e56-121">설명</span><span class="sxs-lookup"><span data-stu-id="07e56-121">Remarks</span></span>  
 <span data-ttu-id="07e56-122">어셈블리의 강력한 이름 서명을 어셈블리의 텍스트 이름, 버전, 문화권 및 공개 키 토큰으로 이루어져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07e56-122">The strong name signature of an assembly consists of the assembly's text name, version, culture, and public key token.</span></span>  
  
 <span data-ttu-id="07e56-123">경우는 `StrongNameCompareAssemblies` 함수는 성공적으로 완료를 호출 하지는 [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) 함수를 마지막으로 생성 된 오류를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="07e56-123">If the `StrongNameCompareAssemblies` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07e56-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="07e56-124">See Also</span></span>  
 [<span data-ttu-id="07e56-125">StrongNameCompareAssemblies 메서드</span><span class="sxs-lookup"><span data-stu-id="07e56-125">StrongNameCompareAssemblies Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamecompareassemblies-method.md)  
 [<span data-ttu-id="07e56-126">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="07e56-126">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
