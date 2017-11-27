---
title: "GetAssemblyRefHash 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink.GetAssemblyRefHash
api_location: alink.dll
api_type: COM
f1_keywords: GetAssemblyRefHash
helpviewer_keywords: GetAssemblyRefHash method
ms.assetid: 091a18bd-e901-46f6-b999-74d71c8a7c41
topic_type: apiref
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 0a5987bac2a874b01a24732a7c78a926fad0e011
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="getassemblyrefhash-method"></a><span data-ttu-id="122a6-102">GetAssemblyRefHash 메서드</span><span class="sxs-lookup"><span data-stu-id="122a6-102">GetAssemblyRefHash Method</span></span>
<span data-ttu-id="122a6-103">지정된 된 어셈블리에 대 한 해시 blob를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="122a6-103">Retrieves a hash blob for a given assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="122a6-104">구문</span><span class="sxs-lookup"><span data-stu-id="122a6-104">Syntax</span></span>  
  
```  
HRESULT GetAssemblyRefHash(  
    mdToken FileToken,  
    const void** ppvHash,  
    DWORD* pcbHash  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="122a6-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="122a6-105">Parameters</span></span>  
 `FileToken`  
 <span data-ttu-id="122a6-106">해시는 참조 어셈블리의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="122a6-106">ID of assembly to which the hash will refer.</span></span>  
  
 `ppvHash`  
 <span data-ttu-id="122a6-107">결과 해시 blob를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="122a6-107">Receives the resulting hash blob.</span></span>  
  
 `pcbHash`  
 <span data-ttu-id="122a6-108">해시 blob의 바이트의 크기를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="122a6-108">Receives size, in bytes, of hash blob.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="122a6-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="122a6-109">Return Value</span></span>  
 <span data-ttu-id="122a6-110">메서드가 성공 하면 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="122a6-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="122a6-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="122a6-111">Requirements</span></span>  
 <span data-ttu-id="122a6-112">Alink.h 필요</span><span class="sxs-lookup"><span data-stu-id="122a6-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="122a6-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="122a6-113">See Also</span></span>  
 [<span data-ttu-id="122a6-114">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="122a6-114">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="122a6-115">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="122a6-115">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="122a6-116">ALink API</span><span class="sxs-lookup"><span data-stu-id="122a6-116">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
