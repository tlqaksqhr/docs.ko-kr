---
title: ICorDebugThread::GetProcess 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetProcess
helpviewer_keywords:
- ICorDebugThread::GetProcess method [.NET Framework debugging]
- GetProcess method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 163816e7-0739-4566-b3df-cd256be8b8a4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b41c7eeccad8b3f685c81e6afc23eaf19d862182
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33417614"
---
# <a name="icordebugthreadgetprocess-method"></a><span data-ttu-id="0490a-102">ICorDebugThread::GetProcess 메서드</span><span class="sxs-lookup"><span data-stu-id="0490a-102">ICorDebugThread::GetProcess Method</span></span>
<span data-ttu-id="0490a-103">이 ICorDebugThread를 포함 하는 프로세스에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0490a-103">Gets an interface pointer to the process of which this ICorDebugThread forms a part.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0490a-104">구문</span><span class="sxs-lookup"><span data-stu-id="0490a-104">Syntax</span></span>  
  
```  
HRESULT GetProcess (  
    [out] ICorDebugProcess   **ppProcess  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0490a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0490a-105">Parameters</span></span>  
 `ppProcess`  
 <span data-ttu-id="0490a-106">[out] 프로세스를 나타내는 ICorDebugProcess 인터페이스 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="0490a-106">[out] A pointer to the address of an ICorDebugProcess interface object that represents the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0490a-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0490a-107">Requirements</span></span>  
 <span data-ttu-id="0490a-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0490a-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0490a-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0490a-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0490a-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0490a-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0490a-111">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0490a-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
