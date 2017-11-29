---
title: "AssemblyRefFlags 열거형"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: AssemblyRefFlags
api_location: mscoree.dll
api_type: COM
f1_keywords: AssemblyRefFlags
helpviewer_keywords: AssemblyRefFlags enumeration [.NET Framework metadata]
ms.assetid: decd4f46-f3b2-466f-9501-e74f2b86b846
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: fc64d03725df89eac91c85549e287eeb2510037c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="assemblyrefflags-enumeration"></a><span data-ttu-id="928ad-102">AssemblyRefFlags 열거형</span><span class="sxs-lookup"><span data-stu-id="928ad-102">AssemblyRefFlags Enumeration</span></span>
<span data-ttu-id="928ad-103">어셈블리 참조의 기능을 설명 하는 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="928ad-103">Contains values that describe features of an assembly reference.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="928ad-104">구문</span><span class="sxs-lookup"><span data-stu-id="928ad-104">Syntax</span></span>  
  
```  
typedef enum {  
    arfFullOriginator = 0x0001  
} AssemblyRefFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="928ad-105">멤버</span><span class="sxs-lookup"><span data-stu-id="928ad-105">Members</span></span>  
  
|<span data-ttu-id="928ad-106">멤버</span><span class="sxs-lookup"><span data-stu-id="928ad-106">Member</span></span>|<span data-ttu-id="928ad-107">설명</span><span class="sxs-lookup"><span data-stu-id="928ad-107">Description</span></span>|  
|------------|-----------------|  
|`arfFullOriginator`|<span data-ttu-id="928ad-108">어셈블리 참조 어셈블리의 게시자에 대 한 전체, 해시 되지 않은 정보에 포함 되도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="928ad-108">Specifies that the assembly reference contains full, unhashed information about the publisher of the assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="928ad-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="928ad-109">Requirements</span></span>  
 <span data-ttu-id="928ad-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="928ad-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="928ad-111">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="928ad-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="928ad-112">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="928ad-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="928ad-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="928ad-113">See Also</span></span>  
 [<span data-ttu-id="928ad-114">메타 데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="928ad-114">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)  
 [<span data-ttu-id="928ad-115">IMetaDataAssemblyEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="928ad-115">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)  
 [<span data-ttu-id="928ad-116">DefineAssemblyRef 메서드</span><span class="sxs-lookup"><span data-stu-id="928ad-116">DefineAssemblyRef Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md)
