---
title: "CreateALink 함수"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CreateALink
api_location: alink.dll
api_type: DLLExport
f1_keywords: CreateALink
helpviewer_keywords:
- CreateALink function
- Alink API, CreateALink function
ms.assetid: fc73bcb9-6af6-44d8-bc39-2f4400325dae
topic_type: apiref
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a102e9601f751ee8c7e325293e83467b1314ff41
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="createalink-function"></a><span data-ttu-id="a8de0-102">CreateALink 함수</span><span class="sxs-lookup"><span data-stu-id="a8de0-102">CreateALink Function</span></span>
<span data-ttu-id="a8de0-103">어셈블리 링커의 인스턴스를 만들고 지정된 된 인터페이스에 대 한 포인터를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8de0-103">Creates an instance of the Assembly Linker and sets a pointer to the specified interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8de0-104">구문</span><span class="sxs-lookup"><span data-stu-id="a8de0-104">Syntax</span></span>  
  
```  
HRESULT CreateALink (  
   REFIID riid,  
   IUnknown **ppInterface  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a8de0-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a8de0-105">Parameters</span></span>  
  
|<span data-ttu-id="a8de0-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a8de0-106">Parameter</span></span>|<span data-ttu-id="a8de0-107">설명</span><span class="sxs-lookup"><span data-stu-id="a8de0-107">Description</span></span>|  
|---------------|-----------------|  
|`riid`|<span data-ttu-id="a8de0-108">어셈블리 링커 인터페이스 중 하나의 물리적 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="a8de0-108">The physical name of one of the Assembly Linker interfaces.</span></span>|  
|`ppInterface`|<span data-ttu-id="a8de0-109">성공적으로 완료에 대 한 포인터를 포함 하는 위치는 `riid` 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="a8de0-109">The location that on successful completion contains a pointer to the `riid` interface.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a8de0-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a8de0-110">Requirements</span></span>  
 <span data-ttu-id="a8de0-111">**라이브러리**: alink.dll</span><span class="sxs-lookup"><span data-stu-id="a8de0-111">**Library**: alink.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8de0-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a8de0-112">See Also</span></span>  
 [<span data-ttu-id="a8de0-113">Al.exe(어셈블리 링커)</span><span class="sxs-lookup"><span data-stu-id="a8de0-113">Al.exe (Assembly Linker)</span></span>](../../../../docs/framework/tools/al-exe-assembly-linker.md)
