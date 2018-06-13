---
title: EmbedResource 메서드
ms.date: 03/30/2017
api_name:
- IALink.EmbedResource
- EmbedResource
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EmbedResource
helpviewer_keywords:
- EmbedResource method
ms.assetid: 667bd954-6dc6-4020-a3cb-0e8224179993
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: eb1fc266c8451953c8b6a9c686f4a1c1951966e3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33405400"
---
# <a name="embedresource-method"></a><span data-ttu-id="7b9b0-102">EmbedResource 메서드</span><span class="sxs-lookup"><span data-stu-id="7b9b0-102">EmbedResource Method</span></span>
<span data-ttu-id="7b9b0-103">포함된 된 리소스를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="7b9b0-103">Declares an embedded resource.</span></span> <span data-ttu-id="7b9b0-104">이 메서드는 리소스를 실제로 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7b9b0-104">This method does not actually embed the resource.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b9b0-105">구문</span><span class="sxs-lookup"><span data-stu-id="7b9b0-105">Syntax</span></span>  
  
```  
HRESULT EmbedResource(  
    mdAssembly  AssemblyID,  
    mdToken     FileToken,  
    LPCWSTR     pszResourceName,  
    DWORD       dwOffset,  
    DWORD       dwFlags  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7b9b0-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7b9b0-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="7b9b0-107">어셈블리의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="7b9b0-107">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="7b9b0-108">리소스를 포함 하는 파일의 파일 토큰 또는 어셈블리 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="7b9b0-108">File token or assembly ID of file that contains the resource.</span></span>  
  
 `pszResourceName`  
 <span data-ttu-id="7b9b0-109">리소스의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7b9b0-109">Name of the resource.</span></span>  
  
 `dwOffset`  
 <span data-ttu-id="7b9b0-110">RVA에서 리소스의 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="7b9b0-110">Offset of resource from RVA.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="7b9b0-111">내게 필요한 옵션 플래그와 같은 `mrPublic` 및 `mrPrivate`합니다.</span><span class="sxs-lookup"><span data-stu-id="7b9b0-111">Accessibility flags such as `mrPublic` and `mrPrivate`.</span></span> <span data-ttu-id="7b9b0-112">이러한 플래그에 전달할 수 있습니다 [DefineExportedType 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7b9b0-112">These flags may be passed to [DefineExportedType Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7b9b0-113">반환 값</span><span class="sxs-lookup"><span data-stu-id="7b9b0-113">Return Value</span></span>  
 <span data-ttu-id="7b9b0-114">메서드가 성공 하면 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b9b0-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b9b0-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7b9b0-115">Requirements</span></span>  
 <span data-ttu-id="7b9b0-116">Alink.h가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="7b9b0-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b9b0-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7b9b0-117">See Also</span></span>  
 [<span data-ttu-id="7b9b0-118">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7b9b0-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="7b9b0-119">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7b9b0-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="7b9b0-120">ALink API</span><span class="sxs-lookup"><span data-stu-id="7b9b0-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
