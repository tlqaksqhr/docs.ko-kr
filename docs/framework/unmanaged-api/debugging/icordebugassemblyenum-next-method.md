---
title: ICorDebugAssemblyEnum::Next 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugAssemblyEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssemblyEnum::Next method
helpviewer_keywords:
- ICorDebugAssemblyEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugAssemblyEnum interface [.NET Framework debugging]
ms.assetid: b3e7d0c2-3baa-4ef8-8e3f-b865cf252940
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b94ae83f2fb5f71abb8cb3a5c96aac9e268fc5db
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33405290"
---
# <a name="icordebugassemblyenumnext-method"></a><span data-ttu-id="257bf-102">ICorDebugAssemblyEnum::Next 메서드</span><span class="sxs-lookup"><span data-stu-id="257bf-102">ICorDebugAssemblyEnum::Next Method</span></span>
<span data-ttu-id="257bf-103">현재 커서 위치부터 시작 하 고 컬렉션에서 지정 된 어셈블리 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="257bf-103">Gets the specified number of assemblies from the collection, starting at the current cursor position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="257bf-104">구문</span><span class="sxs-lookup"><span data-stu-id="257bf-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugAssembly *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="257bf-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="257bf-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="257bf-106">[in] 어셈블리를 검색할 수입니다.</span><span class="sxs-lookup"><span data-stu-id="257bf-106">[in] The number of assemblies to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="257bf-107">[out] 어셈블리를 나타내는 ICorDebugAssembly 개체를 가리키는 각각 포인터의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="257bf-107">[out] An array of pointers, each of which points to an ICorDebugAssembly object that represents an assembly.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="257bf-108">[out] 실제로 반환 된 어셈블리의 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="257bf-108">[out] A pointer to the number of assemblies actually returned.</span></span> <span data-ttu-id="257bf-109">이 값은 null 일 수 있으면 `celt` 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="257bf-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="257bf-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="257bf-110">Requirements</span></span>  
 <span data-ttu-id="257bf-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="257bf-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="257bf-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="257bf-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="257bf-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="257bf-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="257bf-114">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="257bf-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
