---
title: "Init 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink.Init
api_location: alink.dll
api_type: COM
f1_keywords: Init
helpviewer_keywords: Init method
ms.assetid: e48b5c64-049f-4f93-ad87-d07ae9cd5845
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 999f572d27f75094ecc72c59acee7d35f86d5342
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="init-method"></a><span data-ttu-id="fdc6f-102">Init 메서드</span><span class="sxs-lookup"><span data-stu-id="fdc6f-102">Init Method</span></span>
<span data-ttu-id="fdc6f-103">구현 하는 개체를 준비는 [IALink 인터페이스](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md) 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdc6f-103">Prepares objects implementing the [IALink Interface](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md) for use.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fdc6f-104">구문</span><span class="sxs-lookup"><span data-stu-id="fdc6f-104">Syntax</span></span>  
  
```  
HRESULT Init(  
    IMetaDataDispenserEx* pDispenser,  
    IMetaDataError* pErrorHandler  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fdc6f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="fdc6f-105">Parameters</span></span>  
 `pDispenser`  
 <span data-ttu-id="fdc6f-106">[IMetaDataDispenserEx 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md) 메타 데이터 디스펜서에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="fdc6f-106">[IMetaDataDispenserEx Interface](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md) pointer to the metadata dispenser.</span></span>  
  
 `pErrorHandler`  
 <span data-ttu-id="fdc6f-107">[IMetaDataError 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-interface.md) 인터페이스를 처리 하는 선택적 오류에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="fdc6f-107">[IMetaDataError Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-interface.md) pointer to an optional error handling interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fdc6f-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="fdc6f-108">Return Value</span></span>  
 <span data-ttu-id="fdc6f-109">메서드가 성공 하면 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdc6f-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fdc6f-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fdc6f-110">Requirements</span></span>  
 <span data-ttu-id="fdc6f-111">Alink.h 필요</span><span class="sxs-lookup"><span data-stu-id="fdc6f-111">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdc6f-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fdc6f-112">See Also</span></span>  
 [<span data-ttu-id="fdc6f-113">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fdc6f-113">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="fdc6f-114">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fdc6f-114">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="fdc6f-115">ALink API</span><span class="sxs-lookup"><span data-stu-id="fdc6f-115">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
