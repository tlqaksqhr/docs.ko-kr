---
title: "ICorDebugILCode2::GetLocalVarSigToken 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- cpp
api_name:
- ICorDebugILCode2.GetLocalVarSigToken
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 17665b77-1342-4115-94fd-9f45b0ecfb0f
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 47004375194438b1ef0aaf61144ba6f16278545b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugilcode2getlocalvarsigtoken-method"></a><span data-ttu-id="93e41-102">ICorDebugILCode2::GetLocalVarSigToken 메서드</span><span class="sxs-lookup"><span data-stu-id="93e41-102">ICorDebugILCode2::GetLocalVarSigToken Method</span></span>
<span data-ttu-id="93e41-103">[.NET Framework 4.5.2 이상 버전에서 지원됨]</span><span class="sxs-lookup"><span data-stu-id="93e41-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="93e41-104">이 인스턴스로 표시되는 함수의 로컬 변수 서명에 대한 메타데이터 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="93e41-104">Gets the metadata token for the local variable signature for the function that is represented by this instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93e41-105">구문</span><span class="sxs-lookup"><span data-stu-id="93e41-105">Syntax</span></span>  
  
```cpp
HRESULT GetLocalVarSigToken(  
   [out] mdSignature *pmdSig  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="93e41-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="93e41-106">Parameters</span></span>  
 `pmdSig`  
 <span data-ttu-id="93e41-107">[out] 이 함수 로컬 변수 서명의 `mdSignature` 토큰에 대한 포인터이거나, 서명이 없으면(함수에 로컬 변수가 없으면) `mdSignatureNil`입니다.</span><span class="sxs-lookup"><span data-stu-id="93e41-107">[out] A pointer to the `mdSignature` token for the local variable signature for this function, or `mdSignatureNil` if there is no signature (that is, if the function doesn't have any local variables).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="93e41-108">설명</span><span class="sxs-lookup"><span data-stu-id="93e41-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="93e41-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="93e41-109">Requirements</span></span>  
 <span data-ttu-id="93e41-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="93e41-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="93e41-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="93e41-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="93e41-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="93e41-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="93e41-113">**.NET framework 버전:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="93e41-113">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93e41-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="93e41-114">See Also</span></span>  
 [<span data-ttu-id="93e41-115">ICorDebugILCode2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="93e41-115">ICorDebugILCode2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode2-interface.md)  
 [<span data-ttu-id="93e41-116">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="93e41-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
