---
title: ICorDebugEval::CreateValue 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugEval.CreateValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::CreateValue
helpviewer_keywords:
- ICorDebugEval::CreateValue method [.NET Framework debugging]
- CreateValue method [.NET Framework debugging]
ms.assetid: 9a1c0b47-6f10-4fcb-844a-4ab2d7990140
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6d67784daee055106f104d74d098b9926c6de2ec
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33417114"
---
# <a name="icordebugevalcreatevalue-method"></a><span data-ttu-id="dcc5f-102">ICorDebugEval::CreateValue 메서드</span><span class="sxs-lookup"><span data-stu-id="dcc5f-102">ICorDebugEval::CreateValue Method</span></span>
<span data-ttu-id="dcc5f-103">초기 값이 0 또는 null 인 지정 된 형식의 값을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="dcc5f-103">Creates a value of the specified type, with an initial value of zero or null.</span></span>  
  
 <span data-ttu-id="dcc5f-104">이 메서드는.NET Framework 버전 2.0에서에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dcc5f-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="dcc5f-105">사용 하 여 [icordebugeval2:: Createvaluefortype](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-createvaluefortype-method.md) 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcc5f-105">Use [ICorDebugEval2::CreateValueForType](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-createvaluefortype-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dcc5f-106">구문</span><span class="sxs-lookup"><span data-stu-id="dcc5f-106">Syntax</span></span>  
  
```  
HRESULT CreateValue (  
    [in] CorElementType     elementType,  
    [in] ICorDebugClass     *pElementClass,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="dcc5f-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="dcc5f-107">Parameters</span></span>  
 `elementType`  
 <span data-ttu-id="dcc5f-108">[in] 값은 [CorElementType](../../../../docs/framework/unmanaged-api/metadata/corelementtype-enumeration.md) 값의 형식을 지정 하는 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="dcc5f-108">[in] A value of the [CorElementType](../../../../docs/framework/unmanaged-api/metadata/corelementtype-enumeration.md) enumeration that specifies the type of the value.</span></span>  
  
 `pElementClass`  
 <span data-ttu-id="dcc5f-109">[in] 에 대 한 포인터는 [ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md) 는 형식이 기본 형식이 아닌 경우 값의 클래스를 지정 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="dcc5f-109">[in] Pointer to an [ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md) object that specifies the class of the value, if the type is not a primitive type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="dcc5f-110">[out] 값을 나타내는 "ICorDebugValue" 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="dcc5f-110">[out] Pointer to the address of an "ICorDebugValue" object that represents the value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dcc5f-111">설명</span><span class="sxs-lookup"><span data-stu-id="dcc5f-111">Remarks</span></span>  
 <span data-ttu-id="dcc5f-112">`CreateValue` 만듭니다는 `ICorDebugValue` 함수 실행에 사용 하 여의 목적 으로만 지정 된 형식의 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="dcc5f-112">`CreateValue` creates an `ICorDebugValue` object of the given type for the sole purpose of using it in a function evaluation.</span></span> <span data-ttu-id="dcc5f-113">이 값 개체 사용자 상수를 매개 변수로 전달 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcc5f-113">This value object can be used to pass user constants as parameters.</span></span>  
  
 <span data-ttu-id="dcc5f-114">값 형식의 기본 형식인 경우 해당 초기 값은 0 또는 null입니다.</span><span class="sxs-lookup"><span data-stu-id="dcc5f-114">If the type of the value is a primitive type, its initial value is zero or null.</span></span> <span data-ttu-id="dcc5f-115">사용 하 여 [icordebuggenericvalue:: Setvalue](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-setvalue-method.md) 기본 형식의 값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcc5f-115">Use [ICorDebugGenericValue::SetValue](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-setvalue-method.md) to set the value of a primitive type.</span></span>  
  
 <span data-ttu-id="dcc5f-116">하는 경우의 값 `elementType` ELEMENT_TYPE_CLASS은 "ICorDebugReferenceValue" 얻게 (에 반환 된 `ppValue`) null 개체 참조를 나타내는입니다.</span><span class="sxs-lookup"><span data-stu-id="dcc5f-116">If the value of `elementType` is ELEMENT_TYPE_CLASS, you get an "ICorDebugReferenceValue" (returned in `ppValue`) representing the null object reference.</span></span> <span data-ttu-id="dcc5f-117">Null 개체 참조 매개 변수가 있는 함수 실행을 전달 하려면이 개체를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcc5f-117">You can use this object to pass null to a function evaluation that has object reference parameters.</span></span> <span data-ttu-id="dcc5f-118">설정할 수 없습니다.는 `ICorDebugValue` ; 어디에이 항상 null로 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dcc5f-118">You cannot set the `ICorDebugValue` to anything; it always remains null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dcc5f-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="dcc5f-119">Requirements</span></span>  
 <span data-ttu-id="dcc5f-120">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="dcc5f-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dcc5f-121">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dcc5f-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dcc5f-122">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dcc5f-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dcc5f-123">**.NET framework 버전:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="dcc5f-123">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dcc5f-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dcc5f-124">See Also</span></span>  
    
 [<span data-ttu-id="dcc5f-125">CreateValueForType 메서드</span><span class="sxs-lookup"><span data-stu-id="dcc5f-125">CreateValueForType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-createvaluefortype-method.md)  
 <span data-ttu-id="dcc5f-126">ICorDebugValue</span><span class="sxs-lookup"><span data-stu-id="dcc5f-126">ICorDebugValue</span></span>
