---
title: "CorPropertyAttr 열거형"
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
- CorPropertyAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorPropertyAttr
helpviewer_keywords:
- CorPropertyAttr enumeration [.NET Framework metadata]
ms.assetid: 58ac8202-854d-4efd-acfb-d2da8b446e12
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4470cd46653dd798718e5b3413dbc021a894138b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="corpropertyattr-enumeration"></a><span data-ttu-id="d19e5-102">CorPropertyAttr 열거형</span><span class="sxs-lookup"><span data-stu-id="d19e5-102">CorPropertyAttr Enumeration</span></span>
<span data-ttu-id="d19e5-103">속성의 메타데이터를 설명하는 값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="d19e5-103">Contains values that describe the metadata of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d19e5-104">구문</span><span class="sxs-lookup"><span data-stu-id="d19e5-104">Syntax</span></span>  
  
```  
typedef enum CorPropertyAttr {  
  
    prSpecialName           =   0x0200,   
    prReservedMask          =   0xf400,  
    prRTSpecialName         =   0x0400,  
    prHasDefault            =   0x1000,  
    prUnused                =   0xe9ff  
  
} CorPropertyAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="d19e5-105">멤버</span><span class="sxs-lookup"><span data-stu-id="d19e5-105">Members</span></span>  
  
|<span data-ttu-id="d19e5-106">멤버</span><span class="sxs-lookup"><span data-stu-id="d19e5-106">Member</span></span>|<span data-ttu-id="d19e5-107">설명</span><span class="sxs-lookup"><span data-stu-id="d19e5-107">Description</span></span>|  
|------------|-----------------|  
|`prSpecialName`|<span data-ttu-id="d19e5-108">속성이 특수 문자이 고 해당 이름을 설명 하 고 있음을 지정 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="d19e5-108">Specifies that the property is special, and that its name describes how.</span></span>|  
|`prReservedMask`|<span data-ttu-id="d19e5-109">공용 언어 런타임에서 내부 용도로 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d19e5-109">Reserved for internal use by the common language runtime.</span></span>|  
|`prRTSpecialName`|<span data-ttu-id="d19e5-110">공용 언어 런타임 메타 데이터 내부 Api 확인 하도록 지정 합니다 속성 이름의 인코딩입니다.</span><span class="sxs-lookup"><span data-stu-id="d19e5-110">Specifies that the common language runtime metadata internal APIs should check the encoding of the property name.</span></span>|  
|`prHasDefault`|<span data-ttu-id="d19e5-111">속성이 기본값을 갖도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d19e5-111">Specifies that the property has a default value.</span></span>|  
|`prUnused`|<span data-ttu-id="d19e5-112">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d19e5-112">Unused.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d19e5-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d19e5-113">Requirements</span></span>  
 <span data-ttu-id="d19e5-114">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d19e5-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d19e5-115">**헤더:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="d19e5-115">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="d19e5-116">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d19e5-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d19e5-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d19e5-117">See Also</span></span>  
 [<span data-ttu-id="d19e5-118">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="d19e5-118">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
