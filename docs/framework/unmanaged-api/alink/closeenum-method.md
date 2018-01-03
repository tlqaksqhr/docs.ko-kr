---
title: "CloseEnum 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- CloseEnum
- IALink.CloseEnum
api_location: alink.dll
api_type: COM
f1_keywords: CloseEnum
helpviewer_keywords: CloseEnum method
ms.assetid: aa4a091e-13fe-4264-91de-e12f1c767c87
topic_type: apiref
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 89f5b7069af0bfdfd732ed1ab4935771a565a20f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="closeenum-method"></a><span data-ttu-id="ad242-102">CloseEnum 메서드</span><span class="sxs-lookup"><span data-stu-id="ad242-102">CloseEnum Method</span></span>
<span data-ttu-id="ad242-103">표시 된 열거형을 닫고 연결 된 리소스를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad242-103">Closes the indicated enumeration and frees associated resources.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad242-104">구문</span><span class="sxs-lookup"><span data-stu-id="ad242-104">Syntax</span></span>  
  
```  
HRESULT CloseEnum(  
    HALINKENUM hEnum  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ad242-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ad242-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="ad242-106">닫을 열거형의 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="ad242-106">Handle of enumeration to be closed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ad242-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="ad242-107">Return Value</span></span>  
 <span data-ttu-id="ad242-108">메서드가 성공 하면 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad242-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad242-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ad242-109">Requirements</span></span>  
 <span data-ttu-id="ad242-110">Alink.h 필요</span><span class="sxs-lookup"><span data-stu-id="ad242-110">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad242-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ad242-111">See Also</span></span>  
 [<span data-ttu-id="ad242-112">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ad242-112">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="ad242-113">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ad242-113">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="ad242-114">ALink API</span><span class="sxs-lookup"><span data-stu-id="ad242-114">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
