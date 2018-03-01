---
title: "ICorDebugModule::GetName 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugModule.GetName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetName
helpviewer_keywords:
- ICorDebugModule::GetName method [.NET Framework debugging]
- GetName method, ICorDebugModule interface [.NET Framework debugging]
ms.assetid: db499637-7ba9-421e-b8b1-35856995e80b
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 64be936277b0ebe04248ae2913a882b628ee363f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmodulegetname-method"></a><span data-ttu-id="e9f00-102">ICorDebugModule::GetName 메서드</span><span class="sxs-lookup"><span data-stu-id="e9f00-102">ICorDebugModule::GetName Method</span></span>
<span data-ttu-id="e9f00-103">모듈의 파일 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e9f00-103">Gets the file name of the module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9f00-104">구문</span><span class="sxs-lookup"><span data-stu-id="e9f00-104">Syntax</span></span>  
  
```  
HRESULT GetName(  
    [in] ULONG32 cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e9f00-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e9f00-105">Parameters</span></span>  
 `cchname`  
 <span data-ttu-id="e9f00-106">[in] `szName` 배열의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="e9f00-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="e9f00-107">[in] 반환 된 이름의 길이에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e9f00-107">[in] A pointer to the length of the returned name.</span></span>  
  
 `szName`  
 <span data-ttu-id="e9f00-108">[out] 반환된 된 이름을 저장 하는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="e9f00-108">[out] An array that stores the returned name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e9f00-109">설명</span><span class="sxs-lookup"><span data-stu-id="e9f00-109">Remarks</span></span>  
 <span data-ttu-id="e9f00-110">`GetName` 모듈의 파일 이름에는 디스크에 있는 이름과 일치 하는 경우 메서드가 s_ok이 고 HRESULT를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9f00-110">The `GetName` method returns an S_OK HRESULT if the module's file name matches the name on disk.</span></span> <span data-ttu-id="e9f00-111">`GetName`맞추어진 등을 위해 동적 또는 메모리에 모듈 이름이 S_FALSE HRESULT를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9f00-111">`GetName` returns an S_FALSE HRESULT if the name is fabricated, such as for a dynamic or in-memory module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9f00-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e9f00-112">Requirements</span></span>  
 <span data-ttu-id="e9f00-113">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e9f00-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9f00-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e9f00-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e9f00-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e9f00-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e9f00-116">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9f00-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9f00-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e9f00-117">See Also</span></span>  
    
 
