---
title: "CorThreadSafetyOptions 열거형"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorThreadSafetyOptions
api_location: mscoree.dll
api_type: COM
f1_keywords: CorThreadSafetyOptions
helpviewer_keywords: CorThreadSafetyOptions enumeration [.NET Framework metadata]
ms.assetid: dae07d9b-df51-488c-b17e-52d6e48217bd
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ccdd7fb2b97e98227a581b3b97783c2c47bcab1f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="corthreadsafetyoptions-enumeration"></a><span data-ttu-id="f2cd0-102">CorThreadSafetyOptions 열거형</span><span class="sxs-lookup"><span data-stu-id="f2cd0-102">CorThreadSafetyOptions Enumeration</span></span>
<span data-ttu-id="f2cd0-103">스레드 안정성 옵션을 선택하는 플래그를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f2cd0-103">Specifies flags to select options for thread safety.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2cd0-104">구문</span><span class="sxs-lookup"><span data-stu-id="f2cd0-104">Syntax</span></span>  
  
```  
typedef enum CorThreadSafetyOptions {  
    MDThreadSafetyDefault       = 0x00000000,  
    MDThreadSafetyOff           = 0x00000000,  
    MDThreadSafetyOn            = 0x00000001,  
} CorThreadSafetyOptions;  
```  
  
## <a name="members"></a><span data-ttu-id="f2cd0-105">멤버</span><span class="sxs-lookup"><span data-stu-id="f2cd0-105">Members</span></span>  
  
|<span data-ttu-id="f2cd0-106">멤버</span><span class="sxs-lookup"><span data-stu-id="f2cd0-106">Member</span></span>|<span data-ttu-id="f2cd0-107">설명</span><span class="sxs-lookup"><span data-stu-id="f2cd0-107">Description</span></span>|  
|------------|-----------------|  
|`MDThreadSatetyDefault`|<span data-ttu-id="f2cd0-108">기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="f2cd0-108">Default value.</span></span> <span data-ttu-id="f2cd0-109">`MDThreadSatetyOff`와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="f2cd0-109">Same as `MDThreadSatetyOff`.</span></span>|  
|`MDThreadSatetyOff`|<span data-ttu-id="f2cd0-110">판독기/작성기 잠금의 설정할 수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f2cd0-110">Indicates that a reader/writer lock cannot be set.</span></span>|  
|`MDThreadSatetyOn`|<span data-ttu-id="f2cd0-111">판독기/작성기 잠금을 설정할 수 있도록 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f2cd0-111">Indicates that a reader/writer lock can be set.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f2cd0-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f2cd0-112">Requirements</span></span>  
 <span data-ttu-id="f2cd0-113">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f2cd0-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2cd0-114">**헤더:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="f2cd0-114">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="f2cd0-115">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2cd0-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2cd0-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f2cd0-116">See Also</span></span>  
 [<span data-ttu-id="f2cd0-117">메타 데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="f2cd0-117">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
