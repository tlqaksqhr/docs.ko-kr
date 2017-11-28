---
title: "SYMLINEDELTA 구조체"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: SYMLINEDELTA
api_location: diasymreader.dll
api_type: COM
f1_keywords: SYMLINEDELTA
helpviewer_keywords: SYMLINEDELTA structure [.NET Framework debugging]
ms.assetid: 9634e995-d46d-4397-ab66-cc5781d11e4e
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: cbd83560516e946c03a0ea71cf79fe6d3396bacb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="symlinedelta-structure"></a><span data-ttu-id="d508c-102">SYMLINEDELTA 구조체</span><span class="sxs-lookup"><span data-stu-id="d508c-102">SYMLINEDELTA Structure</span></span>
<span data-ttu-id="d508c-103">편집한 이동 된 방법에 대 한 기호 처리기에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d508c-103">Provides information to the symbol handler about methods that were moved as a result of edits.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d508c-104">구문</span><span class="sxs-lookup"><span data-stu-id="d508c-104">Syntax</span></span>  
  
```  
typedef struct _SYMLINEDELTA  
    {  
        mdMethodDef  mdMethod;  
        INT32        delta;  
    } SYMLINEDELTA;  
```  
  
## <a name="members"></a><span data-ttu-id="d508c-105">멤버</span><span class="sxs-lookup"><span data-stu-id="d508c-105">Members</span></span>  
  
|<span data-ttu-id="d508c-106">멤버</span><span class="sxs-lookup"><span data-stu-id="d508c-106">Member</span></span>|<span data-ttu-id="d508c-107">설명</span><span class="sxs-lookup"><span data-stu-id="d508c-107">Description</span></span>|  
|------------|-----------------|  
|`mdMethod`|<span data-ttu-id="d508c-108">메서드의 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="d508c-108">The method's metadata token.</span></span>|  
|`delta`|<span data-ttu-id="d508c-109">메서드가 이동 된 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d508c-109">The number of lines the method was moved.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d508c-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d508c-110">Requirements</span></span>  
 <span data-ttu-id="d508c-111">**헤더:** CorSym.idl</span><span class="sxs-lookup"><span data-stu-id="d508c-111">**Header:** CorSym.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d508c-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d508c-112">See Also</span></span>  
 [<span data-ttu-id="d508c-113">진단 기호 저장소 구조체</span><span class="sxs-lookup"><span data-stu-id="d508c-113">Diagnostics Symbol Store Structures</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)
