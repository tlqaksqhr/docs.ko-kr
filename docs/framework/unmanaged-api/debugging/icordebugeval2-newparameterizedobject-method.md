---
title: "ICorDebugEval2::NewParameterizedObject 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugEval2.NewParameterizedObject
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugEval2::NewParameterizedObject
helpviewer_keywords:
- NewParameterizedObject method [.NET Framework debugging]
- ICorDebugEval2::NewParameterizedObject method [.NET Framework debugging]
ms.assetid: 3d705463-e640-4249-8036-4e8206d03cfe
topic_type: apiref
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 29b2470f50e96307ad91428fe1c712e7340baa32
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugeval2newparameterizedobject-method"></a><span data-ttu-id="0c582-102">ICorDebugEval2::NewParameterizedObject 메서드</span><span class="sxs-lookup"><span data-stu-id="0c582-102">ICorDebugEval2::NewParameterizedObject Method</span></span>
<span data-ttu-id="0c582-103">새 매개 변수가 있는 형식 개체를 인스턴스화하고 개체의 생성자 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c582-103">Instantiates a new parameterized type object and calls the object's constructor method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c582-104">구문</span><span class="sxs-lookup"><span data-stu-id="0c582-104">Syntax</span></span>  
  
```  
HRESULT NewParameterizedObject (  
    [in] ICorDebugFunction     *pConstructor,  
    [in] ULONG32               nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType *ppTypeArgs[],  
    [in] ULONG32               nArgs,  
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0c582-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0c582-105">Parameters</span></span>  
 `pConstructor`  
 <span data-ttu-id="0c582-106">[in] 인스턴스화할 수 개체의 생성자를 나타내는 ICorDebugFunction 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="0c582-106">[in] A pointer to an ICorDebugFunction object that represents the constructor of the object to be instantiated.</span></span>  
  
 `nTypeArgs`  
 <span data-ttu-id="0c582-107">[in] 형식 인수 수가 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c582-107">[in] The number of type arguments passed.</span></span>  
  
 `ppTypeArgs`  
 <span data-ttu-id="0c582-108">[in] 포인터의 배열을, 각 인스턴스화 중인 개체에 대 한 형식 인수를 나타내는 ICorDebugType 개체를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="0c582-108">[in] An array of pointers, each of which points to an ICorDebugType object that represents a type argument for the object that is being instantiated.</span></span>  
  
 `nArgs`  
 <span data-ttu-id="0c582-109">[in] 인수 개수가 생성자에 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c582-109">[in] The number of arguments passed to the constructor.</span></span>  
  
 `ppArgs`  
 <span data-ttu-id="0c582-110">[in] 생성자에 전달 되는 인수 값을 나타내는 ICorDebugValue 개체를 가리키는 각각 포인터의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="0c582-110">[in] An array of pointers, each of which points to an ICorDebugValue object that represents an argument value that is passed to the constructor.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0c582-111">설명</span><span class="sxs-lookup"><span data-stu-id="0c582-111">Remarks</span></span>  
 <span data-ttu-id="0c582-112">개체의 생성자 걸릴 수 있습니다 <xref:System.Type> 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="0c582-112">The object's constructor may take <xref:System.Type> parameters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0c582-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0c582-113">Requirements</span></span>  
 <span data-ttu-id="0c582-114">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0c582-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c582-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0c582-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0c582-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0c582-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0c582-117">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0c582-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
