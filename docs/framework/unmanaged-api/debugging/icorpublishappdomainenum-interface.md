---
title: ICorPublishAppDomainEnum 인터페이스
ms.date: 03/30/2017
api_name:
- ICorPublishAppDomainEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishAppDomainEnum
helpviewer_keywords:
- ICorPublishAppDomainEnum interface [.NET Framework debugging]
ms.assetid: bb798c56-042e-475d-a245-b6fac36d0c07
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 610f62274aea88c1d5f9bbe1456685aa1d3bca68
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33423743"
---
# <a name="icorpublishappdomainenum-interface"></a><span data-ttu-id="f7a71-102">ICorPublishAppDomainEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f7a71-102">ICorPublishAppDomainEnum Interface</span></span>
<span data-ttu-id="f7a71-103">서브 클래스는 [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) 의 컬렉션을 이동 하는 메서드를 제공 하는 인터페이스 [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md) 프로세스 내에서 현재 존재 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="f7a71-103">A subclass of the [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) interface that provides methods to traverse a collection of [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md) objects that currently exist within a process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f7a71-104">메서드</span><span class="sxs-lookup"><span data-stu-id="f7a71-104">Methods</span></span>  
  
|<span data-ttu-id="f7a71-105">메서드</span><span class="sxs-lookup"><span data-stu-id="f7a71-105">Method</span></span>|<span data-ttu-id="f7a71-106">설명</span><span class="sxs-lookup"><span data-stu-id="f7a71-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f7a71-107">Next 메서드</span><span class="sxs-lookup"><span data-stu-id="f7a71-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-next-method.md)|<span data-ttu-id="f7a71-108">지정된 된 수의 가져옵니다 `ICorPublishAppDomain` 현재 위치부터 시작 하 고 컬렉션에서 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="f7a71-108">Gets the specified number of `ICorPublishAppDomain` instances from the collection, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f7a71-109">설명</span><span class="sxs-lookup"><span data-stu-id="f7a71-109">Remarks</span></span>  
 <span data-ttu-id="f7a71-110">`ICorPublishAppDomainEnum` 추상 인터페이스의 메서드를 구현 하는 인터페이스 [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f7a71-110">The `ICorPublishAppDomainEnum` interface implements the methods of the abstract interface, [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f7a71-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f7a71-111">Requirements</span></span>  
 <span data-ttu-id="f7a71-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f7a71-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f7a71-113">**헤더:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="f7a71-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="f7a71-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f7a71-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f7a71-115">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f7a71-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7a71-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f7a71-116">See Also</span></span>  
 [<span data-ttu-id="f7a71-117">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f7a71-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="f7a71-118">CorpubPublish Coclass</span><span class="sxs-lookup"><span data-stu-id="f7a71-118">CorpubPublish Coclass</span></span>](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
