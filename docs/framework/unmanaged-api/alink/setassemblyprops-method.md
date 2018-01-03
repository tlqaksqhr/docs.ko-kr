---
title: "SetAssemblyProps 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink.SetAssemblyProps
api_location: alink.dll
api_type: COM
f1_keywords: SetAssemblyProps
helpviewer_keywords: SetAssemblyProps method
ms.assetid: a3d7cf29-1414-49e6-8aae-9b3283c4f5f0
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ae13daab0352ad4367c7ad6e06d6c12af23c75bb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="setassemblyprops-method"></a><span data-ttu-id="610b2-102">SetAssemblyProps 메서드</span><span class="sxs-lookup"><span data-stu-id="610b2-102">SetAssemblyProps Method</span></span>
<span data-ttu-id="610b2-103">어셈블리 수준 속성을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="610b2-103">Assigns assembly-level properties.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="610b2-104">구문</span><span class="sxs-lookup"><span data-stu-id="610b2-104">Syntax</span></span>  
  
```  
HRESULT SetAssemblyProps(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    AssemblyOptions Option,  
    VARIANT         Value  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="610b2-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="610b2-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="610b2-106">어셈블리의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="610b2-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="610b2-107">속성을 정의 하는 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="610b2-107">File that defines the property.</span></span> <span data-ttu-id="610b2-108">경우 NULL이 될 수 `AssemblyID` 바인딩되지 않은 어셈블리를 나타내지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="610b2-108">Can be NULL if `AssemblyID` does not indicate an unbound netmodule.</span></span>  
  
 `Option`  
 <span data-ttu-id="610b2-109">수정할 수 있는 옵션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="610b2-109">Indicates the option to modify.</span></span>  
  
 `Value`  
 <span data-ttu-id="610b2-110">옵션의 새 값입니다.</span><span class="sxs-lookup"><span data-stu-id="610b2-110">New value of the option.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="610b2-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="610b2-111">Return Value</span></span>  
 <span data-ttu-id="610b2-112">메서드가 성공 하면 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="610b2-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="610b2-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="610b2-113">Requirements</span></span>  
 <span data-ttu-id="610b2-114">Alink.h가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="610b2-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="610b2-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="610b2-115">See Also</span></span>  
 [<span data-ttu-id="610b2-116">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="610b2-116">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="610b2-117">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="610b2-117">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="610b2-118">ALink API</span><span class="sxs-lookup"><span data-stu-id="610b2-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
