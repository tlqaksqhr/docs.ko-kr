---
title: "CreateAssemblyNameObject 함수"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CreateAssemblyNameObject
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type: DLLExport
f1_keywords: CreateAssemblyNameObject
helpviewer_keywords: CreateAssemblyNameObject function [.NET Framework fusion]
ms.assetid: 55c8b41e-fbe4-4ae0-aa29-68fbb2311691
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 8281c7944ff96110145a6f5c43a0a0e7da58fdcf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="createassemblynameobject-function"></a><span data-ttu-id="cdff0-102">CreateAssemblyNameObject 함수</span><span class="sxs-lookup"><span data-stu-id="cdff0-102">CreateAssemblyNameObject Function</span></span>
<span data-ttu-id="cdff0-103">한 인터페이스 포인터를 가져옵니다는 [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) 지정한 이름 가진 어셈블리의 고유 id를 나타내는 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="cdff0-103">Gets an interface pointer to an [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) instance that represents the unique identity of the assembly with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cdff0-104">구문</span><span class="sxs-lookup"><span data-stu-id="cdff0-104">Syntax</span></span>  
  
```  
HRESULT CreateAssemblyNameObject (  
    [out] LPASSEMBLYNAME  *ppAssemblyNameObj,  
    [in]  LPCWSTR         szAssemblyName,  
    [in]  DWORD           dwFlags,  
    [in]  LPVOID          pvReserved  
 );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cdff0-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cdff0-105">Parameters</span></span>  
 `ppAssemblyNameObj`  
 <span data-ttu-id="cdff0-106">[out] 반환 된 `IAssemblyName`합니다.</span><span class="sxs-lookup"><span data-stu-id="cdff0-106">[out] The returned `IAssemblyName`.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="cdff0-107">[in] 만들 새 어셈블리의 이름을 `IAssemblyName` 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="cdff0-107">[in] The name of the assembly for which to create the new `IAssemblyName` instance.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="cdff0-108">[in] 개체 생성자에 전달 하는 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="cdff0-108">[in] Flags to pass to the object constructor.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="cdff0-109">[in] 다음 버전의 확장에 대 한 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cdff0-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="cdff0-110">`pvReserved`null 참조 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cdff0-110">`pvReserved` must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cdff0-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cdff0-111">Requirements</span></span>  
 <span data-ttu-id="cdff0-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="cdff0-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cdff0-113">**헤더:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="cdff0-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="cdff0-114">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="cdff0-114">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="cdff0-115">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cdff0-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cdff0-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cdff0-116">See Also</span></span>  
 [<span data-ttu-id="cdff0-117">IAssemblyName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cdff0-117">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)  
 [<span data-ttu-id="cdff0-118">Fusion 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="cdff0-118">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
