---
title: "CVStruct 구조체"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CVStruct
api_location: mscoree.dll
api_type: COM
f1_keywords: CVStruct
helpviewer_keywords: CVStruct structure [.NET Framework metadata]
ms.assetid: e9e4e497-d5fb-464b-991c-3bdd824664fd
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2e0c9087b180b39185fbf66235b515b9742e69ca
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="cvstruct-structure"></a><span data-ttu-id="95e84-102">CVStruct 구조체</span><span class="sxs-lookup"><span data-stu-id="95e84-102">CVStruct Structure</span></span>
<span data-ttu-id="95e84-103">모듈 또는 합성 이미지를 설치할 때 사용되는 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="95e84-103">Contains information that is used when installing a module or a composite image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95e84-104">구문</span><span class="sxs-lookup"><span data-stu-id="95e84-104">Syntax</span></span>  
  
```  
typedef struct {  
    short Major;  
    short Minor;  
    short Sub;  
    short Build;  
} CVStruct;  
```  
  
## <a name="members"></a><span data-ttu-id="95e84-105">멤버</span><span class="sxs-lookup"><span data-stu-id="95e84-105">Members</span></span>  
  
|<span data-ttu-id="95e84-106">멤버</span><span class="sxs-lookup"><span data-stu-id="95e84-106">Member</span></span>|<span data-ttu-id="95e84-107">설명</span><span class="sxs-lookup"><span data-stu-id="95e84-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="95e84-108">주요함</span><span class="sxs-lookup"><span data-stu-id="95e84-108">Major</span></span>|<span data-ttu-id="95e84-109">주 버전 빌드 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="95e84-109">Major version build number.</span></span>|  
|<span data-ttu-id="95e84-110">부</span><span class="sxs-lookup"><span data-stu-id="95e84-110">Minor</span></span>|<span data-ttu-id="95e84-111">부 버전 빌드 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="95e84-111">Minor version build number.</span></span>|  
|<span data-ttu-id="95e84-112">Sub</span><span class="sxs-lookup"><span data-stu-id="95e84-112">Sub</span></span>|<span data-ttu-id="95e84-113">하위 빌드 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="95e84-113">Sub-build number.</span></span>|  
|<span data-ttu-id="95e84-114">빌드</span><span class="sxs-lookup"><span data-stu-id="95e84-114">Build</span></span>|<span data-ttu-id="95e84-115">빌드 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="95e84-115">Build number.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="95e84-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="95e84-116">Requirements</span></span>  
 <span data-ttu-id="95e84-117">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="95e84-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95e84-118">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="95e84-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="95e84-119">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="95e84-119">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="95e84-120">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95e84-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95e84-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="95e84-121">See Also</span></span>  
 [<span data-ttu-id="95e84-122">메타데이터 구조체</span><span class="sxs-lookup"><span data-stu-id="95e84-122">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
