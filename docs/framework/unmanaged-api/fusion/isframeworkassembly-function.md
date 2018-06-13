---
title: IsFrameworkAssembly 함수
ms.date: 03/30/2017
api_name:
- IsFrameworkAssembly
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IsFrameworkAssembly
helpviewer_keywords:
- IsFrameworkAssembly function [.NET Framework fusion]
ms.assetid: b0c6f19b-d4fd-4971-88f0-12ffb5793da3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c3fd130759ab11b54b597d5c099c33dab93070ae
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33429252"
---
# <a name="isframeworkassembly-function"></a><span data-ttu-id="5fe69-102">IsFrameworkAssembly 함수</span><span class="sxs-lookup"><span data-stu-id="5fe69-102">IsFrameworkAssembly Function</span></span>
<span data-ttu-id="5fe69-103">지정된 된 어셈블리 관리 되는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5fe69-103">Gets a value that indicates whether the specified assembly is managed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5fe69-104">구문</span><span class="sxs-lookup"><span data-stu-id="5fe69-104">Syntax</span></span>  
  
```  
HRESULT IsFrameworkAssembly (  
    [in]  LPCWSTR pwzAssemblyReference,  
    [out] LPBOOL  pbIsFrameworkAssembly,  
    [in]  LPWSTR  pwzFrameworkAssemblyIdentity,  
    [in]  LPDWORD pccSize  
 );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5fe69-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5fe69-105">Parameters</span></span>  
 `pwzAssemblyReference`  
 <span data-ttu-id="5fe69-106">[in] 확인할 어셈블리의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="5fe69-106">[in] The name of the assembly to check.</span></span>  
  
 `pbIsFrameworkAssembly`  
 <span data-ttu-id="5fe69-107">[out] 어셈블리 관리 되는지 여부를 나타내는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="5fe69-107">[out] A Boolean value that indicates whether the assembly is managed.</span></span>  
  
 `pwzFrameworkAssemblyIdentity`  
 <span data-ttu-id="5fe69-108">[in] 어셈블리의 고유 id를 포함 하는 uncanonicalized 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="5fe69-108">[in] An uncanonicalized string that contains the unique identity of the assembly.</span></span>  
  
 `pccSize`  
 <span data-ttu-id="5fe69-109">[in] `pwzFrameworkAssemblyIdentity`의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="5fe69-109">[in] The size of `pwzFrameworkAssemblyIdentity`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5fe69-110">설명</span><span class="sxs-lookup"><span data-stu-id="5fe69-110">Remarks</span></span>  
 <span data-ttu-id="5fe69-111">`pwzAssemblyReference` 매개 변수는 어셈블리의 이름이 포함 된 문자열에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="5fe69-111">The `pwzAssemblyReference` parameter is a pointer to a character string that contains the name of an assembly.</span></span>  
  
 <span data-ttu-id="5fe69-112">이 어셈블리는.NET Framework의 일부인 경우는 `pbIsFrameworkAssembly` 매개 변수는 부울 값을 포함 됩니다 `true`합니다.</span><span class="sxs-lookup"><span data-stu-id="5fe69-112">If this assembly is part of the .NET Framework, the `pbIsFrameworkAssembly` parameter will contain a Boolean value of `true`.</span></span>  
  
 <span data-ttu-id="5fe69-113">명명된 된 어셈블리는.NET Framework의 일부가 아닌 경우 또는 경우는 `pwzAssemblyReference` 매개 변수는 어셈블리 이름을 지정 하지 않습니다 `pbIsFrameworkAssembly` 의 부울 값이 포함 됩니다 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="5fe69-113">If the named assembly is not part of the .NET Framework, or if the `pwzAssemblyReference` parameter does not name an assembly, `pbIsFrameworkAssembly` will contain a Boolean value of `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5fe69-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5fe69-114">Requirements</span></span>  
 <span data-ttu-id="5fe69-115">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5fe69-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5fe69-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5fe69-116">See Also</span></span>  
 [<span data-ttu-id="5fe69-117">Fusion 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="5fe69-117">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
