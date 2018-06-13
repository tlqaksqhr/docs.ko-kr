---
title: ICLRMetaHost::ExitProcess 메서드
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.ExitProcess
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::ExitProcess
helpviewer_keywords:
- ICLRMetaHost::ExitProcess method [.NET Framework hosting]
- ExitProcess method, ICLRMetaHost interface [.NET Framework hosting]
ms.assetid: b4df98cc-4e4e-407b-b8f4-e0076afef3a4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fc71762fb4a660cf84814cdd46d09696a161f3c9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33431599"
---
# <a name="iclrmetahostexitprocess-method"></a><span data-ttu-id="0ad91-102">ICLRMetaHost::ExitProcess 메서드</span><span class="sxs-lookup"><span data-stu-id="0ad91-102">ICLRMetaHost::ExitProcess Method</span></span>
<span data-ttu-id="0ad91-103">모든 로드 된 런타임을 정상적으로 종료 하 고 프로세스를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ad91-103">Attempts to shut down all loaded runtimes gracefully and then terminates the process.</span></span> <span data-ttu-id="0ad91-104">대체는 [CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md) 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="0ad91-104">Supersedes the [CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ad91-105">구문</span><span class="sxs-lookup"><span data-stu-id="0ad91-105">Syntax</span></span>  
  
```  
HRESULT ExitProcess (  
    [in] INT32 iExitCode);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0ad91-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0ad91-106">Parameters</span></span>  
 `iExitCode`  
 <span data-ttu-id="0ad91-107">[in] 프로세스 종료 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="0ad91-107">[in] The exit code for the process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0ad91-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="0ad91-108">Return Value</span></span>  
 <span data-ttu-id="0ad91-109">이 메서드가 반환 하지 않으므로 반환 값이 정의 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0ad91-109">This method never returns, so its return value is undefined.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0ad91-110">설명</span><span class="sxs-lookup"><span data-stu-id="0ad91-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ad91-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0ad91-111">Requirements</span></span>  
 <span data-ttu-id="0ad91-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0ad91-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ad91-113">**헤더:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="0ad91-113">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="0ad91-114">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="0ad91-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0ad91-115">**.NET framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ad91-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ad91-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0ad91-116">See Also</span></span>  
 [<span data-ttu-id="0ad91-117">ICLRMetaHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0ad91-117">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)  
 [<span data-ttu-id="0ad91-118">호스팅</span><span class="sxs-lookup"><span data-stu-id="0ad91-118">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
