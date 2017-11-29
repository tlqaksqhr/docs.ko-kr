---
title: "ICorDebugProcess::GetHandle 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess.GetHandle
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess::GetHandle
helpviewer_keywords:
- GetHandle method, ICorDebugProcess interface [.NET Framework debugging]
- ICorDebugProcess::GetHandle method [.NET Framework debugging]
ms.assetid: e7d3ecf5-09d2-4d94-abb6-ff3483deebb6
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 139d9341e11b87aa0c10146fdfeaa3752e32467b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugprocessgethandle-method"></a><span data-ttu-id="0698c-102">ICorDebugProcess::GetHandle 메서드</span><span class="sxs-lookup"><span data-stu-id="0698c-102">ICorDebugProcess::GetHandle Method</span></span>
<span data-ttu-id="0698c-103">프로세스에 대 한 핸들을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0698c-103">Gets a handle to the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0698c-104">구문</span><span class="sxs-lookup"><span data-stu-id="0698c-104">Syntax</span></span>  
  
```  
HRESULT GetHandle([out] HPROCESS *phProcessHandle);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0698c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0698c-105">Parameters</span></span>  
 `phProcessHandle`  
 <span data-ttu-id="0698c-106">[out] 에 대 한 포인터는 `HPROCESS` 프로세스에 대 한 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="0698c-106">[out] A pointer to an `HPROCESS` that is the handle to the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0698c-107">설명</span><span class="sxs-lookup"><span data-stu-id="0698c-107">Remarks</span></span>  
 <span data-ttu-id="0698c-108">디버깅 인터페이스에 의해 검색 된 핸들을 소유 합니다.</span><span class="sxs-lookup"><span data-stu-id="0698c-108">The retrieved handle is owned by the debugging interface.</span></span> <span data-ttu-id="0698c-109">디버거는 핸들 사용 하기 전에 복제 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0698c-109">The debugger should duplicate the handle before using it.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0698c-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0698c-110">Requirements</span></span>  
 <span data-ttu-id="0698c-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0698c-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0698c-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0698c-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0698c-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0698c-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0698c-114">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0698c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
