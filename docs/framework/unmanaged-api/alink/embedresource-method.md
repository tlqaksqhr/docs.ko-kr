---
title: "EmbedResource 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IALink.EmbedResource
- EmbedResource
api_location: alink.dll
api_type: COM
f1_keywords: EmbedResource
helpviewer_keywords: EmbedResource method
ms.assetid: 667bd954-6dc6-4020-a3cb-0e8224179993
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 98dbd32452184bf4f832bd66ffebb0fcf3d5bb0b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="embedresource-method"></a><span data-ttu-id="1007a-102">EmbedResource 메서드</span><span class="sxs-lookup"><span data-stu-id="1007a-102">EmbedResource Method</span></span>
<span data-ttu-id="1007a-103">포함된 된 리소스를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="1007a-103">Declares an embedded resource.</span></span> <span data-ttu-id="1007a-104">이 메서드는 리소스를 실제로 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1007a-104">This method does not actually embed the resource.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1007a-105">구문</span><span class="sxs-lookup"><span data-stu-id="1007a-105">Syntax</span></span>  
  
```  
HRESULT EmbedResource(  
    mdAssembly  AssemblyID,  
    mdToken     FileToken,  
    LPCWSTR     pszResourceName,  
    DWORD       dwOffset,  
    DWORD       dwFlags  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1007a-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1007a-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="1007a-107">어셈블리의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="1007a-107">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="1007a-108">리소스를 포함 하는 파일의 파일 토큰 또는 어셈블리 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="1007a-108">File token or assembly ID of file that contains the resource.</span></span>  
  
 `pszResourceName`  
 <span data-ttu-id="1007a-109">리소스의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="1007a-109">Name of the resource.</span></span>  
  
 `dwOffset`  
 <span data-ttu-id="1007a-110">RVA에서 리소스의 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="1007a-110">Offset of resource from RVA.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="1007a-111">내게 필요한 옵션 플래그와 같은 `mrPublic` 및 `mrPrivate`합니다.</span><span class="sxs-lookup"><span data-stu-id="1007a-111">Accessibility flags such as `mrPublic` and `mrPrivate`.</span></span> <span data-ttu-id="1007a-112">이러한 플래그에 전달할 수 있습니다 [DefineExportedType 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1007a-112">These flags may be passed to [DefineExportedType Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1007a-113">반환 값</span><span class="sxs-lookup"><span data-stu-id="1007a-113">Return Value</span></span>  
 <span data-ttu-id="1007a-114">메서드가 성공 하면 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="1007a-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1007a-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1007a-115">Requirements</span></span>  
 <span data-ttu-id="1007a-116">Alink.h가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="1007a-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1007a-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1007a-117">See Also</span></span>  
 [<span data-ttu-id="1007a-118">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1007a-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="1007a-119">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1007a-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="1007a-120">ALink API</span><span class="sxs-lookup"><span data-stu-id="1007a-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
