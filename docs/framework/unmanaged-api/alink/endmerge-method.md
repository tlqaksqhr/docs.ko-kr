---
title: "EndMerge 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IALink.EndMerge
- EndMerge
api_location: alink.dll
api_type: COM
f1_keywords: EndMerge
helpviewer_keywords: EndMerge method
ms.assetid: 1d03bb15-a2c8-4a04-8fc6-b126c89c3778
topic_type: apiref
caps.latest.revision: "5"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 7f29abf03c636fc552fe550534ca1b1395b43aae
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="endmerge-method"></a><span data-ttu-id="071e3-102">EndMerge 메서드</span><span class="sxs-lookup"><span data-stu-id="071e3-102">EndMerge Method</span></span>
<span data-ttu-id="071e3-103">모든 사용자 지정 특성 내보내기 범위에 병합 된 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="071e3-103">Indicates that all custom attributes have been merged into the emit scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="071e3-104">구문</span><span class="sxs-lookup"><span data-stu-id="071e3-104">Syntax</span></span>  
  
```  
HRESULT EndMerge(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="071e3-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="071e3-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="071e3-106">어셈블리의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="071e3-106">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="071e3-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="071e3-107">Return Value</span></span>  
 <span data-ttu-id="071e3-108">메서드가 성공 하면 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="071e3-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="071e3-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="071e3-109">Requirements</span></span>  
 <span data-ttu-id="071e3-110">Alink.h 필요</span><span class="sxs-lookup"><span data-stu-id="071e3-110">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="071e3-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="071e3-111">See Also</span></span>  
 [<span data-ttu-id="071e3-112">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="071e3-112">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="071e3-113">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="071e3-113">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="071e3-114">ALink API</span><span class="sxs-lookup"><span data-stu-id="071e3-114">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
