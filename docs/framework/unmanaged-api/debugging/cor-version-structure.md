---
title: "COR_VERSION 구조체"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_VERSION
api_location: mscordbi.dll
api_type: COM
f1_keywords: COR_VERSION
helpviewer_keywords: COR_VERSION structure [.NET Framework debugging]
ms.assetid: 5efaee1c-a001-4c73-9525-4160f4c71567
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: bd4a878b51685befb39eb486097be2e2f2c1d409
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="corversion-structure"></a><span data-ttu-id="40adf-102">COR_VERSION 구조체</span><span class="sxs-lookup"><span data-stu-id="40adf-102">COR_VERSION Structure</span></span>
<span data-ttu-id="40adf-103">공용 언어 런타임의 4부분으로 구성된 표준 버전 번호를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="40adf-103">Stores the standard four-part version number of the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40adf-104">구문</span><span class="sxs-lookup"><span data-stu-id="40adf-104">Syntax</span></span>  
  
```  
typedef struct _COR_VERSION {  
    DWORD dwMajor;  
    DWORD dwMinor;  
    DWORD dwBuild;  
    DWORD dwSubBuild;  
} COR_VERSION;  
```  
  
## <a name="members"></a><span data-ttu-id="40adf-105">멤버</span><span class="sxs-lookup"><span data-stu-id="40adf-105">Members</span></span>  
  
|<span data-ttu-id="40adf-106">멤버</span><span class="sxs-lookup"><span data-stu-id="40adf-106">Member</span></span>|<span data-ttu-id="40adf-107">설명</span><span class="sxs-lookup"><span data-stu-id="40adf-107">Description</span></span>|  
|------------|-----------------|  
|`dwMajor`|<span data-ttu-id="40adf-108">주 버전 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="40adf-108">The major version number.</span></span>|  
|`dwMinor`|<span data-ttu-id="40adf-109">부 버전 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="40adf-109">The minor version number.</span></span>|  
|`dwBuild`|<span data-ttu-id="40adf-110">빌드 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="40adf-110">The build number.</span></span>|  
|`dwSubBuild`|<span data-ttu-id="40adf-111">하위 빌드 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="40adf-111">The sub-build number.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="40adf-112">설명</span><span class="sxs-lookup"><span data-stu-id="40adf-112">Remarks</span></span>  
 <span data-ttu-id="40adf-113">버전 번호가 1.0.3705.288 이면 1은 주 버전 번호, 0은 부 버전 번호, 3705는 빌드 번호 및 288는 하위 빌드 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="40adf-113">If the version number is 1.0.3705.288, 1 is the major version number, 0 is the minor version number, 3705 is the build number, and 288 is the sub-build number.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="40adf-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="40adf-114">Requirements</span></span>  
 <span data-ttu-id="40adf-115">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="40adf-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="40adf-116">**헤더:** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="40adf-116">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="40adf-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="40adf-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="40adf-118">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="40adf-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40adf-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="40adf-119">See Also</span></span>  
 [<span data-ttu-id="40adf-120">디버깅 구조체</span><span class="sxs-lookup"><span data-stu-id="40adf-120">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="40adf-121">디버깅</span><span class="sxs-lookup"><span data-stu-id="40adf-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
