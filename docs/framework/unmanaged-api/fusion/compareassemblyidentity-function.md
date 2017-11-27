---
title: "CompareAssemblyIdentity 함수"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CompareAssemblyIdentity
api_location:
- fusion.dll
- clr.dll
api_type: COM
f1_keywords: CompareAssemblyIdentity
helpviewer_keywords: CompareAssemblyIdentity function [.NET Framework fusion]
ms.assetid: 8b364ae1-8efa-4744-a7da-81fd093d84d6
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9d9d7b4934d4295ee799fb13d3d749e6b977e644
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="compareassemblyidentity-function"></a><span data-ttu-id="1a3b5-102">CompareAssemblyIdentity 함수</span><span class="sxs-lookup"><span data-stu-id="1a3b5-102">CompareAssemblyIdentity Function</span></span>
<span data-ttu-id="1a3b5-103">동일한 지 여부를 확인 하려면 두 개의 어셈블리 id를 비교 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a3b5-103">Compares two assembly identities to determine whether they are equivalent.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a3b5-104">구문</span><span class="sxs-lookup"><span data-stu-id="1a3b5-104">Syntax</span></span>  
  
```  
STDAPI CompareAssemblyIdentity (  
    [in]  LPCWSTR                  pwzAssemblyIdentity1,  
    [in]  BOOL                     fUnified1,  
    [in]  LPCWSTR                  pwzAssemblyIdentity2,  
    [in]  BOOL                     fUnified2,  
    [out] BOOL                     *pfEquivalent,  
    [out] AssemblyComparisonResult *pResult  
 );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1a3b5-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1a3b5-105">Parameters</span></span>  
 `pwzAssemblyIdentity1`  
 <span data-ttu-id="1a3b5-106">[in] 텍스트 비교에 사용 된 첫 번째 어셈블리의 id입니다.</span><span class="sxs-lookup"><span data-stu-id="1a3b5-106">[in] The textual identity of the first assembly in the comparison.</span></span>  
  
 `fUnified1`  
 <span data-ttu-id="1a3b5-107">[in] 에 대 한 사용자 지정 통합을 나타내는 부울 플래그 `pwzAssemblyIdentity1`합니다.</span><span class="sxs-lookup"><span data-stu-id="1a3b5-107">[in] A Boolean flag that indicates user-specified unification for `pwzAssemblyIdentity1`.</span></span>  
  
 `pwzAssemblyIdentity2`  
 <span data-ttu-id="1a3b5-108">[in] 텍스트 비교에 사용 된 두 번째 어셈블리의 id입니다.</span><span class="sxs-lookup"><span data-stu-id="1a3b5-108">[in] The textual identity of the second assembly in the comparison.</span></span>  
  
 `fUnified2`  
 <span data-ttu-id="1a3b5-109">[in] 에 대 한 사용자 지정 통합을 나타내는 부울 플래그 `pwzAssemblyIdentity2`합니다.</span><span class="sxs-lookup"><span data-stu-id="1a3b5-109">[in] A Boolean flag that indicates user-specified unification for `pwzAssemblyIdentity2`.</span></span>  
  
 `pfEquivalent`  
 <span data-ttu-id="1a3b5-110">[out] 두 명의 어셈블리가 동일한 지 여부를 나타내는 부울 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="1a3b5-110">[out] A Boolean flag that indicates whether the two assemblies are equivalent.</span></span>  
  
 `pResult`  
 <span data-ttu-id="1a3b5-111">[out] [AssemblyComparisonResult](../../../../docs/framework/unmanaged-api/fusion/assemblycomparisonresult-enumeration.md) 비교에 대 한 자세한 정보를 포함 하는 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="1a3b5-111">[out] An [AssemblyComparisonResult](../../../../docs/framework/unmanaged-api/fusion/assemblycomparisonresult-enumeration.md) enumeration that contains detailed information about the comparison.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1a3b5-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="1a3b5-112">Return Value</span></span>  
 <span data-ttu-id="1a3b5-113">`pfEquivalent`두 명의 어셈블리가 동일한 지 여부를 나타내는 부울 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a3b5-113">`pfEquivalent` returns a Boolean value that indicates whether the two assemblies are equivalent.</span></span> <span data-ttu-id="1a3b5-114">`pResult`중 하나를 반환 된 `AssemblyComparisonResult` 값의 값에 대 한 보다 자세한 이유와 함께을 `pfEquivalent`합니다.</span><span class="sxs-lookup"><span data-stu-id="1a3b5-114">`pResult` returns one of the `AssemblyComparisonResult` values, to give a more detailed reason for the value of `pfEquivalent`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1a3b5-115">설명</span><span class="sxs-lookup"><span data-stu-id="1a3b5-115">Remarks</span></span>  
 <span data-ttu-id="1a3b5-116">`CompareAssemblyIdentity`확인 여부 `pwzAssemblyIdentity1` 및 `pwzAssemblyIdentity2` 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a3b5-116">`CompareAssemblyIdentity` checks whether `pwzAssemblyIdentity1` and `pwzAssemblyIdentity2` are equivalent.</span></span> <span data-ttu-id="1a3b5-117">`pfEquivalent`로 설정 되어 `true` 다음 조건 중 하나 이상:</span><span class="sxs-lookup"><span data-stu-id="1a3b5-117">`pfEquivalent` is set to `true` under one or more of the following conditions:</span></span>  
  
-   <span data-ttu-id="1a3b5-118">두 어셈블리 id는 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a3b5-118">The two assembly identities are equivalent.</span></span> <span data-ttu-id="1a3b5-119">강력한 이름의 어셈블리 어셈블리일 어셈블리 이름, 버전, 공개 키 토큰 및 culture 동일 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1a3b5-119">For strongly named assemblies, equivalency requires the assembly name, version, public key token, and culture to be identical.</span></span> <span data-ttu-id="1a3b5-120">간단한 이름의 어셈블리일 어셈블리 이름 및 문화권의 일치 내용이 해당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1a3b5-120">For simply named assemblies, equivalency requires a match on the assembly name and culture.</span></span>  
  
-   <span data-ttu-id="1a3b5-121">두 어셈블리 id는.NET Framework에서 실행 되는 어셈블리를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="1a3b5-121">Both assembly identities refer to assemblies that run on the .NET Framework.</span></span> <span data-ttu-id="1a3b5-122">이 반환 `true` 경우 어셈블리 버전 번호가 일치 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1a3b5-122">This condition returns `true` even if the assembly version numbers do not match.</span></span>  
  
-   <span data-ttu-id="1a3b5-123">두 어셈블리는 관리 되는 어셈블리 하지만 `fUnified1` 또는 `fUnified2` 로 설정 된 `true`합니다.</span><span class="sxs-lookup"><span data-stu-id="1a3b5-123">The two assemblies are not managed assemblies, but `fUnified1` or `fUnified2` was set to `true`.</span></span>  
  
 <span data-ttu-id="1a3b5-124">`fUnified` 플래그가 모든 버전 번호는 강력한 이름의 어셈블리의 버전 번호는 강력한 이름의 어셈블리에 해당 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1a3b5-124">The `fUnified` flag indicates that all version numbers up to the version number of the strongly named assembly are considered equivalent to the strongly named assembly.</span></span> <span data-ttu-id="1a3b5-125">예를 들어 경우의 값 `pwzAssemblyIndentity1` 은 "MyAssembly, 버전 3.0.0.0, culture = neutral, publicKeyToken = =...", 및의 값 `fUnified1` 은 `true`, 모든 버전의 버전 3.0.0.0를 0.0.0.0 MyAssembly 되어야 함을 나타냅니다 동등한 것으로 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a3b5-125">For example, if the value of `pwzAssemblyIndentity1` is "MyAssembly, version=3.0.0.0, culture=neutral, publicKeyToken=....", and the value of `fUnified1` is `true`, this indicates that all versions of MyAssembly from version 0.0.0.0 to 3.0.0.0 should be treated as equivalent.</span></span> <span data-ttu-id="1a3b5-126">이 경우 경우 `pwzAssemblyIndentity2` 동일한 어셈블리를 참조 `pwzAssemblyIndentity1`낮은 버전 번호를 가진 것 이라는 점을 제외 하면 `pfEquivalent` 로 설정 된 `true`합니다.</span><span class="sxs-lookup"><span data-stu-id="1a3b5-126">In such a case, if `pwzAssemblyIndentity2` refers to the same assembly as `pwzAssemblyIndentity1`, except that it has a lower version number, `pfEquivalent` is set to `true`.</span></span> <span data-ttu-id="1a3b5-127">경우 `pwzAssemblyIdentity2` 더 높은 버전 번호를 참조 `pfEquivalent` 로 설정 된 `true` 경우에만 값을 `fUnified2` 은 `true`합니다.</span><span class="sxs-lookup"><span data-stu-id="1a3b5-127">If `pwzAssemblyIdentity2` refers to a higher version number, `pfEquivalent` is set to `true` only if the value of `fUnified2` is `true`.</span></span>  
  
 <span data-ttu-id="1a3b5-128">`pResult` 매개 변수 같은 두 명의 어셈블리가으로 간주 하는 이유는 방법에 대 한 특정 정보를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a3b5-128">The `pResult` parameter includes specific information about why the two assemblies are considered equivalent or not equivalent.</span></span> <span data-ttu-id="1a3b5-129">자세한 내용은 참조 [AssemblyComparisonResult 열거형](../../../../docs/framework/unmanaged-api/fusion/assemblycomparisonresult-enumeration.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1a3b5-129">For more information, see [AssemblyComparisonResult Enumeration](../../../../docs/framework/unmanaged-api/fusion/assemblycomparisonresult-enumeration.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1a3b5-130">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1a3b5-130">Requirements</span></span>  
 <span data-ttu-id="1a3b5-131">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1a3b5-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1a3b5-132">**헤더:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="1a3b5-132">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="1a3b5-133">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="1a3b5-133">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1a3b5-134">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1a3b5-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a3b5-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1a3b5-135">See Also</span></span>  
 [<span data-ttu-id="1a3b5-136">Fusion 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="1a3b5-136">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)  
 [<span data-ttu-id="1a3b5-137">AssemblyComparisonResult 열거형</span><span class="sxs-lookup"><span data-stu-id="1a3b5-137">AssemblyComparisonResult Enumeration</span></span>](../../../../docs/framework/unmanaged-api/fusion/assemblycomparisonresult-enumeration.md)
