---
title: "GetALinkMessageDll 함수"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- GetALinkMessageDll
api_location:
- alink.dll
api_type:
- DLLExport
f1_keywords:
- GetALinkMessageDll
helpviewer_keywords:
- Alink API, GetALinkMessageDll function
- GetALinkMessageDll function
ms.assetid: 67985a22-88a2-4c54-8d99-4bcde9d6213e
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 16657c62d66db1570ad379ff5d42a75aaf3ea2a7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="getalinkmessagedll-function"></a><span data-ttu-id="79ef9-102">GetALinkMessageDll 함수</span><span class="sxs-lookup"><span data-stu-id="79ef9-102">GetALinkMessageDll Function</span></span>
<span data-ttu-id="79ef9-103">찾아서 메시지 DLL을 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="79ef9-103">Finds and loads the message DLL.</span></span> <span data-ttu-id="79ef9-104">0을 반환 메시지 DLL 찾거나 로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="79ef9-104">Returns 0 if the message DLL could not be located or loaded.</span></span> <span data-ttu-id="79ef9-105">메시지 DLL 이름이 언어 ID, 하위 디렉터리 또는 현재 디렉터리에 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="79ef9-105">The message DLL should be either in a subdirectory whose name is a language ID, or in the current directory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79ef9-106">구문</span><span class="sxs-lookup"><span data-stu-id="79ef9-106">Syntax</span></span>  
  
```  
HINSTANCE WINAPI GetALinkMessageDll();  
```  
  
## <a name="requirements"></a><span data-ttu-id="79ef9-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="79ef9-107">Requirements</span></span>  
 <span data-ttu-id="79ef9-108">**헤더:** alink.h</span><span class="sxs-lookup"><span data-stu-id="79ef9-108">**Header:** alink.h</span></span>  
  
 <span data-ttu-id="79ef9-109">**라이브러리**: alink.dll</span><span class="sxs-lookup"><span data-stu-id="79ef9-109">**Library**: alink.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79ef9-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="79ef9-110">See Also</span></span>  
 [<span data-ttu-id="79ef9-111">Al.exe(어셈블리 링커)</span><span class="sxs-lookup"><span data-stu-id="79ef9-111">Al.exe (Assembly Linker)</span></span>](../../../../docs/framework/tools/al-exe-assembly-linker.md)
