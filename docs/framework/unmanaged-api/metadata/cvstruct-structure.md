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
ms.openlocfilehash: 95c1aeb0cacef929e99e5121f29e2f69b320caec
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="cvstruct-structure"></a><span data-ttu-id="7c70e-102">CVStruct 구조체</span><span class="sxs-lookup"><span data-stu-id="7c70e-102">CVStruct Structure</span></span>
<span data-ttu-id="7c70e-103">모듈 또는 합성 이미지를 설치할 때 사용되는 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="7c70e-103">Contains information that is used when installing a module or a composite image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c70e-104">구문</span><span class="sxs-lookup"><span data-stu-id="7c70e-104">Syntax</span></span>  
  
```  
typedef struct {  
    short Major;  
    short Minor;  
    short Sub;  
    short Build;  
} CVStruct;  
```  
  
## <a name="members"></a><span data-ttu-id="7c70e-105">멤버</span><span class="sxs-lookup"><span data-stu-id="7c70e-105">Members</span></span>  
  
|<span data-ttu-id="7c70e-106">멤버</span><span class="sxs-lookup"><span data-stu-id="7c70e-106">Member</span></span>|<span data-ttu-id="7c70e-107">설명</span><span class="sxs-lookup"><span data-stu-id="7c70e-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="7c70e-108">주요함</span><span class="sxs-lookup"><span data-stu-id="7c70e-108">Major</span></span>|<span data-ttu-id="7c70e-109">주 버전 빌드 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="7c70e-109">Major version build number.</span></span>|  
|<span data-ttu-id="7c70e-110">사소함</span><span class="sxs-lookup"><span data-stu-id="7c70e-110">Minor</span></span>|<span data-ttu-id="7c70e-111">부 버전 빌드 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="7c70e-111">Minor version build number.</span></span>|  
|<span data-ttu-id="7c70e-112">Sub</span><span class="sxs-lookup"><span data-stu-id="7c70e-112">Sub</span></span>|<span data-ttu-id="7c70e-113">하위 빌드 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="7c70e-113">Sub-build number.</span></span>|  
|<span data-ttu-id="7c70e-114">빌드</span><span class="sxs-lookup"><span data-stu-id="7c70e-114">Build</span></span>|<span data-ttu-id="7c70e-115">빌드 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="7c70e-115">Build number.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7c70e-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7c70e-116">Requirements</span></span>  
 <span data-ttu-id="7c70e-117">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7c70e-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c70e-118">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="7c70e-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7c70e-119">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="7c70e-119">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7c70e-120">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c70e-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c70e-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7c70e-121">See Also</span></span>  
 [<span data-ttu-id="7c70e-122">메타 데이터 구조</span><span class="sxs-lookup"><span data-stu-id="7c70e-122">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
