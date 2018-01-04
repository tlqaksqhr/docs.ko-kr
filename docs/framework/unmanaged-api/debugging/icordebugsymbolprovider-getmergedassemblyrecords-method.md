---
title: "ICorDebugSymbolProvider::GetMergedAssemblyRecords 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: cc4c510d-550d-4941-af34-81987caf3425
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 75c8a98b4e7b2e3250adfb75a5d2dcb29a71ff27
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugsymbolprovidergetmergedassemblyrecords-method"></a><span data-ttu-id="f54a7-102">ICorDebugSymbolProvider::GetMergedAssemblyRecords 메서드</span><span class="sxs-lookup"><span data-stu-id="f54a7-102">ICorDebugSymbolProvider::GetMergedAssemblyRecords Method</span></span>
<span data-ttu-id="f54a7-103">모든 병합된 어셈블리에 대한 기호 레코드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f54a7-103">Gets the symbol records for all the merged assemblies.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f54a7-104">구문</span><span class="sxs-lookup"><span data-stu-id="f54a7-104">Syntax</span></span>  
  
```  
HRESULT GetMergedAssemblyRecords(  
   [in] ULONG32 cRequestedRecords,  
   [out] ULONG32 *pcFetchedRecords,  
   [out, size_is(cRequestedRecords), length_is(*pcFetchedRecords)] ICorDebugMergedAssemblyRecord *pRecords[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f54a7-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f54a7-105">Parameters</span></span>  
 `cRequestedRecords`  
 <span data-ttu-id="f54a7-106">[in] 요청되는 기호 레코드 수입니다.</span><span class="sxs-lookup"><span data-stu-id="f54a7-106">[in] The number of symbol records requested.</span></span>  
  
 `pcFetchedRecords`  
 <span data-ttu-id="f54a7-107">[out] 메서드에 의해 검색되는 기호 레코드 수에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f54a7-107">[out] A pointer to the number of symbol records retrieved by the method.</span></span>  
  
 `pRecords`  
 <span data-ttu-id="f54a7-108">배열에 대 한 포인터 [ICorDebugMergedAssemblyRecord](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md) 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="f54a7-108">A pointer to an array of [ICorDebugMergedAssemblyRecord](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md) objects.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f54a7-109">설명</span><span class="sxs-lookup"><span data-stu-id="f54a7-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f54a7-110">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f54a7-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f54a7-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f54a7-111">Requirements</span></span>  
 <span data-ttu-id="f54a7-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f54a7-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f54a7-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f54a7-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f54a7-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f54a7-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f54a7-115">**.NET framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f54a7-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f54a7-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f54a7-116">See Also</span></span>  
 [<span data-ttu-id="f54a7-117">ICorDebugSymbolProvider 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f54a7-117">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)  
 [<span data-ttu-id="f54a7-118">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f54a7-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
