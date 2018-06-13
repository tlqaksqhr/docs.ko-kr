---
title: ICLRErrorReportingManager 인터페이스
ms.date: 03/30/2017
api_name:
- ICLRErrorReportingManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRErrorReportingManager
helpviewer_keywords:
- ICLRErrorReportingManager interface [.NET Framework hosting]
ms.assetid: ea8af0d5-4133-4472-8a1f-50570d7e85fa
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bf9e04ed1d3a68fed120c4c13ad992af1f777244
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33433798"
---
# <a name="iclrerrorreportingmanager-interface"></a><span data-ttu-id="d1e0b-102">ICLRErrorReportingManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d1e0b-102">ICLRErrorReportingManager Interface</span></span>
<span data-ttu-id="d1e0b-103">오류 보고에 대 한 사용자 지정 스택 덤프를 구성 하기 위해 호스트에 사용할 수 있는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1e0b-103">Provides methods that allow the host to configure custom stack dumps for error reporting.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d1e0b-104">메서드</span><span class="sxs-lookup"><span data-stu-id="d1e0b-104">Methods</span></span>  
  
|<span data-ttu-id="d1e0b-105">메서드</span><span class="sxs-lookup"><span data-stu-id="d1e0b-105">Method</span></span>|<span data-ttu-id="d1e0b-106">설명</span><span class="sxs-lookup"><span data-stu-id="d1e0b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d1e0b-107">BeginCustomDump 메서드</span><span class="sxs-lookup"><span data-stu-id="d1e0b-107">BeginCustomDump Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md)|<span data-ttu-id="d1e0b-108">오류 보고에 대 한 사용자 지정 스택 덤프의 구성을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d1e0b-108">Specifies the configuration of custom stack dumps for error reporting.</span></span>|  
|[<span data-ttu-id="d1e0b-109">EndCustomDump 메서드</span><span class="sxs-lookup"><span data-stu-id="d1e0b-109">EndCustomDump Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-endcustomdump-method.md)|<span data-ttu-id="d1e0b-110">에 대 한 이전 호출에 의해 설정 된 사용자 지정 스택 덤프 구성을 지웁니다 `BeginCustomDump`합니다.</span><span class="sxs-lookup"><span data-stu-id="d1e0b-110">Clears the custom stack dump configuration that was set by an earlier call to `BeginCustomDump`.</span></span>|  
|[<span data-ttu-id="d1e0b-111">GetBucketParametersForCurrentException 메서드</span><span class="sxs-lookup"><span data-stu-id="d1e0b-111">GetBucketParametersForCurrentException Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-getbucketparametersforcurrentexception-method.md)|<span data-ttu-id="d1e0b-112">호출 스레드에서 현재 예외에 대 한 Watson 버킷이 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d1e0b-112">Gets the Watson bucket for the current exception on the calling thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d1e0b-113">설명</span><span class="sxs-lookup"><span data-stu-id="d1e0b-113">Remarks</span></span>  
 <span data-ttu-id="d1e0b-114">`BeginCustomDump` 메서드는 사용자 지정 스택 덤프 구성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1e0b-114">The `BeginCustomDump` method sets custom stack dump configuration.</span></span> <span data-ttu-id="d1e0b-115">`EndCustomDump` 메서드를 사용자 지정 스택 덤프 구성을 지워지고 연결 된 모든 상태를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1e0b-115">The `EndCustomDump` method clears the custom stack dump configuration and frees any associated state.</span></span> <span data-ttu-id="d1e0b-116">사용자 지정 덤프 완료 된 후 호출 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1e0b-116">It should be called after the custom dump is complete.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d1e0b-117">호출 하지 못하면 `EndCustomDump` 하면 메모리 누수를 발생 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="d1e0b-117">Failure to call `EndCustomDump` causes memory to leak.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d1e0b-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d1e0b-118">Requirements</span></span>  
 <span data-ttu-id="d1e0b-119">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d1e0b-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d1e0b-120">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d1e0b-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d1e0b-121">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="d1e0b-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d1e0b-122">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d1e0b-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1e0b-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d1e0b-123">See Also</span></span>  
 [<span data-ttu-id="d1e0b-124">ECustomDumpItemKind 열거형</span><span class="sxs-lookup"><span data-stu-id="d1e0b-124">ECustomDumpItemKind Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md)  
 [<span data-ttu-id="d1e0b-125">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d1e0b-125">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
