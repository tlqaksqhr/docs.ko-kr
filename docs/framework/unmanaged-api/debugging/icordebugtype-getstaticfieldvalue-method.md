---
title: "ICorDebugType::GetStaticFieldValue 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugType.GetStaticFieldValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugType::GetStaticFieldValue
helpviewer_keywords:
- GetStaticFieldValue method, ICorDebugType interface [.NET Framework debugging]
- ICorDebugType::GetStaticFieldValue method [.NET Framework debugging]
ms.assetid: 62eb5d55-53ee-4fb3-8d47-7b6c96808f9e
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 34a37ef9a28dd0e6325db9bee61146f14d4638a6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugtypegetstaticfieldvalue-method"></a><span data-ttu-id="3b38d-102">ICorDebugType::GetStaticFieldValue 메서드</span><span class="sxs-lookup"><span data-stu-id="3b38d-102">ICorDebugType::GetStaticFieldValue Method</span></span>
<span data-ttu-id="3b38d-103">토큰을 지정 된 스택 프레임에 지정 된 필드에서 참조 하는 정적 필드의 값을 포함 하는 ICorDebugValue 개체에 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3b38d-103">Gets an interface pointer to an ICorDebugValue object that contains the value of the static field referenced by the specified field token in the specified stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b38d-104">구문</span><span class="sxs-lookup"><span data-stu-id="3b38d-104">Syntax</span></span>  
  
```  
HRESULT GetStaticFieldValue (  
    [in]  mdFieldDef        fieldDef,  
    [in]  ICorDebugFrame    *pFrame,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3b38d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3b38d-105">Parameters</span></span>  
 `fieldDef`  
 <span data-ttu-id="3b38d-106">[in] `mdFieldDef` 정적 필드를 지정 하는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="3b38d-106">[in] An `mdFieldDef` token that specifies the static field.</span></span>  
  
 `pFrame`  
 <span data-ttu-id="3b38d-107">[in] 스택 프레임을 나타내는 ICorDebugFrame에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="3b38d-107">[in] A pointer to an ICorDebugFrame that represents the stack frame.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="3b38d-108">[out] 주소에 대 한 포인터는 `ICorDebugValue` 정적 필드의 값이 들어 있는입니다.</span><span class="sxs-lookup"><span data-stu-id="3b38d-108">[out] A pointer to the address of an `ICorDebugValue` that contains the value of the static field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3b38d-109">설명</span><span class="sxs-lookup"><span data-stu-id="3b38d-109">Remarks</span></span>  
 <span data-ttu-id="3b38d-110">`GetStaticFieldValue` 메서드 있습니다 사용할 형식이 ELEMENT_TYPE_CLASS 또는 ELEMENT_TYPE_VALUETYPE, 경우에에 표시 된 대로 [icordebugtype:: Gettype](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="3b38d-110">The `GetStaticFieldValue` method may be used only if the type is ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE, as indicated by the [ICorDebugType::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) method.</span></span>  
  
 <span data-ttu-id="3b38d-111">제네릭이 아닌 형식에 대 한 작업을 수행 하 여 `GetStaticFieldValue` 호출 동일 [icordebugclass:: Getstaticfieldvalue](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-getstaticfieldvalue-method.md) ICorDebugClass 개체에서 반환 되는에 [icordebugtype:: Getclass](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md).</span><span class="sxs-lookup"><span data-stu-id="3b38d-111">For non-generic types, the operation performed by `GetStaticFieldValue` is identical to calling [ICorDebugClass::GetStaticFieldValue](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-getstaticfieldvalue-method.md) on the ICorDebugClass object that is returned by [ICorDebugType::GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md).</span></span>  
  
 <span data-ttu-id="3b38d-112">제네릭 형식의 정적 필드 값을 특정 인스턴스화와 관련 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b38d-112">For generic types, a static field value will be relative to a particular instantiation.</span></span> <span data-ttu-id="3b38d-113">또한 정적 필드 스레드, 컨텍스트, 또는 응용 프로그램 도메인을 기준으로 될 수, 다음 스택 프레임 할 경우 디버거에서 적절 한 값을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b38d-113">Also, if the static field could possibly be relative to a thread, a context, or an application domain, then the stack frame will help the debugger determine the proper value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3b38d-114">설명</span><span class="sxs-lookup"><span data-stu-id="3b38d-114">Remarks</span></span>  
 <span data-ttu-id="3b38d-115">`GetStaticFieldValue`호출할 때에 사용할 수 `ICorDebugType::GetType` ELEMENT_TYPE_CLASS 또는 ELEMENT_TYPE_VALUETYPE 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b38d-115">`GetStaticFieldValue` can be used only when a call to `ICorDebugType::GetType` returns a value of ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3b38d-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3b38d-116">Requirements</span></span>  
 <span data-ttu-id="3b38d-117">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3b38d-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3b38d-118">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3b38d-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3b38d-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3b38d-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3b38d-120">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3b38d-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
