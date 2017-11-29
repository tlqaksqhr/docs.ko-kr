---
title: "ICLRMetaHost::ExitProcess 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRMetaHost.ExitProcess
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRMetaHost::ExitProcess
helpviewer_keywords:
- ICLRMetaHost::ExitProcess method [.NET Framework hosting]
- ExitProcess method, ICLRMetaHost interface [.NET Framework hosting]
ms.assetid: b4df98cc-4e4e-407b-b8f4-e0076afef3a4
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 10fb9bef99a90a76ea5bb1f4abe73cd756717285
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="iclrmetahostexitprocess-method"></a><span data-ttu-id="1da49-102">ICLRMetaHost::ExitProcess 메서드</span><span class="sxs-lookup"><span data-stu-id="1da49-102">ICLRMetaHost::ExitProcess Method</span></span>
<span data-ttu-id="1da49-103">모든 로드 된 런타임을 정상적으로 종료 하 고 프로세스를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="1da49-103">Attempts to shut down all loaded runtimes gracefully and then terminates the process.</span></span> <span data-ttu-id="1da49-104">대체는 [CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md) 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="1da49-104">Supersedes the [CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1da49-105">구문</span><span class="sxs-lookup"><span data-stu-id="1da49-105">Syntax</span></span>  
  
```  
HRESULT ExitProcess (  
    [in] INT32 iExitCode);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1da49-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1da49-106">Parameters</span></span>  
 `iExitCode`  
 <span data-ttu-id="1da49-107">[in] 프로세스 종료 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="1da49-107">[in] The exit code for the process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1da49-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="1da49-108">Return Value</span></span>  
 <span data-ttu-id="1da49-109">이 메서드가 반환 하지 않으므로 반환 값이 정의 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1da49-109">This method never returns, so its return value is undefined.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1da49-110">설명</span><span class="sxs-lookup"><span data-stu-id="1da49-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1da49-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1da49-111">Requirements</span></span>  
 <span data-ttu-id="1da49-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1da49-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1da49-113">**헤더:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="1da49-113">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="1da49-114">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="1da49-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1da49-115">**.NET framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1da49-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1da49-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1da49-116">See Also</span></span>  
 [<span data-ttu-id="1da49-117">ICLRMetaHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1da49-117">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)  
 [<span data-ttu-id="1da49-118">호스팅</span><span class="sxs-lookup"><span data-stu-id="1da49-118">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
