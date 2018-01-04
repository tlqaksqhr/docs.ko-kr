---
title: "ICorDebugProcess5::EnumerateGCReferences 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess5.EnumerateGCReferences
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess5::EnumerateGCReferences
helpviewer_keywords:
- EnumerateGCReferences method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::EnumerateGCReferences method [.NET Framework debugging]
ms.assetid: 86c397c3-81d8-463e-a248-3cbe06c44d9d
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 44975a7896c71ce8061dedde13d31c4fbb88d6a1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocess5enumerategcreferences-method"></a><span data-ttu-id="56381-102">ICorDebugProcess5::EnumerateGCReferences 메서드</span><span class="sxs-lookup"><span data-stu-id="56381-102">ICorDebugProcess5::EnumerateGCReferences Method</span></span>
<span data-ttu-id="56381-103">프로세스의 가비지 수집 하는 모든 개체에 대 한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="56381-103">Gets an enumerator for all objects that are to be garbage-collected in a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56381-104">구문</span><span class="sxs-lookup"><span data-stu-id="56381-104">Syntax</span></span>  
  
```  
HRESULT EnumerateGCReferences(  
    [in] Bool enumerateWeakReferences,   
    [out] ICorDebugGCReferenceEnum **ppEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="56381-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="56381-105">Parameters</span></span>  
 `enumerateWeakReferences`  
 <span data-ttu-id="56381-106">[in] 약한 참조를 열거도 지 여부를 나타내는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="56381-106">[in] A Boolean value that indicates whether weak references are also to be enumerated.</span></span> <span data-ttu-id="56381-107">경우 `enumerateWeakReferences` 은 `true`, `ppEnum` 열거자는 강력한 참조 및 약한 참조를 모두 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="56381-107">If `enumerateWeakReferences` is `true`, the `ppEnum` enumerator includes both strong references and weak references.</span></span> <span data-ttu-id="56381-108">경우 `enumerateWeakReferences` 은 `false`, 열거자는 강력한 참조만 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="56381-108">If `enumerateWeakReferences` is `false`, the enumerator includes only strong references.</span></span>  
  
 `ppEnum`  
 <span data-ttu-id="56381-109">[out] 주소에 대 한 포인터는 [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) 즉 하는 열거자 개체에 대 한 가비지 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="56381-109">[out] A pointer to the address of an [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) that is an enumerator for the objects to be garbage-collected.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="56381-110">설명</span><span class="sxs-lookup"><span data-stu-id="56381-110">Remarks</span></span>  
 <span data-ttu-id="56381-111">이 메서드는 프로세스에서 관리 되는 개체에 대 한 전체 루 팅 체인을 결정 하는 방법을 제공 하며 개체가 아직 활성화 된 이유를 확인 하기 위해 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56381-111">This method provides a way to determine the full rooting chain for any managed object in a process and can be used to determine why an object is still alive.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="56381-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="56381-112">Requirements</span></span>  
 <span data-ttu-id="56381-113">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="56381-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="56381-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="56381-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="56381-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="56381-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="56381-116">**.NET framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="56381-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56381-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="56381-117">See Also</span></span>  
 [<span data-ttu-id="56381-118">ICorDebugProcess5 인터페이스</span><span class="sxs-lookup"><span data-stu-id="56381-118">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)  
 [<span data-ttu-id="56381-119">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="56381-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
