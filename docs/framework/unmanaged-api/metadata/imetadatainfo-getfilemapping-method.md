---
title: IMetaDataInfo::GetFileMapping 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataInfo.GetFileMapping
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataInfo::GetFileMapping
helpviewer_keywords:
- IMetaDataInfo::GetFileMapping method [.NET Framework metadata]
- GetFileMapping method [.NET Framework metadata]
ms.assetid: 2868dfec-c992-4606-88bb-a8e0b6b18271
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 562b6fcd015441ce5eb6b5f0ab7a4f361bb229c3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33449431"
---
# <a name="imetadatainfogetfilemapping-method"></a><span data-ttu-id="fcac5-102">IMetaDataInfo::GetFileMapping 메서드</span><span class="sxs-lookup"><span data-stu-id="fcac5-102">IMetaDataInfo::GetFileMapping Method</span></span>
<span data-ttu-id="fcac5-103">매핑된 파일 및 형식 매핑의 메모리 영역을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="fcac5-103">Gets the memory region of the mapped file, and the type of mapping.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fcac5-104">구문</span><span class="sxs-lookup"><span data-stu-id="fcac5-104">Syntax</span></span>  
  
```  
HRESULT GetFileMapping (  
    [out] const void           **ppvData,   
    [out] ULONGLONG            *pcbData,   
    [out] DWORD                *pdwMappingType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fcac5-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="fcac5-105">Parameters</span></span>  
 `ppvData`  
 <span data-ttu-id="fcac5-106">[out] 매핑된 파일의 시작 부분에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="fcac5-106">[out] A pointer to the start of the mapped file.</span></span>  
  
 `pcbData`  
 <span data-ttu-id="fcac5-107">[out] 매핑된 영역의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="fcac5-107">[out] The size of the mapped region.</span></span> <span data-ttu-id="fcac5-108">경우 `pdwMappingType` 은 `fmFlat`, 파일의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="fcac5-108">If `pdwMappingType` is `fmFlat`, this is the size of the file.</span></span>  
  
 `pdwMappingType`  
 <span data-ttu-id="fcac5-109">[out] A [CorFileMapping](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md) 매핑 유형을 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="fcac5-109">[out] A [CorFileMapping](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md) value that indicates the type of mapping.</span></span> <span data-ttu-id="fcac5-110">공용 언어 런타임 (CLR)의 현재 구현은 항상 반환 `fmFlat`합니다.</span><span class="sxs-lookup"><span data-stu-id="fcac5-110">The current implementation of the common language runtime (CLR) always returns `fmFlat`.</span></span> <span data-ttu-id="fcac5-111">다른 값은 나중에 사용할 수는 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcac5-111">Other values are reserved for future use.</span></span> <span data-ttu-id="fcac5-112">그러나 다른 값 이후 버전에서 사용할 수 있습니다 또는 서비스 릴리스 때문에 반환된 된 값에 확인 해야 항상 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcac5-112">However, you should always verify the returned value, because other values may be enabled in future versions or service releases.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fcac5-113">반환 값</span><span class="sxs-lookup"><span data-stu-id="fcac5-113">Return Value</span></span>  
  
|<span data-ttu-id="fcac5-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fcac5-114">HRESULT</span></span>|<span data-ttu-id="fcac5-115">설명</span><span class="sxs-lookup"><span data-stu-id="fcac5-115">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="fcac5-116">모든 출력은 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="fcac5-116">All outputs are filled.</span></span>|  
|`E_INVALIDARG`|<span data-ttu-id="fcac5-117">인수 값으로 NULL이 전달 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fcac5-117">NULL was passed as an argument value.</span></span>|  
|`COR_E_NOTSUPPORTED`|<span data-ttu-id="fcac5-118">CLR 구현 된 메모리 영역에 대 한 정보를 제공할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fcac5-118">The CLR implementation cannot provide information about the memory region.</span></span> <span data-ttu-id="fcac5-119">이 작업은 다음과 같은 이유로 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcac5-119">This can happen for the following reasons:</span></span><br /><br /> <span data-ttu-id="fcac5-120">-메타 데이터 범위의으로 열렸으면는 `ofWrite` 또는 `ofCopyMemory` 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="fcac5-120">-   The metadata scope was opened with the `ofWrite` or `ofCopyMemory` flag.</span></span><br /><span data-ttu-id="fcac5-121">-메타 데이터 범위의 하지 않고 열림는 `ofReadOnly` 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="fcac5-121">-   The metadata scope was opened without the `ofReadOnly` flag.</span></span><br /><span data-ttu-id="fcac5-122">- [Imetadatadispenser:: Openscopeonmemory](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md) 메서드는 파일의 메타 데이터 부분에 여는 데 사용 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fcac5-122">-   The [IMetaDataDispenser::OpenScopeOnMemory](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md) method was used to open only the metadata portion of the file.</span></span><br /><span data-ttu-id="fcac5-123">-파일 (pe) 파일이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="fcac5-123">-   The file is not a portable executable (PE) file.</span></span> <span data-ttu-id="fcac5-124">**참고:** 이러한 조건을 CLR 구현에 따라 다르며는 문제일 수 약화 이후 버전의 CLR 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcac5-124">**Note:**  These conditions depend on the CLR implementation, and are likely to be weakened in future versions of the CLR.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fcac5-125">설명</span><span class="sxs-lookup"><span data-stu-id="fcac5-125">Remarks</span></span>  
 <span data-ttu-id="fcac5-126">메모리는 `ppvData` 동안만 기본 메타 데이터 범위 열릴 가리키는 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcac5-126">The memory that `ppvData` points to is valid only as long as the underlying metadata scope is open.</span></span>  
  
 <span data-ttu-id="fcac5-127">이 메서드를 호출 하 여 메모리에는 디스크에 파일의 메타 데이터를 매핑할 때 작동 되려면는 [imetadatadispenser:: Openscope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) 지정 해야 합니다는 `ofReadOnly` 플래그를 지정 해야 합니다는 `ofWrite` 또는 `ofCopyMemory` 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="fcac5-127">In order for this method to work, when you map the metadata of an on-disk file into memory by calling the [IMetaDataDispenser::OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) method, you must specify the `ofReadOnly` flag and you must not specify the `ofWrite` or `ofCopyMemory` flag.</span></span>  
  
 <span data-ttu-id="fcac5-128">각 범위에 대 한 파일 매핑 형식의 choice는 CLR의 지정 된 구현 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcac5-128">The choice of file mapping type for each scope is specific to a given implementation of the CLR.</span></span> <span data-ttu-id="fcac5-129">사용자가 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fcac5-129">It cannot be set by the user.</span></span> <span data-ttu-id="fcac5-130">CLR의 현재 구현은 항상 반환 `fmFlat` 에 `pdwMappingType`, CLR의 버전 또는 나중에 지정된 된 버전의 서비스 릴리스 나중에 변경할 수이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcac5-130">The current implementation of the CLR always returns `fmFlat` in `pdwMappingType`, but this can change in future versions of the CLR or in future service releases of a given version.</span></span> <span data-ttu-id="fcac5-131">반환된 된 값을 항상 확인 해야 `pdwMappingType`때문에 유형이 다른 다양 한 레이아웃 및 오프셋, 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcac5-131">You should always check the returned value in `pdwMappingType`, because different types will have different layouts and offsets.</span></span>  
  
 <span data-ttu-id="fcac5-132">세 개의 매개 변수 중 하나에 대 한 NULL을 전달 하는 것은 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fcac5-132">Passing NULL for any of the three parameters is not supported.</span></span> <span data-ttu-id="fcac5-133">메서드가 반환 `E_INVALIDARG`, 및 아무런 출력이 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="fcac5-133">The method returns `E_INVALIDARG`, and none of the outputs are filled.</span></span> <span data-ttu-id="fcac5-134">매핑 유형 또는 크기의 영역을 무시 합니다. 비정상적인 프로그램 종료 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcac5-134">Ignoring the mapping type or the size of the region can result in abnormal program termination.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fcac5-135">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fcac5-135">Requirements</span></span>  
 <span data-ttu-id="fcac5-136">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fcac5-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fcac5-137">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="fcac5-137">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fcac5-138">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="fcac5-138">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="fcac5-139">**.NET framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fcac5-139">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcac5-140">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fcac5-140">See Also</span></span>  
 [<span data-ttu-id="fcac5-141">IMetaDataInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fcac5-141">IMetaDataInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-interface.md)  
 [<span data-ttu-id="fcac5-142">CorFileMapping 열거형</span><span class="sxs-lookup"><span data-stu-id="fcac5-142">CorFileMapping Enumeration</span></span>](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md)
