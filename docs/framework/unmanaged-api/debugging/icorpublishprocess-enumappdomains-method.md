---
title: ICorPublishProcess::EnumAppDomains 메서드
ms.date: 03/30/2017
api_name:
- ICorPublishProcess.EnumAppDomains
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess::EnumAppDomains
helpviewer_keywords:
- EnumAppDomains method [.NET Framework debugging]
- ICorPublishProcess::EnumAppDomains method [.NET Framework debugging]
ms.assetid: 7da621fc-e7d0-4c00-9439-5c93619d7414
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5492d4e1245c6c0ce5c1eb98d25168c5d69d123b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33423704"
---
# <a name="icorpublishprocessenumappdomains-method"></a><span data-ttu-id="6bccf-102">ICorPublishProcess::EnumAppDomains 메서드</span><span class="sxs-lookup"><span data-stu-id="6bccf-102">ICorPublishProcess::EnumAppDomains Method</span></span>
<span data-ttu-id="6bccf-103">이 참조 하는 프로세스에서 응용 프로그램 도메인에 대 한 열거자를 가져옵니다 [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6bccf-103">Gets an enumerator for the application domains in the process that is referenced by this [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6bccf-104">구문</span><span class="sxs-lookup"><span data-stu-id="6bccf-104">Syntax</span></span>  
  
```  
HRESULT EnumAppDomains (  
    [out] ICorPublishAppDomainEnum   **ppEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6bccf-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6bccf-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="6bccf-106">[out] 주소에 대 한 포인터는 [ICorPublishAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md) 이 프로세스의 응용 프로그램 도메인의 컬렉션을 반복할 수 있는 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="6bccf-106">[out] A pointer to the address of an [ICorPublishAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md) instance that allows iteration through the collection of application domains in this process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6bccf-107">설명</span><span class="sxs-lookup"><span data-stu-id="6bccf-107">Remarks</span></span>  
 <span data-ttu-id="6bccf-108">응용 프로그램 도메인 목록에 존재 하는 응용 프로그램 도메인의 스냅숏을 기반 때는 `EnumAppDomains` 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="6bccf-108">The list of application domains is based on a snapshot of the application domains that exist when the `EnumAppDomains` method is called.</span></span> <span data-ttu-id="6bccf-109">새로운 최신 목록을 만들려면이 메서드를 두 번 이상 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6bccf-109">This method may be called more than once to create a new up-to-date list.</span></span> <span data-ttu-id="6bccf-110">기존 목록이이 방법의 후속 호출에 의해 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6bccf-110">Existing lists will not be affected by subsequent calls of this method.</span></span>  
  
 <span data-ttu-id="6bccf-111">프로세스가 종료 된 경우 `EnumAppDomains` CORDBG_E_PROCESS_TERMINATED HRESULT 값와 함께 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="6bccf-111">If the process has been terminated, `EnumAppDomains` will fail with an HRESULT value of CORDBG_E_PROCESS_TERMINATED.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6bccf-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6bccf-112">Requirements</span></span>  
 <span data-ttu-id="6bccf-113">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6bccf-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6bccf-114">**헤더:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="6bccf-114">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="6bccf-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6bccf-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6bccf-116">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6bccf-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6bccf-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6bccf-117">See Also</span></span>  
 [<span data-ttu-id="6bccf-118">ICorPublishProcess 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6bccf-118">ICorPublishProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)
