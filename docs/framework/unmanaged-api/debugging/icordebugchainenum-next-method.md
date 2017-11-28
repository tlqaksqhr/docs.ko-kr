---
title: "ICorDebugChainEnum::Next 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugChainEnum.Next
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugChainEnum::Next
helpviewer_keywords:
- ICorDebugChainEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugChainEnum interface [.NET Framework debugging]
ms.assetid: 6b791351-bcc5-4ddd-9cab-eff2f7dd5142
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3d6d587b1a249d08ffb250453fb9c007dc3df3e2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugchainenumnext-method"></a><span data-ttu-id="5a868-102">ICorDebugChainEnum::Next 메서드</span><span class="sxs-lookup"><span data-stu-id="5a868-102">ICorDebugChainEnum::Next Method</span></span>
<span data-ttu-id="5a868-103">현재 위치부터 시작 하는 열거형에서 지정 된 ICorDebugChain 인스턴스 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5a868-103">Gets the specified number of ICorDebugChain instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a868-104">구문</span><span class="sxs-lookup"><span data-stu-id="5a868-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugChain *chains[],  
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5a868-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5a868-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="5a868-106">[in] 수가 `ICorDebugChain` 인스턴스를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a868-106">[in] The number of `ICorDebugChain` instances to be retrieved.</span></span>  
  
 `chains`  
 <span data-ttu-id="5a868-107">[out] 각각 가리키는 포인터의 배열은 `ICorDebugChain` 체인을 나타내는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="5a868-107">[out] An array of pointers, each of which points to an `ICorDebugChain` object that represents a chain.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="5a868-108">[out] 수에 대 한 포인터 `ICorDebugChain` 실제로 반환 된 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="5a868-108">[out] A pointer to the number of `ICorDebugChain` instances actually returned.</span></span> <span data-ttu-id="5a868-109">이 값은 null 일 수 있으면 `celt` 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="5a868-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5a868-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5a868-110">Requirements</span></span>  
 <span data-ttu-id="5a868-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5a868-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a868-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5a868-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5a868-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5a868-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5a868-114">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a868-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
