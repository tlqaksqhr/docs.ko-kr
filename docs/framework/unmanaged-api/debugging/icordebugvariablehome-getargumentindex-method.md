---
title: "ICorDebugVariableHome::GetArgumentIndex 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
api_name: ICorDebugVariableHome.GetArgumentIndex
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugVariableHome::GetArgumentIndex
helpviewer_keywords:
- ICorDebugVariableHome::GetArgumentiIndex method [.NET Framework debugging]
- GetArgumentIndex method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: e86fcc72-388d-4009-ab21-8f9c3323e9a3
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 175e45758d26d8168279c825d41ee58d049edf0b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugvariablehomegetargumentindex-method"></a><span data-ttu-id="62dc6-102">ICorDebugVariableHome::GetArgumentIndex 메서드</span><span class="sxs-lookup"><span data-stu-id="62dc6-102">ICorDebugVariableHome::GetArgumentIndex Method</span></span>
<span data-ttu-id="62dc6-103">함수 인수 인덱스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="62dc6-103">Gets the index of a function argument.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62dc6-104">구문</span><span class="sxs-lookup"><span data-stu-id="62dc6-104">Syntax</span></span>  
  
```  
HRESULT GetArgumentIndex(  
    [out] ULONG32* pArgumentIndex  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="62dc6-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="62dc6-105">Parameters</span></span>  
 `pArgumentIndex`  
 <span data-ttu-id="62dc6-106">[out] 인수 인덱스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="62dc6-106">[out] A pointer to the argument index.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="62dc6-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="62dc6-107">Return Value</span></span>  
 <span data-ttu-id="62dc6-108">메서드는 다음 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="62dc6-108">The method returns the following values.</span></span>  
  
|<span data-ttu-id="62dc6-109">값</span><span class="sxs-lookup"><span data-stu-id="62dc6-109">Value</span></span>|<span data-ttu-id="62dc6-110">설명</span><span class="sxs-lookup"><span data-stu-id="62dc6-110">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="62dc6-111">이 메서드는 유효한 인수 인덱스를 반환 했습니다.</span><span class="sxs-lookup"><span data-stu-id="62dc6-111">The method call returned a valid argument index.</span></span>|  
|`E_FAIL`|<span data-ttu-id="62dc6-112">현재 [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) 인스턴스 지역 변수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="62dc6-112">The current [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) instance represents a local variable.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="62dc6-113">설명</span><span class="sxs-lookup"><span data-stu-id="62dc6-113">Remarks</span></span>  
 <span data-ttu-id="62dc6-114">이 인수에 대 한 메타 데이터를 검색 인수 인덱스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62dc6-114">The argument index can be used to retrieve metadata for this argument.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62dc6-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="62dc6-115">Requirements</span></span>  
 <span data-ttu-id="62dc6-116">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="62dc6-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62dc6-117">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="62dc6-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="62dc6-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="62dc6-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="62dc6-119">**.NET framework 버전:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="62dc6-119">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62dc6-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="62dc6-120">See Also</span></span>  
 [<span data-ttu-id="62dc6-121">ICorDebugVariableHome 인터페이스</span><span class="sxs-lookup"><span data-stu-id="62dc6-121">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
