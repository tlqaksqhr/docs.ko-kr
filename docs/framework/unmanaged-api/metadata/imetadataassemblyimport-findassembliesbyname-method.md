---
title: "IMetaDataAssemblyImport::FindAssembliesByName 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyImport.FindAssembliesByName
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyImport::FindAssembliesByName
helpviewer_keywords:
- FindAssembliesByName method [.NET Framework metadata]
- IMetaDataAssemblyImport::FindAssembliesByName method [.NET Framework metadata]
ms.assetid: 4db97cf9-e4c1-4233-8efa-cbdc0e14a8e4
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 3b957430e66e4381a9be33ceb687d7aecba53a4a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataassemblyimportfindassembliesbyname-method"></a>IMetaDataAssemblyImport::FindAssembliesByName 메서드
지정 된 어셈블리의 배열을 가져옵니다 `szAssemblyName` 참조를 확인 하는 것에 대 한 공용 언어 런타임 (CLR)에서 표준 규칙을 사용 하 여 매개 변수입니다.  
  
## <a name="syntax"></a>구문  
  
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
  
#### <a name="parameters"></a>매개 변수  
 `szAppBase`  
 [in] 지정된 된 어셈블리에 대 한 검색 하려는 루트 디렉터리입니다. 이 값 설정 하는 경우 `null`, `FindAssembliesByName` 어셈블리에 대 한 전역 어셈블리 캐시에만 표시 됩니다.  
  
 `szPrivateBin`  
 [in] 세미콜론으로 구분 된 아래의 하위 디렉터리 (예를 들어, "bin; bin2"), 루트 디렉터리에서 어셈블리에 대 한 검색할 목록. 기본 검색 규칙에에서 지정 된 된 권한과 함께 이러한 디렉터리가 검색 됩니다.  
  
 `szAssemblyName`  
 [in] 찾을 어셈블리의 이름입니다. 이 문자열의 형식은 클래스 참조 페이지에 정의 되어 <xref:System.Reflection.AssemblyName>합니다.  
  
 `ppIUnk`  
 [in] 형식의 배열 <<!--zzxref:IUnknown --> `IUnknown`>를 작성할는 `IMetadataAssemblyImport` 인터페이스 포인터입니다.  
  
 `cMax`  
 [out] 에 추가할 수 있는 인터페이스 포인터의 최대 수 `ppIUnk`합니다.  
  
 `pcAssemblies`  
 [out] 반환 된 인터페이스 포인터의 수입니다. 인터페이스 포인터의 개수에 실제로 배치, 즉 `ppIUnk`합니다.  
  
## <a name="return-value"></a>반환 값  
  
|HRESULT|설명|  
|-------------|-----------------|  
|`S_OK`|`FindAssembliesByName`성공적으로 반환 합니다.|  
|`S_FALSE`|어셈블리가 없는 있습니다.|  
  
## <a name="remarks"></a>설명  
 지정 된 어셈블리 이름의 `FindAssembliesByName` 메서드 어셈블리 참조를 확인 하기 위한 표준 규칙에 따라 어셈블리를 찾습니다. (자세한 내용은 참조 [런타임에서 어셈블리를 찾는 방법을](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).) `FindAssembliesByName` 호출자가 어셈블리 확인자 컨텍스트 응용 프로그램 기본 및 개인 검색 경로 등의 다양 한 측면을 구성할 수 있습니다.  
  
 `FindAssembliesByName` 메서드를 사용 하려면 CLR 어셈블리 확인 논리를 호출 하려면 프로세스에서 초기화 되어야 합니다. 따라서 호출 해야 [CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md) (COINITEE_DEFAULT 전달) 호출 하기 전에 `FindAssembliesByName`, 한 다음 호출 하 여 따라 [CoUninitializeCor](../../../../docs/framework/unmanaged-api/hosting/couninitializecor-function.md)합니다.  
  
 `FindAssembliesByName`반환 된 [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) 전달 되는 어셈블리 이름에 대 한 어셈블리 매니페스트를 포함 하는 파일에 대 한 포인터입니다. 지정 된 어셈블리 이름 (예: 버전 포함 되어 있지 않으면) 완전 하 게 지정 되지 않은 경우 여러 어셈블리를 반환 될 수 있습니다.  
  
 `FindAssembliesByName`컴파일 타임에 참조 된 어셈블리를 찾으려고 시도 하는 컴파일러에서 일반적으로 사용 됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** Cor.h  
  
 **라이브러리:** MsCorEE.dll에서 리소스로 사용  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [런타임에서 어셈블리를 찾는 방법](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 [IMetaDataAssemblyImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
