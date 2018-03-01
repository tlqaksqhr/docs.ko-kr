---
title: "ICorDebugModule::GetBaseAddress 메서드"
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
- ICorDebugModule.GetBaseAddress
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetBaseAddress
helpviewer_keywords:
- GetBaseAddress method [.NET Framework debugging]
- ICorDebugModule::GetBaseAddress method [.NET Framework debugging]
ms.assetid: 26a82815-1982-4eb7-92d1-5c3d318d5be4
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: aca93086e5425d7579b1394f72b039938f519ca9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmodulegetbaseaddress-method"></a><span data-ttu-id="92c40-102">ICorDebugModule::GetBaseAddress 메서드</span><span class="sxs-lookup"><span data-stu-id="92c40-102">ICorDebugModule::GetBaseAddress Method</span></span>
<span data-ttu-id="92c40-103">모듈의 기준 주소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="92c40-103">Gets the base address of the module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92c40-104">구문</span><span class="sxs-lookup"><span data-stu-id="92c40-104">Syntax</span></span>  
  
```  
HRESULT GetBaseAddress(  
    [out] CORDB_ADDRESS *pAddress  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="92c40-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="92c40-105">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="92c40-106">[out] A `CORDB_ADDRESS` 모듈의 기준 주소를 지정 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="92c40-106">[out] A `CORDB_ADDRESS` that specifies the base address of the module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="92c40-107">설명</span><span class="sxs-lookup"><span data-stu-id="92c40-107">Remarks</span></span>  
 <span data-ttu-id="92c40-108">모듈이 네이티브 경우 (즉, 경우 모듈 네이티브 이미지 생성기, NGen.exe에서 생성 된) 이미지 기준 주소는 0이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="92c40-108">If the module is a native image (that is, if the module was produced by the native image generator, NGen.exe), its base address will be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="92c40-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="92c40-109">Requirements</span></span>  
 <span data-ttu-id="92c40-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="92c40-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="92c40-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="92c40-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="92c40-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="92c40-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="92c40-113">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="92c40-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92c40-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="92c40-114">See Also</span></span>  
    
 
