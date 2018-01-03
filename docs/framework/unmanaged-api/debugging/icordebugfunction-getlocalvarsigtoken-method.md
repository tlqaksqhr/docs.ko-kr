---
title: "ICorDebugFunction::GetLocalVarSigToken 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugFunction.GetLocalVarSigToken
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugFunction::GetLocalVarSigToken
helpviewer_keywords:
- ICorDebugFunction::GetLocalVarSigToken method [.NET Framework debugging]
- GetLocalVarSigToken method [.NET Framework debugging]
ms.assetid: 31e53494-bcc9-4981-91a4-f7e0f02cad48
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: bfd2998393429d26f4670edfeae44b83893f479d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugfunctiongetlocalvarsigtoken-method"></a><span data-ttu-id="f7ebe-102">ICorDebugFunction::GetLocalVarSigToken 메서드</span><span class="sxs-lookup"><span data-stu-id="f7ebe-102">ICorDebugFunction::GetLocalVarSigToken Method</span></span>
<span data-ttu-id="f7ebe-103">이 ICorDebugFunction 인스턴스로 표시 되는 함수의 로컬 변수 서명에 대 한 메타 데이터를 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f7ebe-103">Gets the metadata token for the local variable signature of the function that is represented by this ICorDebugFunction instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7ebe-104">구문</span><span class="sxs-lookup"><span data-stu-id="f7ebe-104">Syntax</span></span>  
  
```  
HRESULT GetLocalVarSigToken (  
    [out] mdSignature *pmdSig  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f7ebe-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f7ebe-105">Parameters</span></span>  
 `pmdSig`  
 <span data-ttu-id="f7ebe-106">[out] 에 대 한 포인터는 `mdSignature` 이 함수의 로컬 변수 서명에 대해 토큰 또는 `mdSignatureNil`이 함수는 로컬 변수가 없는 경우.</span><span class="sxs-lookup"><span data-stu-id="f7ebe-106">[out] A pointer to the `mdSignature` token for the local variable signature of this function, or `mdSignatureNil`, if this function has no local variables.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f7ebe-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f7ebe-107">Requirements</span></span>  
 <span data-ttu-id="f7ebe-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f7ebe-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f7ebe-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f7ebe-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f7ebe-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f7ebe-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f7ebe-111">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f7ebe-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
