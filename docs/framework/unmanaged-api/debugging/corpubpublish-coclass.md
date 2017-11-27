---
title: CorpubPublish Coclass
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorpubPublish Coclass
api_location: mscoree.dll
api_type: COM
f1_keywords: CorpubPublish
helpviewer_keywords: CorpubPublish coclass [.NET Framework debugging]
ms.assetid: 191015da-f54a-4bac-a28a-1de7ab3c3428
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3c1565c9321e64536139e02b239fbeb4247a58a3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="corpubpublish-coclass"></a><span data-ttu-id="2a307-102">CorpubPublish Coclass</span><span class="sxs-lookup"><span data-stu-id="2a307-102">CorpubPublish Coclass</span></span>
<span data-ttu-id="2a307-103">응용 프로그램 도메인 및 프로세스에 대한 정보를 게시하기 위한 인터페이스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2a307-103">Provides interfaces for publishing information about application domains and processes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a307-104">구문</span><span class="sxs-lookup"><span data-stu-id="2a307-104">Syntax</span></span>  
  
```  
coclass CorpubPublish {  
    [default] interface ICorPublish;  
    interface           ICorPublishProcess;  
    interface           ICorPublishAppDomain;  
    interface           ICorPublishProcessEnum;  
    interface           ICorPublishAppDomainEnum;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="2a307-105">인터페이스</span><span class="sxs-lookup"><span data-stu-id="2a307-105">Interfaces</span></span>  
  
|<span data-ttu-id="2a307-106">인터페이스</span><span class="sxs-lookup"><span data-stu-id="2a307-106">Interface</span></span>|<span data-ttu-id="2a307-107">설명</span><span class="sxs-lookup"><span data-stu-id="2a307-107">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="2a307-108">ICorPublish 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2a307-108">ICorPublish Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md)|<span data-ttu-id="2a307-109">해당 프로세스의 프로세스 및 응용 프로그램 도메인에 대 한 정보를 게시 하기 위한 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a307-109">Provides methods for publishing information about processes and the application domains in those processes.</span></span>|  
|[<span data-ttu-id="2a307-110">ICorPublishAppDomain 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2a307-110">ICorPublishAppDomain Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)|<span data-ttu-id="2a307-111">를 나타내고 프로세스에서 응용 프로그램 도메인에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a307-111">Represents, and provides information about, an application domain in a process.</span></span>|  
|[<span data-ttu-id="2a307-112">ICorPublishAppDomainEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2a307-112">ICorPublishAppDomainEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md)|<span data-ttu-id="2a307-113">프로세스 내에서 현재 존재 하는 응용 프로그램 도메인의 컬렉션을 이동 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a307-113">Provides methods that traverse a collection of application domains that currently exist within a process.</span></span>|  
|[<span data-ttu-id="2a307-114">ICorPublishProcess 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2a307-114">ICorPublishProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)|<span data-ttu-id="2a307-115">컴퓨터에서 실행 되는 프로세스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2a307-115">Represents a process that is running on a computer.</span></span>|  
|[<span data-ttu-id="2a307-116">ICorPublishProcessEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2a307-116">ICorPublishProcessEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md)|<span data-ttu-id="2a307-117">컴퓨터에서 실행 되는 프로세스의 컬렉션을 이동 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a307-117">Provides methods that traverse a collection of processes that are running on a computer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2a307-118">설명</span><span class="sxs-lookup"><span data-stu-id="2a307-118">Remarks</span></span>  
 <span data-ttu-id="2a307-119">일반적인 게시 시나리오에는 응용 프로그램 도메인 내의 컴퓨터에서 실행 되는 관리 되는 코드를 디버깅 하려는 개발자가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a307-119">A typical publishing scenario involves a developer who wants to debug managed code that is running on a computer within an application domain.</span></span> <span data-ttu-id="2a307-120">호스팅 환경에서 프로세스 내에서 둘 이상의 응용 프로그램 도메인을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a307-120">The hosting environment may be running more than one application domain within a process.</span></span> <span data-ttu-id="2a307-121">개발자의 모든 컴퓨터에서 실행 되는 프로세스를 나열 하는 그래픽 사용자 인터페이스 또는 다른 방법을 사용 하 고 특정 프로세스를 선택 하고자 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a307-121">The developer would like to use a graphical user interface or some other means to list all of the processes that are running on the computer, and pick a specific process.</span></span> <span data-ttu-id="2a307-122">관리 코드를 실행 하는 프로세스 내의 응용 프로그램 도메인의 모든 목록에 포함 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a307-122">The listing should include all of the application domains within processes that are running managed code.</span></span> <span data-ttu-id="2a307-123">다음 개발자 특정 응용 프로그램 도메인을 식별 하 고 해당 도메인에 디버거를 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a307-123">The developer can then identify the specific application domain and attach a debugger to that domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2a307-124">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2a307-124">Requirements</span></span>  
 <span data-ttu-id="2a307-125">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2a307-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a307-126">**헤더:** CorPub.idl</span><span class="sxs-lookup"><span data-stu-id="2a307-126">**Header:** CorPub.idl</span></span>  
  
 <span data-ttu-id="2a307-127">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2a307-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2a307-128">**.NET framework 버전:**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a307-128">**.NET Framework Versions:**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a307-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2a307-129">See Also</span></span>  
 [<span data-ttu-id="2a307-130">디버깅</span><span class="sxs-lookup"><span data-stu-id="2a307-130">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
