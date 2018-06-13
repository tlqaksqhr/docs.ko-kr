---
title: CVStruct 구조체
ms.date: 03/30/2017
api_name:
- CVStruct
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CVStruct
helpviewer_keywords:
- CVStruct structure [.NET Framework metadata]
ms.assetid: e9e4e497-d5fb-464b-991c-3bdd824664fd
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 195f311d58f2169d715bb33986ee6e591622f377
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33445045"
---
# <a name="cvstruct-structure"></a><span data-ttu-id="fea45-102">CVStruct 구조체</span><span class="sxs-lookup"><span data-stu-id="fea45-102">CVStruct Structure</span></span>
<span data-ttu-id="fea45-103">모듈 또는 합성 이미지를 설치할 때 사용되는 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="fea45-103">Contains information that is used when installing a module or a composite image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fea45-104">구문</span><span class="sxs-lookup"><span data-stu-id="fea45-104">Syntax</span></span>  
  
```  
typedef struct {  
    short Major;  
    short Minor;  
    short Sub;  
    short Build;  
} CVStruct;  
```  
  
## <a name="members"></a><span data-ttu-id="fea45-105">멤버</span><span class="sxs-lookup"><span data-stu-id="fea45-105">Members</span></span>  
  
|<span data-ttu-id="fea45-106">멤버</span><span class="sxs-lookup"><span data-stu-id="fea45-106">Member</span></span>|<span data-ttu-id="fea45-107">설명</span><span class="sxs-lookup"><span data-stu-id="fea45-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="fea45-108">주요함</span><span class="sxs-lookup"><span data-stu-id="fea45-108">Major</span></span>|<span data-ttu-id="fea45-109">주 버전 빌드 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="fea45-109">Major version build number.</span></span>|  
|<span data-ttu-id="fea45-110">부</span><span class="sxs-lookup"><span data-stu-id="fea45-110">Minor</span></span>|<span data-ttu-id="fea45-111">부 버전 빌드 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="fea45-111">Minor version build number.</span></span>|  
|<span data-ttu-id="fea45-112">Sub</span><span class="sxs-lookup"><span data-stu-id="fea45-112">Sub</span></span>|<span data-ttu-id="fea45-113">하위 빌드 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="fea45-113">Sub-build number.</span></span>|  
|<span data-ttu-id="fea45-114">빌드</span><span class="sxs-lookup"><span data-stu-id="fea45-114">Build</span></span>|<span data-ttu-id="fea45-115">빌드 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="fea45-115">Build number.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fea45-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fea45-116">Requirements</span></span>  
 <span data-ttu-id="fea45-117">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fea45-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fea45-118">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="fea45-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fea45-119">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="fea45-119">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="fea45-120">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fea45-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fea45-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fea45-121">See Also</span></span>  
 [<span data-ttu-id="fea45-122">메타데이터 구조체</span><span class="sxs-lookup"><span data-stu-id="fea45-122">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
