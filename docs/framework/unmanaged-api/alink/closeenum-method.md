---
title: CloseEnum 메서드
ms.date: 03/30/2017
api_name:
- CloseEnum
- IALink.CloseEnum
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- CloseEnum
helpviewer_keywords:
- CloseEnum method
ms.assetid: aa4a091e-13fe-4264-91de-e12f1c767c87
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e5c3185dc6d488223d5882f543f0c690d82261b5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33402446"
---
# <a name="closeenum-method"></a><span data-ttu-id="83c10-102">CloseEnum 메서드</span><span class="sxs-lookup"><span data-stu-id="83c10-102">CloseEnum Method</span></span>
<span data-ttu-id="83c10-103">표시 된 열거형을 닫고 연결 된 리소스를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="83c10-103">Closes the indicated enumeration and frees associated resources.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83c10-104">구문</span><span class="sxs-lookup"><span data-stu-id="83c10-104">Syntax</span></span>  
  
```  
HRESULT CloseEnum(  
    HALINKENUM hEnum  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="83c10-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="83c10-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="83c10-106">닫을 열거형의 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="83c10-106">Handle of enumeration to be closed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="83c10-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="83c10-107">Return Value</span></span>  
 <span data-ttu-id="83c10-108">메서드가 성공 하면 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="83c10-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83c10-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="83c10-109">Requirements</span></span>  
 <span data-ttu-id="83c10-110">Alink.h 필요</span><span class="sxs-lookup"><span data-stu-id="83c10-110">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83c10-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="83c10-111">See Also</span></span>  
 [<span data-ttu-id="83c10-112">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="83c10-112">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="83c10-113">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="83c10-113">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="83c10-114">ALink API</span><span class="sxs-lookup"><span data-stu-id="83c10-114">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
