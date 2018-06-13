---
title: IMetaDataDispenser::OpenScopeOnMemory 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataDispenser.OpenScopeOnMemory
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenser::OpenScopeOnMemory
helpviewer_keywords:
- OpenScopeOnMemory method [.NET Framework metadata]
- IMetaDataDispenser::OpenScopeOnMemory method [.NET Framework metadata]
ms.assetid: 14218249-bdec-48ae-b5fc-9f57f7ca8501
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f184c04db384c2b9bdbce2d8ae6919c05a2ab425
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33448897"
---
# <a name="imetadatadispenseropenscopeonmemory-method"></a>IMetaDataDispenser::OpenScopeOnMemory 메서드
기존 메타 데이터가 포함 된 메모리 영역을 엽니다. 즉,이 메서드는 메타 데이터로 기존 데이터를 처리 하는 메모리의 지정된 된 영역을 엽니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT OpenScopeOnMemory (  
    [in]  LPCVOID     pData,   
    [in]  ULONG       cbData,   
    [in]  DWORD       dwOpenFlags,   
    [in]  REFIID      riid,   
    [out] IUnknown    **ppIUnk  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pData`  
 [in] 메모리 영역의 시작 주소를 지정 하는 포인터입니다.  
  
 `cbData`  
 [in] 바이트 단위로 메모리 영역의 크기입니다.  
  
 `dwOpenFlags`  
 [in] 값은 [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) 열기 위한 모드 (읽기, 쓰기 및 등)를 지정 하는 열거형입니다.  
  
 `riid`  
 [in] 반환할; 원하는 메타 데이터 인터페이스의 IID 호출자에 게 가져옵니다 (읽기 대상) 또는 (쓰기) 메타 데이터 내보내기 인터페이스를 사용 합니다.  
  
 값 `riid` "가져오기" 또는 "내보내기" 인터페이스 중 하나를 지정 해야 합니다. 유효한 값은 IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyEmit, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2, 또는 IID_IMetaDataImport2입니다.  
  
 `ppIUnk`  
 [out] 반환 되는 인터페이스 포인터입니다.  
  
## <a name="remarks"></a>설명  
 "가져오기" 인터페이스 중 하나에서 메서드를 사용 하 여 또는 "내보내기" 인터페이스 중 하나에서 메서드를 사용 하 여 추가할 메타 데이터의 메모리 내 복사본을 쿼리할 수 있습니다.  
  
 `OpenScopeOnMemory` 메서드는 비슷합니다는 [imetadatadispenser:: Openscope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) 메서드를 제외 하 고 관심 있는 메타 데이터 디스크에 파일에서 하지 않고 메모리에 이미 있습니다.  
  
 대상 영역의 메모리 공용 언어 런타임 (CLR) 메타 데이터가 포함 되어 있지 않으면는 `OpenScopeOnMemory` 메서드가 실패 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** Cor.h  
  
 **라이브러리:** MsCorEE.dll에서 리소스로 사용  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [IMetaDataDispenser 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)  
 [IMetaDataDispenserEx 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)  
 [IMetaDataAssemblyEmit 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)  
 [IMetaDataAssemblyImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)  
 [IMetaDataEmit 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [IMetaDataEmit2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)  
 [IMetaDataImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [IMetaDataImport2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
