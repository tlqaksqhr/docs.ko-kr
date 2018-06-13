---
title: IMetaDataAssemblyImport::FindAssembliesByName 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.FindAssembliesByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::FindAssembliesByName
helpviewer_keywords:
- FindAssembliesByName method [.NET Framework metadata]
- IMetaDataAssemblyImport::FindAssembliesByName method [.NET Framework metadata]
ms.assetid: 4db97cf9-e4c1-4233-8efa-cbdc0e14a8e4
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a6c7bf332d829a440fe216756f7a23ec1277e6c6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33449288"
---
# <a name="imetadataassemblyimportfindassembliesbyname-method"></a><span data-ttu-id="bd0fd-102">IMetaDataAssemblyImport::FindAssembliesByName 메서드</span><span class="sxs-lookup"><span data-stu-id="bd0fd-102">IMetaDataAssemblyImport::FindAssembliesByName Method</span></span>
<span data-ttu-id="bd0fd-103">지정 된 어셈블리의 배열을 가져옵니다 `szAssemblyName` 참조를 확인 하는 것에 대 한 공용 언어 런타임 (CLR)에서 표준 규칙을 사용 하 여 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="bd0fd-103">Gets an array of assemblies with the specified `szAssemblyName` parameter, using the standard rules employed by the common language runtime (CLR) for resolving references.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd0fd-104">구문</span><span class="sxs-lookup"><span data-stu-id="bd0fd-104">Syntax</span></span>  
  
```  
HRESULT FindAssembliesByName (  
    [in]  LPCWSTR     szAppBase,   
    [in]  LPCWSTR     szPrivateBin,   
    [in]  LPCWSTR     szAssemblyName,   
    [out] IUnknown    *ppIUnk[],   
    [in]  ULONG       cMax,   
    [out] ULONG       *pcAssemblies  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bd0fd-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="bd0fd-105">Parameters</span></span>  
 `szAppBase`  
 <span data-ttu-id="bd0fd-106">[in] 지정된 된 어셈블리에 대 한 검색 하려는 루트 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="bd0fd-106">[in] The root directory in which to search for the given assembly.</span></span> <span data-ttu-id="bd0fd-107">이 값 설정 하는 경우 `null`, `FindAssembliesByName` 어셈블리에 대 한 전역 어셈블리 캐시에만 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd0fd-107">If this value is set to `null`, `FindAssembliesByName` will look only in the global assembly cache for the assembly.</span></span>  
  
 `szPrivateBin`  
 <span data-ttu-id="bd0fd-108">[in] 세미콜론으로 구분 된 아래의 하위 디렉터리 (예를 들어, "bin; bin2"), 루트 디렉터리에서 어셈블리에 대 한 검색할 목록.</span><span class="sxs-lookup"><span data-stu-id="bd0fd-108">[in] A list of semicolon-delimited subdirectories (for example, "bin;bin2"), under the root directory, in which to search for the assembly.</span></span> <span data-ttu-id="bd0fd-109">기본 검색 규칙에에서 지정 된 된 권한과 함께 이러한 디렉터리가 검색 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd0fd-109">These directories are probed in addition to those specified in the default probing rules.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="bd0fd-110">[in] 찾을 어셈블리의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="bd0fd-110">[in] The name of the assembly to find.</span></span> <span data-ttu-id="bd0fd-111">이 문자열의 형식은 클래스 참조 페이지에 정의 되어 <xref:System.Reflection.AssemblyName>합니다.</span><span class="sxs-lookup"><span data-stu-id="bd0fd-111">The format of this string is defined in the class reference page for <xref:System.Reflection.AssemblyName>.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="bd0fd-112">[in] 형식의 배열 <<!--zzxref:IUnknown --> `IUnknown`>를 작성할는 `IMetadataAssemblyImport` 인터페이스 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="bd0fd-112">[in] An array of type <<!--zzxref:IUnknown --> `IUnknown`> in which to put the `IMetadataAssemblyImport` interface pointers.</span></span>  
  
 `cMax`  
 <span data-ttu-id="bd0fd-113">[out] 에 추가할 수 있는 인터페이스 포인터의 최대 수 `ppIUnk`합니다.</span><span class="sxs-lookup"><span data-stu-id="bd0fd-113">[out] The maximum number of interface pointers that can be placed in `ppIUnk`.</span></span>  
  
 `pcAssemblies`  
 <span data-ttu-id="bd0fd-114">[out] 반환 된 인터페이스 포인터의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="bd0fd-114">[out] The number of interface pointers returned.</span></span> <span data-ttu-id="bd0fd-115">인터페이스 포인터의 개수에 실제로 배치, 즉 `ppIUnk`합니다.</span><span class="sxs-lookup"><span data-stu-id="bd0fd-115">That is, the number of interface pointers actually placed in `ppIUnk`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bd0fd-116">반환 값</span><span class="sxs-lookup"><span data-stu-id="bd0fd-116">Return Value</span></span>  
  
|<span data-ttu-id="bd0fd-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="bd0fd-117">HRESULT</span></span>|<span data-ttu-id="bd0fd-118">설명</span><span class="sxs-lookup"><span data-stu-id="bd0fd-118">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="bd0fd-119">`FindAssembliesByName` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd0fd-119">`FindAssembliesByName` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="bd0fd-120">어셈블리가 없는 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd0fd-120">There are no assemblies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bd0fd-121">설명</span><span class="sxs-lookup"><span data-stu-id="bd0fd-121">Remarks</span></span>  
 <span data-ttu-id="bd0fd-122">지정 된 어셈블리 이름의 `FindAssembliesByName` 메서드 어셈블리 참조를 확인 하기 위한 표준 규칙에 따라 어셈블리를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="bd0fd-122">Given an assembly name, the `FindAssembliesByName` method finds the assembly by following the standard rules for resolving assembly references.</span></span> <span data-ttu-id="bd0fd-123">(자세한 내용은 참조 [런타임에서 어셈블리를 찾는 방법을](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).) `FindAssembliesByName` 호출자가 어셈블리 확인자 컨텍스트 응용 프로그램 기본 및 개인 검색 경로 등의 다양 한 측면을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd0fd-123">(For more information, see [How the Runtime Locates Assemblies](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).) `FindAssembliesByName` allows the caller to configure various aspects of the assembly resolver context, such as application base and private search path.</span></span>  
  
 <span data-ttu-id="bd0fd-124">`FindAssembliesByName` 메서드를 사용 하려면 CLR 어셈블리 확인 논리를 호출 하려면 프로세스에서 초기화 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd0fd-124">The `FindAssembliesByName` method requires the CLR to be initialized in the process in order to invoke the assembly resolution logic.</span></span> <span data-ttu-id="bd0fd-125">따라서 호출 해야 [CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md) (COINITEE_DEFAULT 전달) 호출 하기 전에 `FindAssembliesByName`, 한 다음 호출 하 여 따라 [CoUninitializeCor](../../../../docs/framework/unmanaged-api/hosting/couninitializecor-function.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="bd0fd-125">Therefore, you must call [CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md) (passing COINITEE_DEFAULT) before calling `FindAssembliesByName`, and then follow with a call to [CoUninitializeCor](../../../../docs/framework/unmanaged-api/hosting/couninitializecor-function.md).</span></span>  
  
 <span data-ttu-id="bd0fd-126">`FindAssembliesByName` 반환 된 [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) 전달 되는 어셈블리 이름에 대 한 어셈블리 매니페스트를 포함 하는 파일에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="bd0fd-126">`FindAssembliesByName` returns an [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) pointer to the file containing the assembly manifest for the assembly name that is passed in.</span></span> <span data-ttu-id="bd0fd-127">지정 된 어셈블리 이름 (예: 버전 포함 되어 있지 않으면) 완전 하 게 지정 되지 않은 경우 여러 어셈블리를 반환 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd0fd-127">If the given assembly name is not fully specified (for example, if it does not include a version), multiple assemblies might be returned.</span></span>  
  
 <span data-ttu-id="bd0fd-128">`FindAssembliesByName` 컴파일 타임에 참조 된 어셈블리를 찾으려고 시도 하는 컴파일러에서 일반적으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd0fd-128">`FindAssembliesByName` is commonly used by a compiler that attempts to find a referenced assembly at compile time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bd0fd-129">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bd0fd-129">Requirements</span></span>  
 <span data-ttu-id="bd0fd-130">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="bd0fd-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bd0fd-131">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="bd0fd-131">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bd0fd-132">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="bd0fd-132">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bd0fd-133">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bd0fd-133">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd0fd-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bd0fd-134">See Also</span></span>  
 [<span data-ttu-id="bd0fd-135">런타임에서 어셈블리를 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="bd0fd-135">How the Runtime Locates Assemblies</span></span>](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 [<span data-ttu-id="bd0fd-136">IMetaDataAssemblyImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bd0fd-136">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
