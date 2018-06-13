---
title: ICorDebugProcess2::GetVersion 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.GetVersion
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::GetVersion
helpviewer_keywords:
- GetVersion method, ICorDebugProcess2 nterface [.NET Framework debugging]
- ICorDebugProcess2::GetVersion method [.NET Framework debugging]
ms.assetid: e11d5a75-61d9-4548-aedf-79c26079bd17
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c1e1f850e85099a466c497a8fcc822bce9510f69
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33416382"
---
# <a name="icordebugprocess2getversion-method"></a><span data-ttu-id="179fe-102">ICorDebugProcess2::GetVersion 메서드</span><span class="sxs-lookup"><span data-stu-id="179fe-102">ICorDebugProcess2::GetVersion Method</span></span>
<span data-ttu-id="179fe-103">이 프로세스에서 실행 중인 공용 언어 런타임 (CLR)의 버전 번호를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="179fe-103">Gets the version number of the common language runtime (CLR) that is running in this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="179fe-104">구문</span><span class="sxs-lookup"><span data-stu-id="179fe-104">Syntax</span></span>  
  
```  
HRESULT GetVersion (  
    [out] COR_VERSION     *version  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="179fe-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="179fe-105">Parameters</span></span>  
 `version`  
 <span data-ttu-id="179fe-106">[out] 런타임에서의 버전 번호를 저장 하는 COR_VERSION 구조에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="179fe-106">[out] A pointer to a COR_VERSION structure that stores the version number of the runtime.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="179fe-107">설명</span><span class="sxs-lookup"><span data-stu-id="179fe-107">Remarks</span></span>  
 <span data-ttu-id="179fe-108">`GetVersion` 메서드 없는 런타임 프로세스에서 로드 된 경우 오류 코드를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="179fe-108">The `GetVersion` method returns an error code if no runtime has been loaded in the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="179fe-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="179fe-109">Requirements</span></span>  
 <span data-ttu-id="179fe-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="179fe-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="179fe-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="179fe-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="179fe-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="179fe-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="179fe-113">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="179fe-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
