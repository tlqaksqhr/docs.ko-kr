---
title: "ICorDebugArrayValue::HasBaseIndicies 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugArrayValue.HasBaseIndicies
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugArrayValue::HasBaseIndicies
helpviewer_keywords:
- HasBaseIndicies method [.NET Framework debugging]
- ICorDebugArrayValue::HasBaseIndicies method [.NET Framework debugging]
ms.assetid: aa26df07-e0a6-4608-bdef-d4afafec89aa
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 256429bfed350181aa13ee2c119eb5c9541ce231
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugarrayvaluehasbaseindicies-method"></a><span data-ttu-id="f6deb-102">ICorDebugArrayValue::HasBaseIndicies 메서드</span><span class="sxs-lookup"><span data-stu-id="f6deb-102">ICorDebugArrayValue::HasBaseIndicies Method</span></span>
<span data-ttu-id="f6deb-103">이 배열의 모든 차원은 기본 0이 아닌 인덱스가 있는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f6deb-103">Gets a value that indicates whether any dimensions of this array have a base index of non-zero.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6deb-104">구문</span><span class="sxs-lookup"><span data-stu-id="f6deb-104">Syntax</span></span>  
  
```  
HRESULT HasBaseIndicies (  
    [out] BOOL    *pbHasBaseIndicies  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f6deb-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f6deb-105">Parameters</span></span>  
 `pbHasBaseIndicies`  
 <span data-ttu-id="f6deb-106">[out] 부울 값이에 대 한 포인터 `true` 경우이 하나 이상의 차원을 `ICorDebugArrayValue` 개체의 0이 아닌 기본 인덱스가 있는지, 그렇지 않으면 부울 값이 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="f6deb-106">[out] A pointer to a Boolean value that is `true` if one or more dimensions of this `ICorDebugArrayValue` object have a base index of non-zero; otherwise, the Boolean value is `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f6deb-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f6deb-107">Requirements</span></span>  
 <span data-ttu-id="f6deb-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f6deb-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f6deb-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f6deb-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f6deb-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f6deb-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f6deb-111">**.NET framework 버전:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f6deb-111">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>
