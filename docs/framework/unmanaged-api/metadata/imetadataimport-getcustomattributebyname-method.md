---
title: IMetaDataImport::GetCustomAttributeByName 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetCustomAttributeByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetCustomAttributeByName
helpviewer_keywords:
- IMetaDataImport::GetCustomAttributeByName method [.NET Framework metadata]
- GetCustomAttributeByName method [.NET Framework metadata]
ms.assetid: 909aa530-2e3b-4d0a-a38a-a2750e535d7d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c25304bef4d240eedea749bb2829595056f9b74d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33449249"
---
# <a name="imetadataimportgetcustomattributebyname-method"></a><span data-ttu-id="42e22-102">IMetaDataImport::GetCustomAttributeByName 메서드</span><span class="sxs-lookup"><span data-stu-id="42e22-102">IMetaDataImport::GetCustomAttributeByName Method</span></span>
<span data-ttu-id="42e22-103">지정 된 이름 및 소유자 사용자 지정 특성을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="42e22-103">Gets the custom attribute, given its name and owner.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42e22-104">구문</span><span class="sxs-lookup"><span data-stu-id="42e22-104">Syntax</span></span>  
  
```  
HRESULT GetCustomAttributeByName (  
   [in]  mdToken          tkObj,  
   [in]  LPCWSTR          szName,  
   [out] const void       **ppData,  
   [out] ULONG            *pcbData  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="42e22-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="42e22-105">Parameters</span></span>  
 `tkObj`  
 <span data-ttu-id="42e22-106">[in] 사용자 지정 특성을 소유 하 고 개체를 나타내는 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="42e22-106">[in] A metadata token representing the object that owns the custom attribute.</span></span>  
  
 `szName`  
 <span data-ttu-id="42e22-107">[in] 사용자 지정 특성의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="42e22-107">[in] The name of the custom attribute.</span></span>  
  
 `ppData`  
 <span data-ttu-id="42e22-108">[out] 사용자 지정 특성의 값인 데이터 배열에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="42e22-108">[out] A pointer to an array of data that is the value of the custom attribute.</span></span>  
  
 `pcbData`  
 <span data-ttu-id="42e22-109">[out] 반환 되는 데이터의 바이트 크기 \*`ppData`합니다.</span><span class="sxs-lookup"><span data-stu-id="42e22-109">[out] The size in bytes of the data returned in \*`ppData`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="42e22-110">설명</span><span class="sxs-lookup"><span data-stu-id="42e22-110">Remarks</span></span>  
 <span data-ttu-id="42e22-111">같은 소유자;에 대 한 여러 사용자 지정 특성을 정의할 수 동일한 이름을 가지도 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42e22-111">It is legal to define multiple custom attributes for the same owner; they may even have the same name.</span></span> <span data-ttu-id="42e22-112">그러나 `GetCustomAttributeByName` 하나의 인스턴스를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="42e22-112">However, `GetCustomAttributeByName` returns only one instance.</span></span> <span data-ttu-id="42e22-113">(`GetCustomAttributeByName` 발견 되는 첫 번째 인스턴스를 반환 합니다.) 사용자 지정 특성의 모든 인스턴스를 찾으려면 호출는 [imetadataimport:: Enumcustomattributes](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumcustomattributes-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="42e22-113">(`GetCustomAttributeByName` returns the first instance that it encounters.) To find all instances of a custom attribute, call the [IMetaDataImport::EnumCustomAttributes](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumcustomattributes-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42e22-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="42e22-114">Requirements</span></span>  
 <span data-ttu-id="42e22-115">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="42e22-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42e22-116">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="42e22-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="42e22-117">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="42e22-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="42e22-118">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42e22-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42e22-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="42e22-119">See Also</span></span>  
 [<span data-ttu-id="42e22-120">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="42e22-120">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="42e22-121">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="42e22-121">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
