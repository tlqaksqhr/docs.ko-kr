---
title: ICoreClrDebugTarget::FreeMemory 메서드
ms.date: 03/30/2017
api_name:
- ICoreDebugTarget.FreeMemory
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- ICoreClrDebugTarget::FreeMemory
helpviewer_keywords:
- remote debugging API [Silverlight]
- FreeMemory method, ICoreClrDebugTarget interface [Silverlight debugging]
- ICorClrDebugTarget::FreeMemory method [Silverlight debugging]
- Silverlight, remote debugging
ms.assetid: 98f2a0db-a6ec-4f9b-861d-f82485237d08
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cbaf312d3f9200448d43f12c5d3f8052aa6d36a5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33420152"
---
# <a name="icoreclrdebugtargetfreememory-method"></a><span data-ttu-id="ec6a2-102">ICoreClrDebugTarget::FreeMemory 메서드</span><span class="sxs-lookup"><span data-stu-id="ec6a2-102">ICoreClrDebugTarget::FreeMemory Method</span></span>
<span data-ttu-id="ec6a2-103">에 의해 할당 된 메모리를 해제는 [icoreclrdebugtarget:: Enumprocesses](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-enumprocesses-method.md) 및 [icoreclrdebugtarget:: Enumruntimes](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-enumruntimes-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="ec6a2-103">Frees the memory allocated by the [ICoreClrDebugTarget::EnumProcesses](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-enumprocesses-method.md) and [ICoreClrDebugTarget::EnumRuntimes](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-enumruntimes-method.md) methods.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec6a2-104">구문</span><span class="sxs-lookup"><span data-stu-id="ec6a2-104">Syntax</span></span>  
  
```  
void FreeMemory (  
     [in] void*pMemory);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ec6a2-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ec6a2-105">Parameters</span></span>  
 `pMemory`  
 <span data-ttu-id="ec6a2-106">[in] 반환 되는 배열에 대 한 포인터는 [icoreclrdebugtarget:: Enumprocesses](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-enumprocesses-method.md) 또는 [icoreclrdebugtarget:: Enumruntimes](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-enumruntimes-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="ec6a2-106">[in] A pointer to the array that is returned by either the [ICoreClrDebugTarget::EnumProcesses](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-enumprocesses-method.md) or the [ICoreClrDebugTarget::EnumRuntimes](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-enumruntimes-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ec6a2-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ec6a2-107">Requirements</span></span>  
 <span data-ttu-id="ec6a2-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ec6a2-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ec6a2-109">**헤더:** CoreClrRemoteDebuggingInterfaces.h</span><span class="sxs-lookup"><span data-stu-id="ec6a2-109">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="ec6a2-110">**라이브러리:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="ec6a2-110">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="ec6a2-111">**.NET framework 버전:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="ec6a2-111">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec6a2-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ec6a2-112">See Also</span></span>  
 [<span data-ttu-id="ec6a2-113">ICoreClrDebugTarget 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ec6a2-113">ICoreClrDebugTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-interface.md)
