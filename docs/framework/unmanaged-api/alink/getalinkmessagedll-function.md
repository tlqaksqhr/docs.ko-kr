---
title: GetALinkMessageDll 함수
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 395dc85ad638e8a790962a4aa38019612c360ce1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33402219"
---
# <a name="getalinkmessagedll-function"></a><span data-ttu-id="8ecc2-102">GetALinkMessageDll 함수</span><span class="sxs-lookup"><span data-stu-id="8ecc2-102">GetALinkMessageDll Function</span></span>
<span data-ttu-id="8ecc2-103">찾아서 메시지 DLL을 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ecc2-103">Finds and loads the message DLL.</span></span> <span data-ttu-id="8ecc2-104">0을 반환 메시지 DLL 찾거나 로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8ecc2-104">Returns 0 if the message DLL could not be located or loaded.</span></span> <span data-ttu-id="8ecc2-105">메시지 DLL 이름이 언어 ID, 하위 디렉터리 또는 현재 디렉터리에 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ecc2-105">The message DLL should be either in a subdirectory whose name is a language ID, or in the current directory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ecc2-106">구문</span><span class="sxs-lookup"><span data-stu-id="8ecc2-106">Syntax</span></span>  
  
```  
HINSTANCE WINAPI GetALinkMessageDll();  
```  
  
## <a name="requirements"></a><span data-ttu-id="8ecc2-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8ecc2-107">Requirements</span></span>  
 <span data-ttu-id="8ecc2-108">**헤더:** alink.h</span><span class="sxs-lookup"><span data-stu-id="8ecc2-108">**Header:** alink.h</span></span>  
  
 <span data-ttu-id="8ecc2-109">**라이브러리**: alink.dll</span><span class="sxs-lookup"><span data-stu-id="8ecc2-109">**Library**: alink.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ecc2-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8ecc2-110">See Also</span></span>  
 [<span data-ttu-id="8ecc2-111">Al.exe(어셈블리 링커)</span><span class="sxs-lookup"><span data-stu-id="8ecc2-111">Al.exe (Assembly Linker)</span></span>](../../../../docs/framework/tools/al-exe-assembly-linker.md)
