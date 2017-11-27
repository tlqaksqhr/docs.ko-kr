---
title: "ICorDebugProcess::GetThread 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess.GetThread
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess::GetThread
helpviewer_keywords:
- ICorDebugProcess::GetThread method [.NET Framework debugging]
- GetThread method, ICorDebugProcess interface [.NET Framework debugging]
ms.assetid: a48261ed-700b-41c9-8cb4-18c526546603
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: da5acebb9cb90efa69b0f553a1480e5e6883d079
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugprocessgetthread-method"></a><span data-ttu-id="8bede-102">ICorDebugProcess::GetThread 메서드</span><span class="sxs-lookup"><span data-stu-id="8bede-102">ICorDebugProcess::GetThread Method</span></span>
<span data-ttu-id="8bede-103">지정 된 운영 체제 (OS) 스레드 ID를 가집니다.이 프로세스의이 스레드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8bede-103">Gets this process's thread that has the specified operating system (OS) thread ID.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8bede-104">구문</span><span class="sxs-lookup"><span data-stu-id="8bede-104">Syntax</span></span>  
  
```  
HRESULT GetThread(  
    [in] DWORD dwThreadId,  
    [out] ICorDebugThread **ppThread);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8bede-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8bede-105">Parameters</span></span>  
 `dwThreadId`  
 <span data-ttu-id="8bede-106">[in] 운영 체제 스레드의 ID를 검색할 스레드입니다.</span><span class="sxs-lookup"><span data-stu-id="8bede-106">[in] The OS thread ID of the thread to be retrieved.</span></span>  
  
 `ppThread`  
 <span data-ttu-id="8bede-107">[out] 스레드를 나타내는 ICorDebugThread 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="8bede-107">[out] A pointer to the address of an ICorDebugThread object that represents the thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8bede-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8bede-108">Requirements</span></span>  
 <span data-ttu-id="8bede-109">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8bede-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8bede-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8bede-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8bede-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8bede-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8bede-112">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8bede-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
