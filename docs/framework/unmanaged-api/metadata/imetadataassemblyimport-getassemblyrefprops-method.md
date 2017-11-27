---
title: "IMetaDataAssemblyImport::GetAssemblyRefProps 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyImport.GetAssemblyRefProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyImport::GetAssemblyRefProps
helpviewer_keywords:
- IMetaDataAssemblyImport::GetAssemblyRefProps method [.NET Framework metadata]
- GetAssemblyRefProps method [.NET Framework metadata]
ms.assetid: 5c6b7fb4-cbca-4479-b650-ab9a99732ea0
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 9159352c4f7f338c6b9b82ea579ad3cb36c19007
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="imetadataassemblyimportgetassemblyrefprops-method"></a><span data-ttu-id="51cec-102">IMetaDataAssemblyImport::GetAssemblyRefProps 메서드</span><span class="sxs-lookup"><span data-stu-id="51cec-102">IMetaDataAssemblyImport::GetAssemblyRefProps Method</span></span>
<span data-ttu-id="51cec-103">지정 된 메타 데이터 서명 가진 어셈블리 참조에 대 한 속성의 집합을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="51cec-103">Gets the set of properties for the assembly reference with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51cec-104">구문</span><span class="sxs-lookup"><span data-stu-id="51cec-104">Syntax</span></span>  
  
```  
HRESULT GetAssemblyRefProps (  
    [in]  mdAssemblyRef        mdar,   
    [out] const void          **ppbPublicKeyOrToken,   
    [out] ULONG                *pcbPublicKeyOrToken,   
    [out] LPWSTR               szName,   
    [in]  ULONG                cchName,   
    [out] ULONG                *pchName,   
    [out] ASSEMBLYMETADATA     *pMetaData,   
    [out] const void           **ppbHashValue,   
    [out] ULONG                *pcbHashValue,   
    [out] DWORD                *pdwAssemblyRefFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="51cec-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="51cec-105">Parameters</span></span>  
 `mdar`  
 <span data-ttu-id="51cec-106">[in] `mdAssemblyRef` 메타 데이터 토큰을 가져올 속성에 대 한 어셈블리 참조를 나타내는입니다.</span><span class="sxs-lookup"><span data-stu-id="51cec-106">[in] The `mdAssemblyRef` metadata token that represents the assembly reference for which to get the properties.</span></span>  
  
 `ppbPublicKeyOrToken`  
 <span data-ttu-id="51cec-107">[out] 공개 키 또는 메타 데이터 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="51cec-107">[out] A pointer to the public key or the metadata token.</span></span>  
  
 `pcbPublicKeyOrToken`  
 <span data-ttu-id="51cec-108">[out] 반환 된 공개 키 또는 토큰의 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="51cec-108">[out] The number of bytes in the returned public key or token.</span></span>  
  
 `szName`  
 <span data-ttu-id="51cec-109">[out] 어셈블리의 단순한 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="51cec-109">[out] The simple name of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="51cec-110">[in] 와이드 문자에서 크기의 `szName`합니다.</span><span class="sxs-lookup"><span data-stu-id="51cec-110">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="51cec-111">[out] 와이드 문자에 실제로 반환 된 수에 대 한 포인터 `szName`합니다.</span><span class="sxs-lookup"><span data-stu-id="51cec-111">[out] A pointer to the number of wide chars actually returned in `szName`.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="51cec-112">[out] 어셈블리 메타 데이터가 포함 된 ASSEMBLYMETADATA 구조체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="51cec-112">[out] A pointer to an ASSEMBLYMETADATA structure that contains the assembly metadata.</span></span>  
  
 `ppbHashValue`  
 <span data-ttu-id="51cec-113">[out] 해시 값에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="51cec-113">[out] A pointer to the hash value.</span></span> <span data-ttu-id="51cec-114">이것이의 sha-1 알고리즘을 사용 하 여 해시는 `PublicKey` 는 arfFullOriginator의 플래그를 지정 하지 않으면 참조 되는 어셈블리의 속성은 [AssemblyRefFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyrefflags-enumeration.md) 열거형 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="51cec-114">This is the hash, using the SHA-1 algorithm, of the `PublicKey` property of the assembly being referenced, unless the arfFullOriginator flag of the [AssemblyRefFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyrefflags-enumeration.md) enumeration is set.</span></span>  
  
 `pcbHashValue`  
 <span data-ttu-id="51cec-115">[out] 반환 된 해시 값의 와이드 문자 수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="51cec-115">[out] The number of wide chars in the returned hash value.</span></span>  
  
 `pdwAssemblyRefFlags`  
 <span data-ttu-id="51cec-116">[out] 어셈블리에 적용할 메타 데이터를 설명 하는 플래그에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="51cec-116">[out] A pointer to flags that describe the metadata applied to an assembly.</span></span> <span data-ttu-id="51cec-117">플래그 값은 하나 이상의 조합 [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) 값입니다.</span><span class="sxs-lookup"><span data-stu-id="51cec-117">The flags value is a combination of one or more [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) values.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="51cec-118">반환 값</span><span class="sxs-lookup"><span data-stu-id="51cec-118">Return Value</span></span>  
 <span data-ttu-id="51cec-119">이 메서드가 반환; 성공 하면 s_ok이 고 그렇지 않은 경우 Winerror.h 헤더 파일에 정의 된 오류 코드 중 하나 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="51cec-119">This method returns S_OK if it succeeds; otherwise, it returns one of the error codes defined in the Winerror.h header file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="51cec-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="51cec-120">Requirements</span></span>  
 <span data-ttu-id="51cec-121">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="51cec-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51cec-122">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="51cec-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="51cec-123">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="51cec-123">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="51cec-124">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51cec-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51cec-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="51cec-125">See Also</span></span>  
 [<span data-ttu-id="51cec-126">IMetaDataAssemblyImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="51cec-126">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
