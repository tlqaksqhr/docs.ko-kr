---
title: ICorDebugThread::GetObject 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetObject
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetObject
helpviewer_keywords:
- GetObject method, ICorDebugThread interface [.NET Framework debugging]
- ICorDebugThread::GetObject method [.NET Framework debugging]
ms.assetid: 1590febe-96c2-4046-97db-d81d81d67e01
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ad2dd4cded6800ce016d821f8e3ffe01dcb6264b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33418261"
---
# <a name="icordebugthreadgetobject-method"></a><span data-ttu-id="ae141-102">ICorDebugThread::GetObject 메서드</span><span class="sxs-lookup"><span data-stu-id="ae141-102">ICorDebugThread::GetObject Method</span></span>
<span data-ttu-id="ae141-103">공용 언어 런타임 (CLR) 스레드에서에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ae141-103">Gets an interface pointer to the common language runtime (CLR) thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae141-104">구문</span><span class="sxs-lookup"><span data-stu-id="ae141-104">Syntax</span></span>  
  
```  
HRESULT GetObject (  
    [out] ICorDebugValue   **ppObject  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ae141-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ae141-105">Parameters</span></span>  
 `ppObject`  
 <span data-ttu-id="ae141-106">[out] CLR 스레드를 나타내는 ICorDebugValue 인터페이스 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ae141-106">[out] A pointer to the address of an ICorDebugValue interface object that represents the CLR thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae141-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ae141-107">Requirements</span></span>  
 <span data-ttu-id="ae141-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ae141-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae141-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ae141-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ae141-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ae141-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ae141-111">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae141-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae141-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ae141-112">See Also</span></span>  
 <xref:System.Threading.Thread>
