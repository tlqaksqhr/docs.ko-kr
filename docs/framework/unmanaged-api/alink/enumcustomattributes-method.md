---
title: "EnumCustomAttributes 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- EnumCustomAttributes
- IALink.EnumCustomAttributes
api_location: alink.dll
api_type: COM
f1_keywords: EnumCustomAttributes
helpviewer_keywords: EnumCustomAttributes method
ms.assetid: 08dff60c-f01b-4050-8865-ea3f95361c9f
topic_type: apiref
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: febaba5155753e9d60a3708582f4f58bd7861ec7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="enumcustomattributes-method"></a><span data-ttu-id="dac18-102">EnumCustomAttributes 메서드</span><span class="sxs-lookup"><span data-stu-id="dac18-102">EnumCustomAttributes Method</span></span>
<span data-ttu-id="dac18-103">어셈블리 수준의 사용자 지정 특성을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="dac18-103">Retrieves assembly-level custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dac18-104">구문</span><span class="sxs-lookup"><span data-stu-id="dac18-104">Syntax</span></span>  
  
```  
HRESULT EnumCustomAttributes(  
    HALINKENUM hEnum,  
    mdToken tkType,  
    mdCustomAttribute rCustomValues[],  
    ULONG cMax,  
    ULONG* pcCustomValues  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="dac18-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="dac18-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="dac18-106">열거자의 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="dac18-106">Handle of enumerator.</span></span>  
  
 `tkType`  
 <span data-ttu-id="dac18-107">열거할 특성의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="dac18-107">Type of attributes to be enumerated.</span></span> <span data-ttu-id="dac18-108">사용 하 여 `mdTokenNill` 모든 특성에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="dac18-108">Use `mdTokenNill` for all attributes.</span></span>  
  
 `rCustomValues`  
 <span data-ttu-id="dac18-109">사용자 지정 특성 토큰을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="dac18-109">Receives custom attributes tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="dac18-110">크기를 지정 `rCustomValues` 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="dac18-110">Specifies size of `rCustomValues` array.</span></span>  
  
 `pcCustomValues`  
 <span data-ttu-id="dac18-111">필요에 따라 토큰 값의 개수를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="dac18-111">Optionally receives count of token values.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dac18-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="dac18-112">Return Value</span></span>  
 <span data-ttu-id="dac18-113">메서드가 성공 하면 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="dac18-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dac18-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="dac18-114">Requirements</span></span>  
 <span data-ttu-id="dac18-115">Alink.h 필요</span><span class="sxs-lookup"><span data-stu-id="dac18-115">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dac18-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dac18-116">See Also</span></span>  
 [<span data-ttu-id="dac18-117">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dac18-117">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="dac18-118">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dac18-118">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="dac18-119">ALink API</span><span class="sxs-lookup"><span data-stu-id="dac18-119">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
