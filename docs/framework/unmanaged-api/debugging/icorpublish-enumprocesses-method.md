---
title: ICorPublish::EnumProcesses 메서드
ms.date: 03/30/2017
api_name:
- ICorPublish.EnumProcesses
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublish::EnumProcesses
helpviewer_keywords:
- ICorPublish::EnumProcesses method [.NET Framework debugging]
- EnumProcesses method [.NET Framework debugging]
ms.assetid: 4ae765f0-93b2-4b6f-aea1-7b0cf44e04a7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2779138a0999e34ad6424d76ddfebbcfdf611d58
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33422899"
---
# <a name="icorpublishenumprocesses-method"></a><span data-ttu-id="d4b95-102">ICorPublish::EnumProcesses 메서드</span><span class="sxs-lookup"><span data-stu-id="d4b95-102">ICorPublish::EnumProcesses Method</span></span>
<span data-ttu-id="d4b95-103">이 컴퓨터에서 실행 중인 관리 되는 프로세스에 대 한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d4b95-103">Gets an enumerator for the managed processes running on this computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4b95-104">구문</span><span class="sxs-lookup"><span data-stu-id="d4b95-104">Syntax</span></span>  
  
```  
HRESULT EnumProcesses (  
    [in] COR_PUB_ENUMPROCESS       Type,  
    [out] ICorPublishProcessEnum   **ppIEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d4b95-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d4b95-105">Parameters</span></span>  
 `Type`  
 <span data-ttu-id="d4b95-106">값은 [COR_PUB_ENUMPROCESS](../../../../docs/framework/unmanaged-api/debugging/cor-pub-enumprocess-enumeration.md) 검색할 프로세스의 유형을 지정 하는 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="d4b95-106">A value of the [COR_PUB_ENUMPROCESS](../../../../docs/framework/unmanaged-api/debugging/cor-pub-enumprocess-enumeration.md) enumeration that specifies the type of process to be retrieved.</span></span> <span data-ttu-id="d4b95-107">현재 버전에서 COR_PUB_MANAGEDONLY만 유효합니다.</span><span class="sxs-lookup"><span data-stu-id="d4b95-107">In the current version, only COR_PUB_MANAGEDONLY is valid.</span></span>  
  
 `ppIEnum`  
 <span data-ttu-id="d4b95-108">주소에 대 한 포인터는 [ICorPublishProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md) 인스턴스 프로세스의 열거자입니다.</span><span class="sxs-lookup"><span data-stu-id="d4b95-108">A pointer to the address of an [ICorPublishProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md) instance that is the enumerator of the processes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d4b95-109">설명</span><span class="sxs-lookup"><span data-stu-id="d4b95-109">Remarks</span></span>  
 <span data-ttu-id="d4b95-110">프로세스의 열거자의 컬렉션 때 실행 되 고 있는 프로세스의 스냅숏을 기반는 `EnumProcesses` 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4b95-110">The enumerator's collection of processes is based on a snapshot of the processes that are running when the `EnumProcesses` method is called.</span></span> <span data-ttu-id="d4b95-111">열거자를 종료 하기 전에 또는 후에 시작 하는 모든 프로세스에 포함 되지 것입니다 `EnumProcesses` 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4b95-111">The enumerator will not include any processes that terminate before or start after `EnumProcesses` is called.</span></span>  
  
 <span data-ttu-id="d4b95-112">`EnumProcesses` 이 메서드를 두 번 이상 호출할 수 있습니다 [ICorPublish](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md) 인스턴스 프로세스의 새로운 최신 컬렉션을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4b95-112">The `EnumProcesses` method may be called more than once on this [ICorPublish](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md) instance to create a new up-to-date collection of processes.</span></span> <span data-ttu-id="d4b95-113">기존 컬렉션의 후속 호출에 의해 적용 되지 것입니다는 `EnumProcesses` 메서드.</span><span class="sxs-lookup"><span data-stu-id="d4b95-113">Existing collections will not be affected by subsequent calls of the `EnumProcesses` method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4b95-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d4b95-114">Requirements</span></span>  
 <span data-ttu-id="d4b95-115">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d4b95-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d4b95-116">**헤더:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="d4b95-116">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="d4b95-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d4b95-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d4b95-118">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d4b95-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4b95-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d4b95-119">See Also</span></span>  
 [<span data-ttu-id="d4b95-120">ICorPublish 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d4b95-120">ICorPublish Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md)
