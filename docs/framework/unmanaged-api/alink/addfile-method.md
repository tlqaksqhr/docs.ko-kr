---
title: AddFile Method1
ms.date: 03/30/2017
api_name:
- IALink.AddFile
- AddFile
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- AddFile
helpviewer_keywords:
- AddFile method
ms.assetid: 9e707abb-f905-4568-9356-12aa21d1b11c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 57a350fadfa77fdad545ca7ccf2f63d28607c2ba
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33403922"
---
# <a name="addfile-method1"></a><span data-ttu-id="a4098-102">AddFile Method1</span><span class="sxs-lookup"><span data-stu-id="a4098-102">AddFile Method1</span></span>
<span data-ttu-id="a4098-103">어셈블리에 파일을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a4098-103">Adds files to the assembly.</span></span> <span data-ttu-id="a4098-104">바인딩되지 않은 모듈을 만드는 데 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4098-104">Can also be used to create unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4098-105">구문</span><span class="sxs-lookup"><span data-stu-id="a4098-105">Syntax</span></span>  
  
```  
HRESULT AddFile(  
    mdAssembly      AssemblyID,  
    LPCWSTR         pszFilename,  
    DWORD           dwFlags,  
    IMetaDataEmit*  pEmitter,  
    mdFile*         pFileToken  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a4098-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a4098-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="a4098-107">확대할 어셈블리의 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="a4098-107">Unique ID of the assembly to be augmented.</span></span>  
  
 `pszFilename`  
 <span data-ttu-id="a4098-108">추가할 파일의 정규화 된 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="a4098-108">Fully qualified name of file to be added.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="a4098-109">COM + FileDef 플래그와 같은 `ffContainsNoMetaData` 및 `ffWriteable`합니다.</span><span class="sxs-lookup"><span data-stu-id="a4098-109">COM+ FileDef flags such as `ffContainsNoMetaData` and `ffWriteable`.</span></span> <span data-ttu-id="a4098-110">`dwFlags` 에 전달 [DefineFile 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a4098-110">`dwFlags` is passed to [DefineFile Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="a4098-111">[IMetaDataEmit 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) 필요한 경우 메타 데이터를 내보내는 데 사용할 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="a4098-111">[IMetaDataEmit Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) interface to be used to emit metadata, if necessary.</span></span>  
  
 `pFileToken`  
 <span data-ttu-id="a4098-112">추가 된 파일의 고유 ID가 저장 될 위치에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a4098-112">Pointer to where the unique ID of the added file will be stored.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a4098-113">반환 값</span><span class="sxs-lookup"><span data-stu-id="a4098-113">Return Value</span></span>  
 <span data-ttu-id="a4098-114">메서드가 성공 하면 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4098-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a4098-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a4098-115">Requirements</span></span>  
 <span data-ttu-id="a4098-116">Alink.h가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a4098-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4098-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a4098-117">See Also</span></span>  
 [<span data-ttu-id="a4098-118">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a4098-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="a4098-119">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a4098-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="a4098-120">ALink API</span><span class="sxs-lookup"><span data-stu-id="a4098-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
