---
title: "ICorDebugType::GetClass 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugType.GetClass
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugType::GetClass
helpviewer_keywords:
- ICorDebugType::GetClass method [.NET Framework debugging]
- GetClass method, ICorDebugType interface [.NET Framework debugging]
ms.assetid: 2644f48b-db3c-429f-ae62-76f1c98a1af5
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: be9999cd0dd8db5439dd41e51429841666597b16
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugtypegetclass-method"></a><span data-ttu-id="99b02-102">ICorDebugType::GetClass 메서드</span><span class="sxs-lookup"><span data-stu-id="99b02-102">ICorDebugType::GetClass Method</span></span>
<span data-ttu-id="99b02-103">인스턴스화되지 않은 제네릭 형식을 나타내는 ICorDebugClass에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="99b02-103">Gets an interface pointer to an ICorDebugClass that represents the uninstantiated generic type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99b02-104">구문</span><span class="sxs-lookup"><span data-stu-id="99b02-104">Syntax</span></span>  
  
```  
HRESULT GetClass (  
    [out] ICorDebugClass   **ppClass  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="99b02-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="99b02-105">Parameters</span></span>  
 `ppClass`  
 <span data-ttu-id="99b02-106">[out] 주소에 대 한 포인터는 `ICorDebugClass` 인스턴스화되지 않은 제네릭 형식을 나타내는 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="99b02-106">[out] A pointer to the address of an `ICorDebugClass` interface that represents the uninstantiated generic type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="99b02-107">설명</span><span class="sxs-lookup"><span data-stu-id="99b02-107">Remarks</span></span>  
 <span data-ttu-id="99b02-108">`GetClass`특정 조건 에서만 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99b02-108">`GetClass` can be called only under certain conditions.</span></span> <span data-ttu-id="99b02-109">호출 [icordebugtype:: Gettype](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) 호출 하기 전에 `GetClass`합니다.</span><span class="sxs-lookup"><span data-stu-id="99b02-109">Call [ICorDebugType::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) before calling `GetClass`.</span></span> <span data-ttu-id="99b02-110">경우 `ICorDebugType::GetType` ELEMENT_TYPE_CLASS 또는 ELEMENT_TYPE_VALUETYPE, CorElementType 값을 반환 `GetClass` 인스턴스화되지 않은 형식을 제네릭 형식에 대 한 가져오기 위해 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99b02-110">If `ICorDebugType::GetType` returns a CorElementType value that is ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE, `GetClass` can be called to get the uninstantiated type for a generic type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99b02-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="99b02-111">Requirements</span></span>  
 <span data-ttu-id="99b02-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="99b02-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99b02-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="99b02-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="99b02-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="99b02-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="99b02-115">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="99b02-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
