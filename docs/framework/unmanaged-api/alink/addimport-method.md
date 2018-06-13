---
title: AddImport Method1
ms.date: 03/30/2017
api_name:
- AddImport
- IALink.AddImport
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- AddImport
helpviewer_keywords:
- AddImport method
ms.assetid: 4fedf8a0-08c8-43d0-aa00-20f2a521c991
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 98fefc0240f6496a3e7bfb491e27a57e98cfea1c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33404068"
---
# <a name="addimport-method1"></a><span data-ttu-id="b04b9-102">AddImport Method1</span><span class="sxs-lookup"><span data-stu-id="b04b9-102">AddImport Method1</span></span>
<span data-ttu-id="b04b9-103">Imports 어셈블리에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="b04b9-103">Adds imports to the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b04b9-104">구문</span><span class="sxs-lookup"><span data-stu-id="b04b9-104">Syntax</span></span>  
  
```  
HRESULT AddImport(  
    mdAssembly      AssemblyID,  
    mdToken         ImportToken,  
    DWORD           dwFlags,  
    mdFile*         pFileToken  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b04b9-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b04b9-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="b04b9-106">확대할 어셈블리의 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b04b9-106">Unique ID of assembly to be augmented.</span></span>  
  
 `ImportToken`  
 <span data-ttu-id="b04b9-107">검색 된 고유 ID [ImportFile 메서드](../../../../docs/framework/unmanaged-api/alink/importfile-method.md), 파일을 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b04b9-107">Unique ID, retrieved from [ImportFile Method](../../../../docs/framework/unmanaged-api/alink/importfile-method.md), of file to be imported.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="b04b9-108">COM + FileDef 플래그와 같은 `ffContainsNoMetaData` 및 `ffWriteable`합니다.</span><span class="sxs-lookup"><span data-stu-id="b04b9-108">COM+ FileDef flags such as `ffContainsNoMetaData` and `ffWriteable`.</span></span> <span data-ttu-id="b04b9-109">`dwFlags` 에 전달 [DefineFile 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b04b9-109">`dwFlags` is passed to [DefineFile Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
 `pFileToken`  
 <span data-ttu-id="b04b9-110">결과 파일에 대 한 ID를 받는 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b04b9-110">Pointer to token that receives the ID for the resulting file.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b04b9-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="b04b9-111">Return Value</span></span>  
 <span data-ttu-id="b04b9-112">메서드가 성공 하면 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b04b9-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b04b9-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b04b9-113">Requirements</span></span>  
 <span data-ttu-id="b04b9-114">Alink.h 필요</span><span class="sxs-lookup"><span data-stu-id="b04b9-114">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b04b9-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b04b9-115">See Also</span></span>  
 [<span data-ttu-id="b04b9-116">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b04b9-116">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="b04b9-117">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b04b9-117">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="b04b9-118">ALink API</span><span class="sxs-lookup"><span data-stu-id="b04b9-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
