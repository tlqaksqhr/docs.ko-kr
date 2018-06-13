---
title: ICorDebugEval::NewArray 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugEval.NewArray
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::NewArray
helpviewer_keywords:
- NewArray method [.NET Framework debugging]
- ICorDebugEval::NewArray method [.NET Framework debugging]
ms.assetid: cc79a67d-5368-434d-a943-209db90491b9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 38b00d903fdd7301415a8df7642e12366178fd10
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33413942"
---
# <a name="icordebugevalnewarray-method"></a><span data-ttu-id="9a6fc-102">ICorDebugEval::NewArray 메서드</span><span class="sxs-lookup"><span data-stu-id="9a6fc-102">ICorDebugEval::NewArray Method</span></span>
<span data-ttu-id="9a6fc-103">지정한 요소 형식 및 차원에 대 한 새 배열을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="9a6fc-103">Allocates a new array of the specified element type and dimensions.</span></span>  
  
 <span data-ttu-id="9a6fc-104">이 메서드는.NET Framework 버전 2.0에서에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9a6fc-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="9a6fc-105">사용 하 여 [icordebugeval2:: Newparameterizedarray](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedarray-method.md) 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a6fc-105">Use [ICorDebugEval2::NewParameterizedArray](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedarray-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a6fc-106">구문</span><span class="sxs-lookup"><span data-stu-id="9a6fc-106">Syntax</span></span>  
  
```  
HRESULT NewArray (  
    [in] CorElementType     elementType,  
    [in] ICorDebugClass     *pElementClass,  
    [in] ULONG32            rank,  
    [in, size_is(rank)] ULONG32 dims[],  
    [in, size_is(rank)] ULONG32 lowBounds[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9a6fc-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9a6fc-107">Parameters</span></span>  
 `elementType`  
 <span data-ttu-id="9a6fc-108">[in] 배열의 요소 형식을 지정 하는 CorElementType 열거형의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="9a6fc-108">[in] A value of the CorElementType enumeration that specifies the element type of the array.</span></span>  
  
 `pElementClass`  
 <span data-ttu-id="9a6fc-109">[in] 요소 클래스를 지정 하는 ICorDebugClass 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="9a6fc-109">[in] A pointer to a ICorDebugClass object that specifies the class of the element.</span></span> <span data-ttu-id="9a6fc-110">이 값은 요소 형식은 기본 형식인 경우에 null 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a6fc-110">This value may be null if the element type is a primitive type.</span></span>  
  
 `rank`  
 <span data-ttu-id="9a6fc-111">[in] 배열의 차원 수입니다.</span><span class="sxs-lookup"><span data-stu-id="9a6fc-111">[in] The number of dimensions of the array.</span></span> <span data-ttu-id="9a6fc-112">.NET Framework 2.0에서이 값에는 1 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a6fc-112">In the .NET Framework 2.0, this value must be 1.</span></span>  
  
 `dims`  
 <span data-ttu-id="9a6fc-113">[in] 바이트 배열의 각 차원 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="9a6fc-113">[in] The size, in bytes, of each dimension of the array.</span></span>  
  
 `lowBounds`  
 <span data-ttu-id="9a6fc-114">[in] 선택적 항목으로,</span><span class="sxs-lookup"><span data-stu-id="9a6fc-114">[in] Optional.</span></span> <span data-ttu-id="9a6fc-115">배열의 각 차원 하 한입니다.</span><span class="sxs-lookup"><span data-stu-id="9a6fc-115">The lower bound of each dimension of the array.</span></span> <span data-ttu-id="9a6fc-116">이 값을 생략 하면 각 차원에 대 한 하한값 0으로 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a6fc-116">If this value is omitted, a lower bound of zero is assumed for each dimension.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9a6fc-117">설명</span><span class="sxs-lookup"><span data-stu-id="9a6fc-117">Remarks</span></span>  
 <span data-ttu-id="9a6fc-118">배열의는 스레드가 현재 실행 중인 응용 프로그램 도메인에서 항상 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="9a6fc-118">The array is always created in the application domain in which the thread is currently executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a6fc-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9a6fc-119">Requirements</span></span>  
 <span data-ttu-id="9a6fc-120">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9a6fc-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a6fc-121">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9a6fc-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9a6fc-122">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9a6fc-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9a6fc-123">**.NET framework 버전:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="9a6fc-123">**.NET Framework Versions:** 1.1, 1.0</span></span>
