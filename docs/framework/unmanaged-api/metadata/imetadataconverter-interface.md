---
title: "IMetaDataConverter 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataConverter
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataConverter
helpviewer_keywords: IMetaDataConverter interface [.NET Framework metadata]
ms.assetid: 9caea662-0167-4267-b14a-2fa42c3be4ea
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 758ea4261b859773c600ca91d52e3a9053776136
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataconverter-interface"></a><span data-ttu-id="be4e2-102">IMetaDataConverter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="be4e2-102">IMetaDataConverter Interface</span></span>
<span data-ttu-id="be4e2-103">형식 라이브러리를 메타데이터 서명에 매핑하고 서로 변환하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="be4e2-103">Provides methods to map type libraries to their metadata signatures, and to convert from one to the other.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="be4e2-104">메서드</span><span class="sxs-lookup"><span data-stu-id="be4e2-104">Methods</span></span>  
  
|<span data-ttu-id="be4e2-105">메서드</span><span class="sxs-lookup"><span data-stu-id="be4e2-105">Method</span></span>|<span data-ttu-id="be4e2-106">설명</span><span class="sxs-lookup"><span data-stu-id="be4e2-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="be4e2-107">GetMetaDataFromTypeInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="be4e2-107">GetMetaDataFromTypeInfo Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataconverter-getmetadatafromtypeinfo-method.md)|<span data-ttu-id="be4e2-108">에 대 한 포인터를 가져옵니다는 [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) 를 지정 된 참조 형식 라이브러리에 대 한 메타 데이터 서명을 나타내는 `ITypeInfo` 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="be4e2-108">Gets a pointer to an [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) instance that represents the metadata signature for the type library referenced by the specified `ITypeInfo` instance.</span></span>|  
|[<span data-ttu-id="be4e2-109">GetMetaDataFromTypeLib 메서드</span><span class="sxs-lookup"><span data-stu-id="be4e2-109">GetMetaDataFromTypeLib Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataconverter-getmetadatafromtypelib-method.md)|<span data-ttu-id="be4e2-110">에 대 한 포인터를 가져옵니다는 `IMetaDataImport` 를 지정 된 형식 라이브러리에 대 한 메타 데이터 서명을 나타내는 `ITypeLib` 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="be4e2-110">Gets a pointer to an `IMetaDataImport` instance that represents the metadata signature for the type library represented by the specified `ITypeLib` instance.</span></span>|  
|[<span data-ttu-id="be4e2-111">GetTypeLibFromMetaData 메서드</span><span class="sxs-lookup"><span data-stu-id="be4e2-111">GetTypeLibFromMetaData Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataconverter-gettypelibfrommetadata-method.md)|<span data-ttu-id="be4e2-112">에 대 한 포인터를 가져옵니다는 `ITypeLib` 모듈과 라이브러리 이름이 지정 된 형식 라이브러리를 나타내는 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="be4e2-112">Gets a pointer to an `ITypeLib` instance that represents the type library that has the specified module and library names.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="be4e2-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="be4e2-113">Requirements</span></span>  
 <span data-ttu-id="be4e2-114">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="be4e2-114">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="be4e2-115">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="be4e2-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="be4e2-116">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="be4e2-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="be4e2-117">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="be4e2-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be4e2-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="be4e2-118">See Also</span></span>  
 [<span data-ttu-id="be4e2-119">메타데이터 인터페이스</span><span class="sxs-lookup"><span data-stu-id="be4e2-119">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)  
 [<span data-ttu-id="be4e2-120">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="be4e2-120">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
