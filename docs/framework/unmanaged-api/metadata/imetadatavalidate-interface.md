---
title: "IMetaDataValidate 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IMetaDataValidate
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataValidate
helpviewer_keywords:
- IMetaDataValidate interface [.NET Framework metadata]
ms.assetid: db98608a-e85c-4f50-9d7b-5f57a426ddb6
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 7d4b83817883879c253fee4718e60a593a337314
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadatavalidate-interface"></a><span data-ttu-id="8e3ca-102">IMetaDataValidate 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8e3ca-102">IMetaDataValidate Interface</span></span>
<span data-ttu-id="8e3ca-103">메타데이터 서명의 유효성을 검사할 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8e3ca-103">Provides methods to validate metadata signatures.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8e3ca-104">메서드</span><span class="sxs-lookup"><span data-stu-id="8e3ca-104">Methods</span></span>  
  
|<span data-ttu-id="8e3ca-105">메서드</span><span class="sxs-lookup"><span data-stu-id="8e3ca-105">Method</span></span>|<span data-ttu-id="8e3ca-106">설명</span><span class="sxs-lookup"><span data-stu-id="8e3ca-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8e3ca-107">ValidateMetaData 메서드</span><span class="sxs-lookup"><span data-stu-id="8e3ca-107">ValidateMetaData Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatavalidate-validatemetadata-method.md)|<span data-ttu-id="8e3ca-108">현재 메타데이터 범위에서 개체에 대한 메타데이터 서명의 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="8e3ca-108">Validates the metadata signatures of the objects in the current metadata scope.</span></span>|  
|[<span data-ttu-id="8e3ca-109">ValidatorInit 메서드</span><span class="sxs-lookup"><span data-stu-id="8e3ca-109">ValidatorInit Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatavalidate-validatorinit-method.md)|<span data-ttu-id="8e3ca-110">현재 메타데이터 범위에서 모듈 형식을 지정하는 플래그를 설정하고 유효성 검사 오류에 대한 지정된 콜백 메서드를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="8e3ca-110">Sets a flag that specifies the type of the module in the current metadata scope, and registers the specified callback method for validation errors.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8e3ca-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8e3ca-111">Requirements</span></span>  
 <span data-ttu-id="8e3ca-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8e3ca-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8e3ca-113">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="8e3ca-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8e3ca-114">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="8e3ca-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8e3ca-115">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8e3ca-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e3ca-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8e3ca-116">See Also</span></span>  
 [<span data-ttu-id="8e3ca-117">메타데이터 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8e3ca-117">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
