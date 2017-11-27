---
title: "CorLinkerOptions 열거형"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorLinkerOptions
api_location: mscoree.dll
api_type: COM
f1_keywords: CorLinkerOptions
helpviewer_keywords: CorLinkerOptions enumeration [.NET Framework metadata]
ms.assetid: a656aad6-cc7e-4994-8251-004a6a45e18f
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 9d2eb081c7ef0b4feb414011d7246a1e2d6d8192
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="corlinkeroptions-enumeration"></a><span data-ttu-id="7af75-102">CorLinkerOptions 열거형</span><span class="sxs-lookup"><span data-stu-id="7af75-102">CorLinkerOptions Enumeration</span></span>
<span data-ttu-id="7af75-103">메타데이터 링커 옵션을 선택하는 플래그를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7af75-103">Specifies flags to select options for the metadata linker.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7af75-104">구문</span><span class="sxs-lookup"><span data-stu-id="7af75-104">Syntax</span></span>  
  
```  
typedef enum CorLinkerOptions {  
    MDAssembly          = 0x00000000,  
    MDNetModule         = 0x00000001,  
} CorLinkerOptions;  
```  
  
## <a name="members"></a><span data-ttu-id="7af75-105">멤버</span><span class="sxs-lookup"><span data-stu-id="7af75-105">Members</span></span>  
  
|<span data-ttu-id="7af75-106">멤버</span><span class="sxs-lookup"><span data-stu-id="7af75-106">Member</span></span>|<span data-ttu-id="7af75-107">설명</span><span class="sxs-lookup"><span data-stu-id="7af75-107">Description</span></span>|  
|------------|-----------------|  
|`MDAssembly`|<span data-ttu-id="7af75-108">전용 형식 및 전역 함수 유지 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7af75-108">The private types and global functions are not preserved.</span></span>|  
|`MDNetModule`|<span data-ttu-id="7af75-109">개인 형식 및 전역 함수는 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7af75-109">The private types and global functions are preserved.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7af75-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7af75-110">Requirements</span></span>  
 <span data-ttu-id="7af75-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7af75-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7af75-112">**헤더:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="7af75-112">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="7af75-113">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7af75-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7af75-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7af75-114">See Also</span></span>  
 [<span data-ttu-id="7af75-115">메타 데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="7af75-115">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
