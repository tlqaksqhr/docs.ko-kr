---
title: "ICorDebugThread::EnumerateChains 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugThread.EnumerateChains
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugThread::EnumerateChains
helpviewer_keywords:
- EnumerateChains method [.NET Framework debugging]
- ICorDebugThread::EnumerateChains method [.NET Framework debugging]
ms.assetid: ec00bc21-117e-4acd-9301-2cfafd5be8d3
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8e6a9637edb4a846b4d10dd6565533a9219ad558
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugthreadenumeratechains-method"></a><span data-ttu-id="4173f-102">ICorDebugThread::EnumerateChains 메서드</span><span class="sxs-lookup"><span data-stu-id="4173f-102">ICorDebugThread::EnumerateChains Method</span></span>
<span data-ttu-id="4173f-103">이 ICorDebugThread 개체에서 스택 체인을 모두 포함 하는 ICorDebugChainEnum 열거자에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="4173f-103">Gets an interface pointer to an ICorDebugChainEnum enumerator that contains all the stack chains in this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4173f-104">구문</span><span class="sxs-lookup"><span data-stu-id="4173f-104">Syntax</span></span>  
  
```  
HRESULT EnumerateChains (  
    [out] ICorDebugChainEnum **ppChains  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4173f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4173f-105">Parameters</span></span>  
 `ppChains`  
 <span data-ttu-id="4173f-106">[out] 주소에 대 한 포인터는 `ICorDebugChainEnum` 활성 (즉, 가장 최근의) 체인에서 시작이 스레드에서 모든 스택의 열거를 사용할 수 있는 개체를 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="4173f-106">[out] A pointer to the address of an `ICorDebugChainEnum` object that allows enumeration of all the stack chains in this thread, starting at the active (that is, the most recent) chain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4173f-107">설명</span><span class="sxs-lookup"><span data-stu-id="4173f-107">Remarks</span></span>  
 <span data-ttu-id="4173f-108">스택 체인 스레드에 대 한 실제 호출 스택을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4173f-108">The stack chain represents the physical call stack for the thread.</span></span> <span data-ttu-id="4173f-109">다음과 같은 경우 스택 체인 경계를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4173f-109">The following circumstances create a stack chain boundary:</span></span>  
  
-   <span data-ttu-id="4173f-110">관리 되는-관리 또는 관리 되지 않는 리소스에서 관리로 전환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4173f-110">A managed-to-unmanaged or unmanaged-to-managed transition.</span></span>  
  
-   <span data-ttu-id="4173f-111">컨텍스트 스위치입니다.</span><span class="sxs-lookup"><span data-stu-id="4173f-111">A context switch.</span></span>  
  
-   <span data-ttu-id="4173f-112">A의 사용자 스레드 하이재킹 디버거 합니다.</span><span class="sxs-lookup"><span data-stu-id="4173f-112">A debugger hijacking of a user thread.</span></span>  
  
 <span data-ttu-id="4173f-113">단일 컨텍스트에서 순수 관리 코드를 실행 하는 스레드에 대 한 단순한 경우, 스레드 및 스택 체인 간에 일대일로 대응 존재 합니다.</span><span class="sxs-lookup"><span data-stu-id="4173f-113">In the simple case for a thread that is running purely managed code in a single context, a one-to-one correspondence will exist between threads and stack chains.</span></span>  
  
 <span data-ttu-id="4173f-114">디버거 논리 호출 스택으로 모든 스레드의 실제 호출 스택을 다시 정렬 하려고 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4173f-114">A debugger may want to rearrange the physical call stacks of all threads into logical call stacks.</span></span> <span data-ttu-id="4173f-115">이 모든 스레드가 체인의 호출자/호출 수신자 관계에 의해 정렬 되 고 이러한 다시 그룹화 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4173f-115">This would involve sorting all the threads' chains by their caller/callee relationships and regrouping them.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4173f-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4173f-116">Requirements</span></span>  
 <span data-ttu-id="4173f-117">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4173f-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4173f-118">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4173f-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4173f-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4173f-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4173f-120">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4173f-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
