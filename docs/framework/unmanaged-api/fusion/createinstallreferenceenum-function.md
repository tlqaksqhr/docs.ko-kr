---
title: "CreateInstallReferenceEnum 함수"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CreateInstallReferenceEnum
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type: DLLExport
f1_keywords: CreateInstallReference
helpviewer_keywords: CreateInstallReference function [.NET Framework fusion]
ms.assetid: 80dbbbf8-54fc-4894-b74a-0179d3201083
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a0c902cf5d9d8b6295cab95552aae6775c5bf889
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="createinstallreferenceenum-function"></a><span data-ttu-id="7ca84-102">CreateInstallReferenceEnum 함수</span><span class="sxs-lookup"><span data-stu-id="7ca84-102">CreateInstallReferenceEnum Function</span></span>
<span data-ttu-id="7ca84-103">에 대 한 포인터를 가져옵니다는 [IInstallReferenceEnum](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md) 목록이 지정된 된 어셈블리에 대 한 응용 프로그램의 한 참조를 나타내는 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="7ca84-103">Gets a pointer to an [IInstallReferenceEnum](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md) instance that represents a list of an application's references to the specified assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ca84-104">구문</span><span class="sxs-lookup"><span data-stu-id="7ca84-104">Syntax</span></span>  
  
```  
HRESULT CreateInstallReferenceEnum (  
    [out] IInstallReferenceEnum **ppRefEnum,  
    [in]  IAssemblyName         *pName,  
    [in]  DWORD                 dwFlags,  
    [in]  LPVOID                pvReserved  
 );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7ca84-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7ca84-105">Parameters</span></span>  
 `ppRefEnum`  
 <span data-ttu-id="7ca84-106">[out] 반환 된 `IInstallReferenceEnum` 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="7ca84-106">[out] The returned `IInstallReferenceEnum` pointer.</span></span>  
  
 `pName`  
 <span data-ttu-id="7ca84-107">[in] [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) 참조를 열거 하는 어셈블리를 식별 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ca84-107">[in] The [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) that identifies the assembly for which to enumerate references.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="7ca84-108">[in] 열거자의 동작에 영향을 주는 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="7ca84-108">[in] Flags that influence the enumerator's behavior.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="7ca84-109">[in] 다음 버전의 확장에 대 한 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ca84-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="7ca84-110">`pvReserved`null 참조 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ca84-110">`pvReserved` must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ca84-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7ca84-111">Requirements</span></span>  
 <span data-ttu-id="7ca84-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7ca84-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ca84-113">**헤더:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="7ca84-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="7ca84-114">**라이브러리:** Fusion.dll 및 Mscorwks.dll 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ca84-114">**Library:** Fusion.dll and Mscorwks.dll.</span></span> <span data-ttu-id="7ca84-115">올바른 버전의.NET Framework를 대상 하는 데 Mscorwks.dll 대신 Fusion.dll를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ca84-115">Use Fusion.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="7ca84-116">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ca84-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ca84-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7ca84-117">See Also</span></span>  
 [<span data-ttu-id="7ca84-118">IInstallReferenceEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7ca84-118">IInstallReferenceEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md)  
 [<span data-ttu-id="7ca84-119">IAssemblyName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7ca84-119">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)  
 [<span data-ttu-id="7ca84-120">Fusion 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="7ca84-120">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
