---
title: AddFile Method1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IALink.AddFile
- AddFile
api_location: alink.dll
api_type: COM
f1_keywords: AddFile
helpviewer_keywords: AddFile method
ms.assetid: 9e707abb-f905-4568-9356-12aa21d1b11c
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 9463f2c41f56287ebfc4fb55aa8208c37522a57f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="addfile-method1"></a><span data-ttu-id="26abd-102">AddFile Method1</span><span class="sxs-lookup"><span data-stu-id="26abd-102">AddFile Method1</span></span>
<span data-ttu-id="26abd-103">어셈블리에 파일을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="26abd-103">Adds files to the assembly.</span></span> <span data-ttu-id="26abd-104">바인딩되지 않은 모듈을 만드는 데 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26abd-104">Can also be used to create unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26abd-105">구문</span><span class="sxs-lookup"><span data-stu-id="26abd-105">Syntax</span></span>  
  
```  
HRESULT AddFile(  
    mdAssembly      AssemblyID,  
    LPCWSTR         pszFilename,  
    DWORD           dwFlags,  
    IMetaDataEmit*  pEmitter,  
    mdFile*         pFileToken  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="26abd-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="26abd-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="26abd-107">확대할 어셈블리의 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="26abd-107">Unique ID of the assembly to be augmented.</span></span>  
  
 `pszFilename`  
 <span data-ttu-id="26abd-108">추가할 파일의 정규화 된 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="26abd-108">Fully qualified name of file to be added.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="26abd-109">COM + FileDef 플래그와 같은 `ffContainsNoMetaData` 및 `ffWriteable`합니다.</span><span class="sxs-lookup"><span data-stu-id="26abd-109">COM+ FileDef flags such as `ffContainsNoMetaData` and `ffWriteable`.</span></span> <span data-ttu-id="26abd-110">`dwFlags`에 전달 [DefineFile 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="26abd-110">`dwFlags` is passed to [DefineFile Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="26abd-111">[IMetaDataEmit 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) 필요한 경우 메타 데이터를 내보내는 데 사용할 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="26abd-111">[IMetaDataEmit Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) interface to be used to emit metadata, if necessary.</span></span>  
  
 `pFileToken`  
 <span data-ttu-id="26abd-112">추가 된 파일의 고유 ID가 저장 될 위치에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="26abd-112">Pointer to where the unique ID of the added file will be stored.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="26abd-113">반환 값</span><span class="sxs-lookup"><span data-stu-id="26abd-113">Return Value</span></span>  
 <span data-ttu-id="26abd-114">메서드가 성공 하면 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="26abd-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="26abd-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="26abd-115">Requirements</span></span>  
 <span data-ttu-id="26abd-116">Alink.h가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="26abd-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26abd-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="26abd-117">See Also</span></span>  
 [<span data-ttu-id="26abd-118">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="26abd-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="26abd-119">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="26abd-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="26abd-120">ALink API</span><span class="sxs-lookup"><span data-stu-id="26abd-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
