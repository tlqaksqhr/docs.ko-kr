---
title: IMetaDataAssemblyImport 인터페이스
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport
helpviewer_keywords:
- IMetaDataAssemblyImport interface [.NET Framework metadata]
ms.assetid: 29c6fba5-4cea-417d-b484-7ed22ebff1c9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: da75f98edb54080658dc86f48d4ebb458d72f20d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33449314"
---
# <a name="imetadataassemblyimport-interface"></a>IMetaDataAssemblyImport 인터페이스
어셈블리 매니페스트에 액세스하여 이를 검사하는 메서드를 제공합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[CloseEnum 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-closeenum-method.md)|지정한 열거자에 대 한 핸들을 해제합니다.|  
|[EnumAssemblyRefs 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumassemblyrefs-method.md)|포함 하는 열거자에 대 한 인터페이스 포인터를 가져옵니다는 `mdAssemblyRef` 현재 메타 데이터 범위에 있는 어셈블리에서 참조 하는 어셈블리의 토큰이 있습니다.|  
|[EnumExportedTypes 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumexportedtypes-method.md)|포함 하는 열거자에 대 한 인터페이스 포인터를 가져옵니다는 `mdExportedType` 현재 메타 데이터 범위에 있는 어셈블리에서 참조 되는 COM 형식의 토큰입니다.|  
|[EnumFiles 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumfiles-method.md)|포함 하는 열거자에 대 한 인터페이스 포인터를 가져옵니다는 `mdFile` 현재 메타 데이터 범위에 있는 어셈블리에서 참조 하는 파일의 토큰이 있습니다.|  
|[EnumManifestResources 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enummanifestresources-method.md)|포함 하는 열거자에 대 한 인터페이스 포인터를 가져옵니다는 `mdManifestResource` 현재 메타 데이터 범위에 있는 어셈블리에서 참조 하는 리소스의 토큰이 있습니다.|  
|[FindAssembliesByName 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findassembliesbyname-method.md)|배열을 가져옵니다 `mdAssemblyRef` 지정한 이름 가진 어셈블리에 대 한 토큰입니다.|  
|[FindExportedTypeByName 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findexportedtypebyname-method.md)|가져옵니다는 `mdExportedType` 지정된 된 이름 사용 하 여 COM 형식에 대 한 토큰입니다.|  
|[FindManifestResourceByName 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findmanifestresourcebyname-method.md)|가져옵니다는 `mdManifestResource` 지정 된 이름의 리소스에 대 한 토큰입니다.|  
|[GetAssemblyFromScope 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyfromscope-method.md)|현재 메타 데이터 범위에서 어셈블리에 대 한 토큰을 가져옵니다.|  
|[GetAssemblyProps 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyprops-method.md)|지정된 된 어셈블리의 속성 설정을 가져옵니다.|  
|[GetAssemblyRefProps 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyrefprops-method.md)|지정 된 속성 설정을 가져옵니다 `mdAssemblyRef` 토큰입니다.|  
|[GetExportedTypeProps 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getexportedtypeprops-method.md)|지정한 COM 형식의 속성 설정을 가져옵니다.|  
|[GetFileProps 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getfileprops-method.md)|지정된 된 파일의 속성 설정을 가져옵니다.|  
|[GetManifestResourceProps 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getmanifestresourceprops-method.md)|지정된 된 매니페스트 리소스의 속성 설정을 가져옵니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** Cor.h  
  
 **라이브러리:** MsCorEE.dll에서 리소스로 사용  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [메타데이터 인터페이스](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)  
 [IMetaDataAssemblyEmit 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
