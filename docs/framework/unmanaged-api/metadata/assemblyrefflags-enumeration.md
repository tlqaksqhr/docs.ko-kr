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
ms.workload: dotnet
ms.openlocfilehash: 0a749a2f0016e7f2ea22c1d61c82f25ac78a9b9d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="assemblyrefflags-enumeration"></a><span data-ttu-id="df323-102">AssemblyRefFlags 열거형</span><span class="sxs-lookup"><span data-stu-id="df323-102">AssemblyRefFlags Enumeration</span></span>
<span data-ttu-id="df323-103">어셈블리 참조의 기능을 설명 하는 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="df323-103">Contains values that describe features of an assembly reference.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df323-104">구문</span><span class="sxs-lookup"><span data-stu-id="df323-104">Syntax</span></span>  
  
```  
typedef enum {  
    arfFullOriginator = 0x0001  
} AssemblyRefFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="df323-105">멤버</span><span class="sxs-lookup"><span data-stu-id="df323-105">Members</span></span>  
  
|<span data-ttu-id="df323-106">멤버</span><span class="sxs-lookup"><span data-stu-id="df323-106">Member</span></span>|<span data-ttu-id="df323-107">설명</span><span class="sxs-lookup"><span data-stu-id="df323-107">Description</span></span>|  
|------------|-----------------|  
|`arfFullOriginator`|<span data-ttu-id="df323-108">어셈블리 참조 어셈블리의 게시자에 대 한 전체, 해시 되지 않은 정보에 포함 되도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="df323-108">Specifies that the assembly reference contains full, unhashed information about the publisher of the assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="df323-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="df323-109">Requirements</span></span>  
 <span data-ttu-id="df323-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="df323-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df323-111">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="df323-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="df323-112">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="df323-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df323-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="df323-113">See Also</span></span>  
 [<span data-ttu-id="df323-114">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="df323-114">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)  
 [<span data-ttu-id="df323-115">IMetaDataAssemblyEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="df323-115">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)  
 [<span data-ttu-id="df323-116">DefineAssemblyRef 메서드</span><span class="sxs-lookup"><span data-stu-id="df323-116">DefineAssemblyRef Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md)
