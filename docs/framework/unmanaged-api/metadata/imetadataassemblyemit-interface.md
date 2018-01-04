---
title: "IMetaDataAssemblyEmit 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyEmit
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyEmit
helpviewer_keywords: IMetaDataAssemblyEmit interface [.NET Framework metadata]
ms.assetid: 34fb03cc-2285-4a45-ac48-ad993b7a921a
topic_type: apiref
caps.latest.revision: "16"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6a7e4bd68bfd985b8902ae3b2340773ca77eee10
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataassemblyemit-interface"></a>IMetaDataAssemblyEmit 인터페이스
공용 언어 런타임에서 리소스를 확인하고 소비하는 데 사용되는 자체 설명 모델을 지원하는 메서드를 제공합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[DefineAssembly 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassembly-method.md)|지정된 어셈블리에 대한 메타데이터를 포함하는 어셈블리 데이터 구조를 만들고 연결된 메타데이터 토큰을 반환합니다.|  
|[DefineAssemblyRef 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md)|이 어셈블리가 참조하는 어셈블리에 대한 메타데이터를 포함하는 `AssemblyRef` 구조를 만들고 연결된 메타데이터 토큰을 반환합니다.|  
|[DefineExportedType 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md)|지정된 내보낸 형식에 대한 메타데이터를 포함하는 `ExportedType` 구조를 만들고 연결된 메타데이터 토큰을 반환합니다.|  
|[DefineFile 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md)|이 어셈블리가 참조하는 어셈블리에 대한 메타데이터를 포함하는 `File` 메타데이터 구조를 만들고 연결된 메타데이터 토큰을 반환합니다.|  
|[DefineManifestResource 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definemanifestresource-method.md)|지정된 매니페스트 리소스에 대한 메타데이터를 포함하는 `ManifestResource` 구조를 만들고 연결된 메타데이터 토큰을 반환합니다.|  
|[SetAssemblyProps 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-setassemblyprops-method.md)|지정된 `Assembly` 메타데이터 구조를 수정합니다.|  
|[SetAssemblyRefProps 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-setassemblyrefprops-method.md)|지정된 `AssemblyRef` 메타데이터 구조를 수정합니다.|  
|[SetExportedTypeProps 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-setexportedtypeprops-method.md)|지정된 `ExportedType` 메타데이터 구조를 수정합니다.|  
|[SetFileProps 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-setfileprops-method.md)|지정된 `File` 메타데이터 구조를 수정합니다.|  
|[SetManifestResourceProps 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-setmanifestresourceprops-method.md)|지정된 `ManifestResource` 메타데이터 구조를 수정합니다.|  
  
## <a name="remarks"></a>설명  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** Cor.h  
  
 **라이브러리:** MsCorEE.dll에서 리소스로 사용  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [메타데이터 인터페이스](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)  
 [IMetaDataAssemblyImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
