---
title: LPTHREAD_START_ROUTINE 함수 포인터
ms.date: 03/30/2017
api_name:
- LPTHREAD_START_ROUTINE
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- LPTHREAD_START_ROUTINE
helpviewer_keywords:
- LPTHREAD_START_ROUTINE function pointer [.NET Framework hosting]
ms.assetid: 7b9b93b0-fe92-42ba-8693-701168a29dde
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5025b75106b2cb0853047a09ca263f795d99633f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33441181"
---
# <a name="lpthreadstartroutine-function-pointer"></a><span data-ttu-id="6bdeb-102">LPTHREAD_START_ROUTINE 함수 포인터</span><span class="sxs-lookup"><span data-stu-id="6bdeb-102">LPTHREAD_START_ROUTINE Function Pointer</span></span>
<span data-ttu-id="6bdeb-103">스레드 실행을 시작 했음을 호스트에 알려 줍니다 하는 함수를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="6bdeb-103">Points to a function that notifies the host that a thread has started to execute.</span></span>  
  
 <span data-ttu-id="6bdeb-104">이 함수 포인터에서 더 이상 사용 되지는 [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="6bdeb-104">This function pointer has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6bdeb-105">구문</span><span class="sxs-lookup"><span data-stu-id="6bdeb-105">Syntax</span></span>  
  
```  
typedef DWORD (__stdcall *LPTHREAD_START_ROUTINE) (  
    [in] LPVOID lpThreadParameter  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6bdeb-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6bdeb-106">Parameters</span></span>  
 `lpThreadParameter`  
 <span data-ttu-id="6bdeb-107">[in] 실행 시작 된 코드에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6bdeb-107">[in] A pointer to the code that has started executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6bdeb-108">설명</span><span class="sxs-lookup"><span data-stu-id="6bdeb-108">Remarks</span></span>  
 <span data-ttu-id="6bdeb-109">함수를 `LPTHREAD_START_ROUTINE` 지점은 콜백 함수 및 호스팅 응용 프로그램의 작성자가 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6bdeb-109">The function to which `LPTHREAD_START_ROUTINE` points is a callback function and must be implemented by the writer of the hosting application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6bdeb-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6bdeb-110">Requirements</span></span>  
 <span data-ttu-id="6bdeb-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6bdeb-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6bdeb-112">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6bdeb-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6bdeb-113">**라이브러리:** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="6bdeb-113">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="6bdeb-114">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6bdeb-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6bdeb-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6bdeb-115">See Also</span></span>  
 [<span data-ttu-id="6bdeb-116">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="6bdeb-116">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
