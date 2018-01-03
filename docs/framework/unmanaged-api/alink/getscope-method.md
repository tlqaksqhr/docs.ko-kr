---
title: GetScope Method1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink.GetScope
api_location: alink.dll
api_type: COM
f1_keywords: GetScope
helpviewer_keywords: GetScope method
ms.assetid: e1555328-2c71-4ece-b357-9eb6d3a8efc4
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4cb51efc3f431dac4a10cc7582e2b43500ccba15
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="getscope-method1"></a><span data-ttu-id="5a536-102">GetScope Method1</span><span class="sxs-lookup"><span data-stu-id="5a536-102">GetScope Method1</span></span>
<span data-ttu-id="5a536-103">가져오기 범위를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5a536-103">Gets an import scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a536-104">구문</span><span class="sxs-lookup"><span data-stu-id="5a536-104">Syntax</span></span>  
  
```  
HRESULT GetScope(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    IMetaDataImport** ppImportScope  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5a536-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5a536-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="5a536-106">가져올 어셈블리의 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="5a536-106">Unique ID of assembly to import to.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="5a536-107">가져올 파일의 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="5a536-107">Unique ID of the file to import from.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="5a536-108">가져올 범위 0부터 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a536-108">Zero-based scope to import.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="5a536-109">수신 [IMetaDataImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) 범위에 대 한 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="5a536-109">Receives [IMetaDataImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interface for the scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5a536-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="5a536-110">Return Value</span></span>  
 <span data-ttu-id="5a536-111">메서드가 성공 하면 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a536-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5a536-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5a536-112">Requirements</span></span>  
 <span data-ttu-id="5a536-113">Alink.h 필요</span><span class="sxs-lookup"><span data-stu-id="5a536-113">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a536-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5a536-114">See Also</span></span>  
 [<span data-ttu-id="5a536-115">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5a536-115">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="5a536-116">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5a536-116">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="5a536-117">ALink API</span><span class="sxs-lookup"><span data-stu-id="5a536-117">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
