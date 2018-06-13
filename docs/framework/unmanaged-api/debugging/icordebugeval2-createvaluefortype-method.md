---
title: ICorDebugEval2::CreateValueForType 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugEval2.CreateValueForType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2::CreateValueForType
helpviewer_keywords:
- CreateValueForType method [.NET Framework debugging]
- ICorDebugEval2::CreateValueForType method [.NET Framework debugging]
ms.assetid: ea38ae20-7e0a-427a-be77-d78fae719d82
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 683457c249915708becadaeda9dec265666e2023
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33412109"
---
# <a name="icordebugeval2createvaluefortype-method"></a><span data-ttu-id="a3ecc-102">ICorDebugEval2::CreateValueForType 메서드</span><span class="sxs-lookup"><span data-stu-id="a3ecc-102">ICorDebugEval2::CreateValueForType Method</span></span>
<span data-ttu-id="a3ecc-103">초기 값이 0 또는 null 인 지정 된 형식의 새 ICorDebugValue에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a3ecc-103">Gets a pointer to a new ICorDebugValue of the specified type, with an initial value of zero or null.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3ecc-104">구문</span><span class="sxs-lookup"><span data-stu-id="a3ecc-104">Syntax</span></span>  
  
```  
HRESULT CreateValueForType (  
    [in] ICorDebugType         *pType,  
    [out] ICorDebugValue       **ppValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a3ecc-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a3ecc-105">Parameters</span></span>  
 `pType`  
 <span data-ttu-id="a3ecc-106">[in] 형식을 나타내는 ICorDebugType 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a3ecc-106">[in] Pointer to an ICorDebugType object that represents the type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="a3ecc-107">[out] 주소에 대 한 포인터는 `ICorDebugValue` 값을 나타내는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="a3ecc-107">[out] Pointer to the address of an `ICorDebugValue` object that represents the value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a3ecc-108">설명</span><span class="sxs-lookup"><span data-stu-id="a3ecc-108">Remarks</span></span>  
 <span data-ttu-id="a3ecc-109">`CreateValueForType` 일반화 [icordebugeval:: Createvalue](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-createvalue-method.md) 임의의 개체 종류를 지정할 수 있도록 하 여 포함 하 여 생성 된 형식을 같은 `List<int>`합니다.</span><span class="sxs-lookup"><span data-stu-id="a3ecc-109">`CreateValueForType` generalizes [ICorDebugEval::CreateValue](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-createvalue-method.md) by allowing you to specify an arbitrary object type, including constructed types such as `List<int>`.</span></span> <span data-ttu-id="a3ecc-110">이 메서드의 유일한 목적은 함수 실행에 전달 될 수 있는 값을 생성 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a3ecc-110">The only purpose of this method is to generate a value that can be passed to a function evaluation.</span></span>  
  
 <span data-ttu-id="a3ecc-111">클래스 또는 값 형식이 형식 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3ecc-111">The type must be a class or a value type.</span></span> <span data-ttu-id="a3ecc-112">배열 값 또는 문자열 값을 만드는이 메서드를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a3ecc-112">You cannot use this method to create array values or string values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a3ecc-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a3ecc-113">Requirements</span></span>  
 <span data-ttu-id="a3ecc-114">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a3ecc-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a3ecc-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a3ecc-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a3ecc-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a3ecc-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a3ecc-117">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a3ecc-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
