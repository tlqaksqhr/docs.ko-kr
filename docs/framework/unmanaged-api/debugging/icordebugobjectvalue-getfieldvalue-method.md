---
title: "ICorDebugObjectValue::GetFieldValue 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugObjectValue.GetFieldValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugObjectValue::GetFieldValue
helpviewer_keywords:
- ICorDebugObjectValue::GetFieldValue method [.NET Framework debugging]
- GetFieldValue method [.NET Framework debugging]
ms.assetid: c96770b0-3e09-47bb-bd29-20353b043459
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 33c3f368d9b78b899f54c989427ea1f660346487
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugobjectvaluegetfieldvalue-method"></a><span data-ttu-id="11cea-102">ICorDebugObjectValue::GetFieldValue 메서드</span><span class="sxs-lookup"><span data-stu-id="11cea-102">ICorDebugObjectValue::GetFieldValue Method</span></span>
<span data-ttu-id="11cea-103">이 개체 값에 대 한 지정된 된 클래스의 지정된 된 필드의 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="11cea-103">Gets the value of the specified field of the specified class for this object value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11cea-104">구문</span><span class="sxs-lookup"><span data-stu-id="11cea-104">Syntax</span></span>  
  
```  
HRESULT GetFieldValue (  
    [in]  ICorDebugClass     *pClass,  
    [in]  mdFieldDef         fieldDef,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="11cea-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="11cea-105">Parameters</span></span>  
 `pClass`  
 <span data-ttu-id="11cea-106">[in] 필드 값을 가져올 수 있도록 클래스를 나타내는 "ICorDebugClass" 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="11cea-106">[in] A pointer to an "ICorDebugClass" object that represents the class for which to get the field value.</span></span>  
  
 `fieldDef`  
 <span data-ttu-id="11cea-107">[in] `mdFieldDef` 필드를 설명 하는 메타 데이터를 참조 하는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="11cea-107">[in] An `mdFieldDef` token that references the metadata describing the field.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="11cea-108">[out] 지정된 된 필드의 값을 나타내는 "ICorDebugValue" 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="11cea-108">[out] A pointer to an "ICorDebugValue" object that represents the value of the specified field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="11cea-109">설명</span><span class="sxs-lookup"><span data-stu-id="11cea-109">Remarks</span></span>  
 <span data-ttu-id="11cea-110">에 지정 된 클래스는 `pClass` 매개 변수를 개체 값의 클래스의 계층 구조에 있어야 하며 필드에는 해당 클래스의 필드 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="11cea-110">The class, specified in the `pClass` parameter, must be in the hierarchy of the object value's class, and the field must be a field of that class.</span></span>  
  
 <span data-ttu-id="11cea-111">`GetFieldValue` 메서드는 제네릭 클래스 및 제네릭 개체에 대 한 실패 하지 것입니다.</span><span class="sxs-lookup"><span data-stu-id="11cea-111">The `GetFieldValue` method will still succeed for generic objects and generic classes.</span></span> <span data-ttu-id="11cea-112">예를 들어 경우 MyDictionary\<V > 사전에서 상속\<문자열, V >, MyDictionary 형식의 개체 값이 고\<i n t 32 > 전달 하는 `ICorDebugClass` 사전에 대 한 개체\<K, V > 됩니다 사전의 필드를 성공적으로 가져오기\<문자열, i n t 32 >입니다.</span><span class="sxs-lookup"><span data-stu-id="11cea-112">For example, if MyDictionary\<V> inherits from Dictionary\<string,V>, and the object value is of type MyDictionary\<int32>, passing the `ICorDebugClass` object for Dictionary\<K,V> will successfully get a field of Dictionary\<string,int32>.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11cea-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="11cea-113">Requirements</span></span>  
 <span data-ttu-id="11cea-114">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="11cea-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="11cea-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="11cea-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="11cea-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="11cea-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="11cea-117">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="11cea-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11cea-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="11cea-118">See Also</span></span>  
    
 
