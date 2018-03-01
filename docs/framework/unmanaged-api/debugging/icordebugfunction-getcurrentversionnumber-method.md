---
title: "ICorDebugFunction::GetCurrentVersionNumber 메서드"
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
- ICorDebugFunction.GetCurrentVersionNumber
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetCurrentVersionNumber
helpviewer_keywords:
- GetCurrentVersionNumber method [.NET Framework debugging]
- ICorDebugFunction::GetCurrentVersionNumber method [.NET Framework debugging]
ms.assetid: c3af1575-cbe6-457a-bc08-c53460edcbc8
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0c230c8ca6da69b45d05b3319220eacfa6c1f212
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugfunctiongetcurrentversionnumber-method"></a><span data-ttu-id="9c79d-102">ICorDebugFunction::GetCurrentVersionNumber 메서드</span><span class="sxs-lookup"><span data-stu-id="9c79d-102">ICorDebugFunction::GetCurrentVersionNumber Method</span></span>
<span data-ttu-id="9c79d-103">ICorDebugFunction 개체가 나타내는 함수에 대 한 최신 편집의 버전 번호를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9c79d-103">Gets the version number of the latest edit made to the function represented by this ICorDebugFunction object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c79d-104">구문</span><span class="sxs-lookup"><span data-stu-id="9c79d-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentVersionNumber (  
    [out] ULONG32 *pnCurrentVersion  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9c79d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9c79d-105">Parameters</span></span>  
 `pnCurrentVersion`  
 <span data-ttu-id="9c79d-106">[out] 이 함수에 대 한 최신 편집의 버전 번호는 하는 정수 값에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="9c79d-106">[out] A pointer to an integer value that is the version number of the latest edit made to this function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9c79d-107">설명</span><span class="sxs-lookup"><span data-stu-id="9c79d-107">Remarks</span></span>  
 <span data-ttu-id="9c79d-108">이 함수에 대 한 최신 편집의 버전 번호는 함수 자체의 버전 번호 보다 클 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c79d-108">The version number of the latest edit made to this function may be greater than the version number of the function itself.</span></span> <span data-ttu-id="9c79d-109">사용 하 여는 [icordebugfunction2:: Getversionnumber](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-getversionnumber-method.md) 메서드 또는 [icordebugcode:: Getversionnumber](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getversionnumber-method.md) 함수의 버전 번호를 검색 하는 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="9c79d-109">Use either the [ICorDebugFunction2::GetVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-getversionnumber-method.md) method or the [ICorDebugCode::GetVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getversionnumber-method.md) method to retrieve the version number of the function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9c79d-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9c79d-110">Requirements</span></span>  
 <span data-ttu-id="9c79d-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9c79d-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9c79d-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9c79d-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9c79d-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9c79d-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9c79d-114">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9c79d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
