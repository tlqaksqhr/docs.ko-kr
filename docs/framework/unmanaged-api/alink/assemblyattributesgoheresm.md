---
title: AssemblyAttributesGoHereSM
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: AssemblyAttributesGoHereSM
api_location: alink.dll
api_type: COM
f1_keywords: AssemblyAttributesGoHereSM
helpviewer_keywords:
- AssemblyAttributesGoHereSM type
- Alink API, AssemblyAttributesGoHereSM type
ms.assetid: 4cf9bf39-1527-49e0-a0e9-55e7a018bf66
topic_type: apiref
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5a753d596d198f7645fc44c48de9c360e15cc269
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="assemblyattributesgoheresm"></a><span data-ttu-id="fa14f-102">AssemblyAttributesGoHereSM</span><span class="sxs-lookup"><span data-stu-id="fa14f-102">AssemblyAttributesGoHereSM</span></span>
<span data-ttu-id="fa14f-103">ALink에서 사용자 지정 특성 정보를 저장하는 자리 표시자로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa14f-103">Used by ALink as a placeholder to store information about custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa14f-104">구문</span><span class="sxs-lookup"><span data-stu-id="fa14f-104">Syntax</span></span>  
  
```  
AssemblyAttributeGoHereSM  
```  
  
## <a name="remarks"></a><span data-ttu-id="fa14f-105">설명</span><span class="sxs-lookup"><span data-stu-id="fa14f-105">Remarks</span></span>  
 <span data-ttu-id="fa14f-106">이 형식에 대한 참조는 소스에 어셈블리 사용자 지정 특성이 들어 있는 netmodule 내부에 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa14f-106">References to this type might be embedded inside netmodules whose sources contain assembly custom attributes.</span></span> <span data-ttu-id="fa14f-107">이러한 유형에 대한 참조가 포함된 netmodule 하나 이상에서 어셈블리 매니페스트를 빌드할 때 ALink에서는 이들 참조에 연결된 정보를 사용하여 실제 사용자 지정 특성을 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="fa14f-107">When building an assembly manifest from one or more netmodules that contain references to these types, ALink uses information attached to these references to emit real custom attributes.</span></span> <span data-ttu-id="fa14f-108">따라서 이 형식은 인스턴스화되지 않으며, 이에 대한 참조는 빌드 프로세스 부분으로만 사용되고 최종 어셈블리에서 도움이 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fa14f-108">As such, this type is never instantiated, and references to it are used only as part of the build process and serve no purpose in the final assembly.</span></span>  
  
 <span data-ttu-id="fa14f-109">이 형식에 대한 참조는 보안과 관련이 있고 다양한 용도로 사용되는 사용자 지정 특성을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fa14f-109">References to this type indicate custom attributes that are security related and multiple-use.</span></span>  
  
 <span data-ttu-id="fa14f-110">이러한 형식은 .NET Framework 내에서 "내부"로 표시되며 <xref:System.Runtime.CompilerServices>에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa14f-110">These types are marked "internal" within the .NET Framework, and are located in <xref:System.Runtime.CompilerServices>.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa14f-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fa14f-111">Requirements</span></span>  
 <span data-ttu-id="fa14f-112">mscorlib.dll</span><span class="sxs-lookup"><span data-stu-id="fa14f-112">mscorlib.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa14f-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fa14f-113">See Also</span></span>  
 [<span data-ttu-id="fa14f-114">AssemblyAttributesGoHere</span><span class="sxs-lookup"><span data-stu-id="fa14f-114">AssemblyAttributesGoHere</span></span>](../../../../docs/framework/unmanaged-api/alink/assemblyattributesgohere.md)  
 [<span data-ttu-id="fa14f-115">AssemblyAttributesGoHereM</span><span class="sxs-lookup"><span data-stu-id="fa14f-115">AssemblyAttributesGoHereM</span></span>](../../../../docs/framework/unmanaged-api/alink/assemblyattributesgoherem.md)  
 [<span data-ttu-id="fa14f-116">AssemblyAttributesGoHereS</span><span class="sxs-lookup"><span data-stu-id="fa14f-116">AssemblyAttributesGoHereS</span></span>](../../../../docs/framework/unmanaged-api/alink/assemblyattributesgoheres.md)
