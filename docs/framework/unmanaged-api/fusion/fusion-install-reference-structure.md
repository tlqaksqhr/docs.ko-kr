---
title: "FUSION_INSTALL_REFERENCE 구조체"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: FUSION_INSTALL_REFERENCE
api_location: fusion.dll
api_type: COM
f1_keywords: FUSION_INSTALL_REFERENCE
helpviewer_keywords: FUSION_INSTALL_REFERENCE structure [.NET Framework fusion]
ms.assetid: ae181ec8-36bf-4ed1-9a02-ca27d417c80b
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 36321606fe208233fb6114fe9568b655f0e1b400
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="fusioninstallreference-structure"></a><span data-ttu-id="53a47-102">FUSION_INSTALL_REFERENCE 구조체</span><span class="sxs-lookup"><span data-stu-id="53a47-102">FUSION_INSTALL_REFERENCE Structure</span></span>
<span data-ttu-id="53a47-103">응용 프로그램은 전역 어셈블리 캐시에는 응용 프로그램이 설치 된 어셈블리 참조를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="53a47-103">Represents a reference that an application makes to an assembly that the application has installed in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53a47-104">구문</span><span class="sxs-lookup"><span data-stu-id="53a47-104">Syntax</span></span>  
  
```  
typedef struct _FUSION_INSTALL_REFERENCE_ {  
    DWORD    cbSize,  
    DWORD    dwFlags,  
    GUID     guidScheme,  
    LPCWSTR  szIdentifier,  
    LPCWSTR  szNonCanonicalData  
} FUSION_INSTALL_REFERENCE, *LPFUSION_INSTALL_REFERENCE;  
```  
  
## <a name="members"></a><span data-ttu-id="53a47-105">멤버</span><span class="sxs-lookup"><span data-stu-id="53a47-105">Members</span></span>  
  
|<span data-ttu-id="53a47-106">멤버</span><span class="sxs-lookup"><span data-stu-id="53a47-106">Member</span></span>|<span data-ttu-id="53a47-107">설명</span><span class="sxs-lookup"><span data-stu-id="53a47-107">Description</span></span>|  
|------------|-----------------|  
|`cbSize`|<span data-ttu-id="53a47-108">크기 (바이트)에서 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="53a47-108">The size of the structure in bytes.</span></span>|  
|`dwFlags`|<span data-ttu-id="53a47-109">다음 버전의 확장에 대 한 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53a47-109">Reserved for future extensibility.</span></span> <span data-ttu-id="53a47-110">이 값은 0 (영) 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="53a47-110">This value must be 0 (zero).</span></span>|  
|`guidScheme`|<span data-ttu-id="53a47-111">참조를 추가 하는 엔터티.</span><span class="sxs-lookup"><span data-stu-id="53a47-111">The entity that adds the reference.</span></span> <span data-ttu-id="53a47-112">이 필드는 다음 값 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53a47-112">This field can have one of the following values:</span></span><br /><br /> <span data-ttu-id="53a47-113">-FUSION_REFCOUNT_MSI_GUID: Microsoft Windows Installer를 사용 하 여 설치 된 응용 프로그램에서 어셈블리 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="53a47-113">-   FUSION_REFCOUNT_MSI_GUID: The assembly is referenced by an application that was installed using the Microsoft Windows Installer.</span></span> <span data-ttu-id="53a47-114">`szIdentifier` 필드가로 설정 된 `MSI`, 및 `szNonCanonicalData` 필드가로 설정 된 `Windows Installer`합니다.</span><span class="sxs-lookup"><span data-stu-id="53a47-114">The `szIdentifier` field is set to `MSI`, and the `szNonCanonicalData` field is set to `Windows Installer`.</span></span> <span data-ttu-id="53a47-115">이 스키마는 Windows-side-by-side 어셈블리에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="53a47-115">This scheme is used for Windows side-by-side assemblies.</span></span><br /><span data-ttu-id="53a47-116">-FUSION_REFCOUNT_UNINSTALL_SUBKEY_GUID: 어셈블리에 표시 되는 응용 프로그램에서 참조 되는 **프로그램 추가/제거** 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="53a47-116">-   FUSION_REFCOUNT_UNINSTALL_SUBKEY_GUID: The assembly is referenced by an application that appears in the **Add/Remove Programs** interface.</span></span> <span data-ttu-id="53a47-117">`szIdentifier` 필드에서 응용 프로그램을 등록 하는 토큰이 제공 된 **프로그램 추가/제거** 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="53a47-117">The `szIdentifier` field provides the token that registers the application with the **Add/Remove Programs** interface.</span></span><br /><span data-ttu-id="53a47-118">-FUSION_REFCOUNT_FILEPATH_GUID: 파일 시스템에는 파일에 의해 표시 되는 응용 프로그램에서 어셈블리 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="53a47-118">-   FUSION_REFCOUNT_FILEPATH_GUID: The assembly is referenced by an application that is represented by a file in the file system.</span></span> <span data-ttu-id="53a47-119">`szIdentifier` 필드에이 파일의 경로를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="53a47-119">The `szIdentifier` field provides the path to this file.</span></span><br /><span data-ttu-id="53a47-120">-FUSION_REFCOUNT_OPAQUE_STRING_GUID:는 불투명 문자열에 의해서만 표현 하는 응용 프로그램에서 어셈블리 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="53a47-120">-   FUSION_REFCOUNT_OPAQUE_STRING_GUID: The assembly is referenced by an application that is represented only by an opaque string.</span></span> <span data-ttu-id="53a47-121">`szIdentifier` 필드가 불투명 문자열이 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="53a47-121">The `szIdentifier` field provides this opaque string.</span></span> <span data-ttu-id="53a47-122">이 값을 제거 하는 경우 전역 어셈블리 캐시 불투명 참조가 있는지 여부를 확인 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="53a47-122">The global assembly cache does not check for the existence of opaque references when you remove this value.</span></span><br /><span data-ttu-id="53a47-123">-FUSION_REFCOUNT_OSINSTALL_GUID:이 값은 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53a47-123">-   FUSION_REFCOUNT_OSINSTALL_GUID: This value is reserved.</span></span>|  
|`szIdentifier`|<span data-ttu-id="53a47-124">전역 어셈블리 캐시에 어셈블리를 설치 하는 응용 프로그램을 식별 하는 고유 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="53a47-124">A unique string that identifies the application that installed the assembly in the global assembly cache.</span></span> <span data-ttu-id="53a47-125">해당 값의 값에 따라 달라는 `guidScheme` 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="53a47-125">Its value depends upon the value of the `guidScheme` field.</span></span>|  
|`szNonCanonicalData`|<span data-ttu-id="53a47-126">엔터티 참조를 추가 하 여만 인식 하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="53a47-126">A string that is understood only by the entity that adds the reference.</span></span> <span data-ttu-id="53a47-127">전역 어셈블리 캐시에서는이 문자열을 저장 하지만 사용 하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="53a47-127">The global assembly cache stores this string, but does not use it.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="53a47-128">요구 사항</span><span class="sxs-lookup"><span data-stu-id="53a47-128">Requirements</span></span>  
 <span data-ttu-id="53a47-129">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="53a47-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="53a47-130">**헤더:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="53a47-130">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="53a47-131">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="53a47-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53a47-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="53a47-132">See Also</span></span>  
 [<span data-ttu-id="53a47-133">Fusion 구조체</span><span class="sxs-lookup"><span data-stu-id="53a47-133">Fusion Structures</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-structures.md)  
 [<span data-ttu-id="53a47-134">전역 어셈블리 캐시</span><span class="sxs-lookup"><span data-stu-id="53a47-134">Global Assembly Cache</span></span>](../../../../docs/framework/app-domains/gac.md)
