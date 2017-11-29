---
title: "ICorConfiguration::AddDebuggerSpecialThread 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorConfiguration.AddDebuggerSpecialThread
api_location: mscoree.dll
api_type: COM
f1_keywords: AddDebuggerSpecialThread
helpviewer_keywords:
- AddDebuggerSpecialThread method [.NET Framework hosting]
- ICorConfiguration::AddDebuggerSpecialThread method [.NET Framework hosting]
ms.assetid: 1f1e3239-438e-4be9-a3bb-7d0722d3a76d
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2501461267ff7369cd9c48f4cef6cda42063a48b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icorconfigurationadddebuggerspecialthread-method"></a><span data-ttu-id="7e5e6-102">ICorConfiguration::AddDebuggerSpecialThread 메서드</span><span class="sxs-lookup"><span data-stu-id="7e5e6-102">ICorConfiguration::AddDebuggerSpecialThread Method</span></span>
<span data-ttu-id="7e5e6-103">디버깅 서비스에 특정 스레드를 계속 디버거가 응용 프로그램을 중지 하는 동안 관리 되거나 관리 되지 않는 디버깅 시나리오는 동시 실행 수 있어야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7e5e6-103">Indicates to the debugging services that a particular thread should be allowed to continue executing while the debugger has an application stopped during managed or unmanaged debugging scenarios.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e5e6-104">구문</span><span class="sxs-lookup"><span data-stu-id="7e5e6-104">Syntax</span></span>  
  
```  
HRESULT AddDebuggerSpecialThread (  
    [in] DWORD dwSpecialThreadId  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7e5e6-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7e5e6-105">Parameters</span></span>  
 `dwSpecialThreadId`  
 <span data-ttu-id="7e5e6-106">[in] 계속 실행 되도록 허용 되어야 하는 스레드의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="7e5e6-106">[in] The ID of the thread that should be allowed to continue executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7e5e6-107">설명</span><span class="sxs-lookup"><span data-stu-id="7e5e6-107">Remarks</span></span>  
 <span data-ttu-id="7e5e6-108">지정된 된 스레드가 관리 되는 코드를 실행 하거나 어떤 방식으로든에서 런타임에 입력 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7e5e6-108">The specified thread will not be allowed to run managed code or enter the runtime in any way.</span></span> <span data-ttu-id="7e5e6-109">이러한 스레드의 예로 레거시 스크립트 디버거를 지원 하기 위해 프로세스에서 스레드 수입니다.</span><span class="sxs-lookup"><span data-stu-id="7e5e6-109">An example of such a thread would be an in-process thread to support legacy script debuggers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7e5e6-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7e5e6-110">Requirements</span></span>  
 <span data-ttu-id="7e5e6-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7e5e6-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7e5e6-112">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7e5e6-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7e5e6-113">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="7e5e6-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7e5e6-114">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7e5e6-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e5e6-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7e5e6-115">See Also</span></span>  
 [<span data-ttu-id="7e5e6-116">ICorConfiguration 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7e5e6-116">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)
