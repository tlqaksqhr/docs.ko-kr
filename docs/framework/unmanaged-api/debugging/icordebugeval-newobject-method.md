---
title: ICorDebugEval::NewObject 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugEval.NewObject
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::NewObject
helpviewer_keywords:
- NewObject method [.NET Framework debugging]
- ICorDebugEval::NewObject method [.NET Framework debugging]
ms.assetid: ce3025e8-defa-4c5e-8298-f49d71fa5736
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5ff378602fc7338263ef49aee6802d2138bab9d2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33413174"
---
# <a name="icordebugevalnewobject-method"></a><span data-ttu-id="6f21d-102">ICorDebugEval::NewObject 메서드</span><span class="sxs-lookup"><span data-stu-id="6f21d-102">ICorDebugEval::NewObject Method</span></span>
<span data-ttu-id="6f21d-103">새 개체 인스턴스를 할당 하 고 지정된 된 생성자 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f21d-103">Allocates a new object instance and calls the specified constructor method.</span></span>  
  
 <span data-ttu-id="6f21d-104">이 메서드는.NET Framework 버전 2.0에서에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6f21d-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="6f21d-105">사용 하 여 [icordebugeval2:: Newparameterizedobject](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobject-method.md) 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f21d-105">Use [ICorDebugEval2::NewParameterizedObject](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobject-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f21d-106">구문</span><span class="sxs-lookup"><span data-stu-id="6f21d-106">Syntax</span></span>  
  
```  
HRESULT NewObject (  
    [in] ICorDebugFunction  *pConstructor,  
    [in] ULONG32            nArgs,  
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6f21d-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6f21d-107">Parameters</span></span>  
 `pConstructor`  
 <span data-ttu-id="6f21d-108">[in] 생성자가 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f21d-108">[in] The constructor to be called.</span></span>  
  
 `nArgs`  
 <span data-ttu-id="6f21d-109">[in] `ppArgs` 배열의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="6f21d-109">[in] The size of the `ppArgs` array.</span></span>  
  
 `ppArgs`  
 <span data-ttu-id="6f21d-110">[in] ICorDebugValue 개체의 생성자에 전달 될 인수를 나타내는 각각의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="6f21d-110">[in] An array of ICorDebugValue objects, each of which represents an argument to be passed to the constructor.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6f21d-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6f21d-111">Requirements</span></span>  
 <span data-ttu-id="6f21d-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6f21d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6f21d-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6f21d-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6f21d-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6f21d-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6f21d-115">**.NET framework 버전:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="6f21d-115">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f21d-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6f21d-116">See Also</span></span>  
 [<span data-ttu-id="6f21d-117">NewParameterizedObject 메서드</span><span class="sxs-lookup"><span data-stu-id="6f21d-117">NewParameterizedObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobject-method.md)
