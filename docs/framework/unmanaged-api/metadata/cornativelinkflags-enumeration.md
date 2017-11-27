---
title: "CorNativeLinkFlags 열거형"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorNativeLinkFlags
api_location: mscoree.dll
api_type: COM
f1_keywords: CorNativeLinkFlags
helpviewer_keywords: CorNativeLinkFlags enumeration [.NET Framework metadata]
ms.assetid: 8027df7c-cfad-4724-bda0-7538d9519070
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 09afda63959d974af71e0264ad116c20d3af1923
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="cornativelinkflags-enumeration"></a><span data-ttu-id="ee39e-102">CorNativeLinkFlags 열거형</span><span class="sxs-lookup"><span data-stu-id="ee39e-102">CorNativeLinkFlags Enumeration</span></span>
<span data-ttu-id="ee39e-103">네이티브 코드를 연결할 때 링커에서 사용하는 플래그 값을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ee39e-103">Provides flag values used by the linker when linking native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee39e-104">구문</span><span class="sxs-lookup"><span data-stu-id="ee39e-104">Syntax</span></span>  
  
```  
typedef enum  
{  
    nlfNone         = 0x00,  
    nlfLastError    = 0x01,  
    nlfNoMangle     = 0x02,  
    nlfMaxValue     = 0x03  
} CorNativeLinkFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="ee39e-105">멤버</span><span class="sxs-lookup"><span data-stu-id="ee39e-105">Members</span></span>  
  
|<span data-ttu-id="ee39e-106">멤버</span><span class="sxs-lookup"><span data-stu-id="ee39e-106">Member</span></span>|<span data-ttu-id="ee39e-107">설명</span><span class="sxs-lookup"><span data-stu-id="ee39e-107">Description</span></span>|  
|------------|-----------------|  
|`nlfNone`|<span data-ttu-id="ee39e-108">플래그가 없음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ee39e-108">Indicates no flags.</span></span>|  
|`nlfLastError`|<span data-ttu-id="ee39e-109">나타냅니다는 `setLastError` 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="ee39e-109">Indicates a `setLastError` keyword.</span></span>|  
|`nlfNoMangle`|<span data-ttu-id="ee39e-110">나타냅니다는 `nomangle` 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="ee39e-110">Indicates a `nomangle` keyword.</span></span>|  
|`nlfMaxValue`|<span data-ttu-id="ee39e-111">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ee39e-111">Not used.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ee39e-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ee39e-112">Requirements</span></span>  
 <span data-ttu-id="ee39e-113">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ee39e-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ee39e-114">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ee39e-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ee39e-115">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="ee39e-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ee39e-116">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ee39e-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee39e-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ee39e-117">See Also</span></span>  
 [<span data-ttu-id="ee39e-118">메타 데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="ee39e-118">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
