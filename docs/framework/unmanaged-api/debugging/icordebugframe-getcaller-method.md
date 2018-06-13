---
title: ICorDebugFrame::GetCaller 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetCaller
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetCaller
helpviewer_keywords:
- GetCaller method, ICorDebugFrame interface [.NET Framework debugging]
- ICorDebugFrame::GetCaller method [.NET Framework debugging]
ms.assetid: bfdc946b-8238-4eb9-8a85-884049fb0fd4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2452f4be0acde300676bf56011416e0a9ef16464
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33411718"
---
# <a name="icordebugframegetcaller-method"></a><span data-ttu-id="44da7-102">ICorDebugFrame::GetCaller 메서드</span><span class="sxs-lookup"><span data-stu-id="44da7-102">ICorDebugFrame::GetCaller Method</span></span>
<span data-ttu-id="44da7-103">이 프레임을 호출한 현재 체인에서 ICorDebugFrame 개체에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="44da7-103">Gets a pointer to the ICorDebugFrame object in the current chain that called this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44da7-104">구문</span><span class="sxs-lookup"><span data-stu-id="44da7-104">Syntax</span></span>  
  
```  
HRESULT GetCaller (  
    [out] ICorDebugFrame     **ppFrame  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="44da7-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="44da7-105">Parameters</span></span>  
 `ppFrame`  
 <span data-ttu-id="44da7-106">[out] 주소에 대 한 포인터는 `ICorDebugFrame` 호출 프레임을 나타내는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="44da7-106">[out] A pointer to the address of an `ICorDebugFrame` object that represents the calling frame.</span></span> <span data-ttu-id="44da7-107">이 값은 호출된 프레임은 현재 체인에서 가장 바깥쪽 프레임 경우 null입니다.</span><span class="sxs-lookup"><span data-stu-id="44da7-107">This value is null if the called frame is the outermost frame in the current chain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="44da7-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="44da7-108">Requirements</span></span>  
 <span data-ttu-id="44da7-109">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="44da7-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="44da7-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="44da7-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="44da7-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="44da7-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="44da7-112">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="44da7-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
