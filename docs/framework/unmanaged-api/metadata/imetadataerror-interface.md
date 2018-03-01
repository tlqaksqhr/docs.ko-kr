---
title: "IMetaDataError 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IMetaDataError
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataError
helpviewer_keywords:
- IMetaDataError interface [.NET Framework metadata]
ms.assetid: 0020b62c-ea88-40c7-a9ee-16b064f81624
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4df7aa7400a180151de5420effc8738955d51c26
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataerror-interface"></a><span data-ttu-id="25205-102">IMetaDataError 인터페이스</span><span class="sxs-lookup"><span data-stu-id="25205-102">IMetaDataError Interface</span></span>
<span data-ttu-id="25205-103">메타 데이터를 병합 하는 동안 오류를 보고 하는 콜백 메커니즘을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="25205-103">Provides a callback mechanism for reporting errors during the metadata merge.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="25205-104">`IMetaDataError` 클라이언트에서 인터페이스를 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="25205-104">The `IMetaDataError` interface must be implemented by the client.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="25205-105">메서드</span><span class="sxs-lookup"><span data-stu-id="25205-105">Methods</span></span>  
  
|<span data-ttu-id="25205-106">메서드</span><span class="sxs-lookup"><span data-stu-id="25205-106">Method</span></span>|<span data-ttu-id="25205-107">설명</span><span class="sxs-lookup"><span data-stu-id="25205-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="25205-108">OnError 메서드</span><span class="sxs-lookup"><span data-stu-id="25205-108">OnError Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-onerror-method.md)|<span data-ttu-id="25205-109">메타 데이터를 병합 하는 동안 발생 하는 오류에 대 한 알림을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="25205-109">Provides notification of errors that occur during the metadata merge.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="25205-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="25205-110">Requirements</span></span>  
 <span data-ttu-id="25205-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="25205-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="25205-112">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="25205-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="25205-113">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="25205-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="25205-114">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="25205-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25205-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="25205-115">See Also</span></span>  
 [<span data-ttu-id="25205-116">메타데이터 인터페이스</span><span class="sxs-lookup"><span data-stu-id="25205-116">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
