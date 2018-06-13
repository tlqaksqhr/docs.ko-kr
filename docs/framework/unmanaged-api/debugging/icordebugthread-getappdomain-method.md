---
title: ICorDebugThread::GetAppDomain 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetAppDomain
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetAppDomain
helpviewer_keywords:
- GetAppDomain method, ICorDebugThread interface [.NET Framework debugging]
- ICorDebugThread::GetAppDomain method [.NET Framework debugging]
ms.assetid: 415b3d34-8b35-4b60-a318-140646cc83f8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 51878f0334afe52608b60ca540e49c86fded148e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33418047"
---
# <a name="icordebugthreadgetappdomain-method"></a><span data-ttu-id="c3772-102">ICorDebugThread::GetAppDomain 메서드</span><span class="sxs-lookup"><span data-stu-id="c3772-102">ICorDebugThread::GetAppDomain Method</span></span>
<span data-ttu-id="c3772-103">이 ICorDebugThread 현재 실행 중인 응용 프로그램 도메인에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c3772-103">Gets an interface pointer to the application domain in which this ICorDebugThread is currently executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3772-104">구문</span><span class="sxs-lookup"><span data-stu-id="c3772-104">Syntax</span></span>  
  
```  
HRESULT GetAppDomain (  
    [out] ICorDebugAppDomain  **ppAppDomain  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c3772-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c3772-105">Parameters</span></span>  
 `ppAppDomain`  
 <span data-ttu-id="c3772-106">[out] 이 스레드가 현재 실행 중인 응용 프로그램 도메인을 나타내는 ICorDebugAppDomain 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c3772-106">[out] A pointer to an ICorDebugAppDomain object that represents the application domain in which this thread is currently executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c3772-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c3772-107">Requirements</span></span>  
 <span data-ttu-id="c3772-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c3772-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c3772-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c3772-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c3772-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c3772-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c3772-111">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c3772-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
