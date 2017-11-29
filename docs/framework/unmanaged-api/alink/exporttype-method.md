---
title: "ExportType 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink.ExportType
api_location: alink.dll
api_type: COM
f1_keywords: ExportType
helpviewer_keywords: ExportType method
ms.assetid: 91a7ce63-f5b8-4f16-b2c4-e1d0baa88944
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 3f7bd3991fa57f11674b7ef0b9b62d12376fa765
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="exporttype-method"></a><span data-ttu-id="d5b44-102">ExportType 메서드</span><span class="sxs-lookup"><span data-stu-id="d5b44-102">ExportType Method</span></span>
<span data-ttu-id="d5b44-103">형식을 내보낼 수 임을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5b44-103">Specifies that a type is exportable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5b44-104">구문</span><span class="sxs-lookup"><span data-stu-id="d5b44-104">Syntax</span></span>  
  
```  
HRESULT ExportType(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    mdTypeDef       TypeToken,  
    LPCWSTR         pszTypename,  
    DWORD           dwFlags,  
    mdExportedType* pType  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d5b44-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d5b44-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="d5b44-106">내보낼 어셈블리의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="d5b44-106">ID of the assembly to export from.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="d5b44-107">내보낼 수 있는 형식을 정의 하는 파일의 파일 토큰 또는 어셈블리 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="d5b44-107">File token or assembly ID of file that defines the exportable type.</span></span>  
  
 `TypeToken`  
 <span data-ttu-id="d5b44-108">내보낼 수 있도록 지정할 형식의 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="d5b44-108">Token of type to be made exportable.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="d5b44-109">내보낼 수 있도록 지정할 정규화 된 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d5b44-109">Fully qualified type name to be made exportable.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="d5b44-110">`ComType`와 같은 플래그 `tdPublic` 또는 `tdNested`합니다.</span><span class="sxs-lookup"><span data-stu-id="d5b44-110">`ComType` flags such as `tdPublic` or `tdNested`.</span></span> <span data-ttu-id="d5b44-111">이 매개 변수 전달 될 수 있습니다 [DefineExportedType 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d5b44-111">This parameter may be passed to [DefineExportedType Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
 `pType`  
 <span data-ttu-id="d5b44-112">내보낸된 형식에 대 한 토큰을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="d5b44-112">Receives token for exported type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d5b44-113">반환 값</span><span class="sxs-lookup"><span data-stu-id="d5b44-113">Return Value</span></span>  
 <span data-ttu-id="d5b44-114">메서드가 성공 하면 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5b44-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d5b44-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d5b44-115">Requirements</span></span>  
 <span data-ttu-id="d5b44-116">Alink.h 필요</span><span class="sxs-lookup"><span data-stu-id="d5b44-116">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5b44-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d5b44-117">See Also</span></span>  
 [<span data-ttu-id="d5b44-118">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d5b44-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="d5b44-119">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d5b44-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="d5b44-120">ALink API</span><span class="sxs-lookup"><span data-stu-id="d5b44-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
