---
title: IMetaDataDispenser::OpenScope 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataDispenser.OpenScope
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenser::OpenScope
helpviewer_keywords:
- IMetaDataDispenser::OpenScope method [.NET Framework metadata]
- OpenScope method, IMetaDataDispenser interface [.NET Framework metadata]
ms.assetid: 65063ad5-e0d9-4c01-8f8b-9a5950109fa6
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0fb805e3292d90fd5f9562d9b0b8fcc31f84ec7f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="imetadatadispenseropenscope-method"></a>IMetaDataDispenser::OpenScope 메서드
기존, 디스크에 파일을 열고 해당 메타 데이터를 메모리에 매핑합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT OpenScope (  
    [in]  LPCWSTR     szScope,   
    [in]  DWORD       dwOpenFlags,   
    [in]  REFIID      riid,   
    [out] IUnknown    **ppIUnk  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `szScope`  
 [in] 열 파일의 이름입니다. 공용 언어 런타임 (CLR) 메타 데이터 파일에 포함 되어야 합니다.  
  
 `dwOpenFlags`  
 [in] 값은 [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) 열기 위한 모드 (읽기, 쓰기 및 등)를 지정 하는 열거형입니다.  
  
 `riid`  
 [in] 반환할; 원하는 메타 데이터 인터페이스의 IID 호출자에 게 가져옵니다 (읽기 대상) 또는 (쓰기) 메타 데이터 내보내기 인터페이스를 사용 합니다.  
  
 값 `riid` "가져오기" 또는 "내보내기" 인터페이스 중 하나를 지정 해야 합니다. 유효한 값은 IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyEmit, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2, 또는 IID_IMetaDataImport2입니다.  
  
 `ppIUnk`  
 [out] 반환 되는 인터페이스 포인터입니다.  
  
## <a name="remarks"></a>설명  
 "가져오기" 인터페이스 중 하나에서 메서드를 사용 하 여 또는 "내보내기" 인터페이스 중 하나에서 메서드를 사용 하 여 추가할 메타 데이터의 메모리 내 복사본을 쿼리할 수 있습니다.  
  
 대상 파일에 CLR 메타 데이터가 없는 경우는 `OpenScope` 메서드가 실패 합니다.  
  
 .NET framework에서 버전 1.0 및 버전 1.1에서 경우 범위를 열지 `dwOpenFlags` ofRead로 설정 될 수 공유 합니다. 즉, 이후에 대 한 호출이 `OpenScope` 이전에 연 파일의 이름을 전달, 기존 범위가 다시 사용 되 고 새로운 집합이 데이터 구조는 만들어지지 않습니다. 그러나이 공유로 인해 문제가 발생할 수 있습니다.  
  
 .NET Framework 버전 2.0에서에서 범위 사용 하 여 열린 `dwOpenFlags` 더 이상 공유 ofRead로 설정 합니다. OfReadOnly 값을 사용 하 여 범위를 공유할 수 있도록 합니다. 범위를 공유 되는 경우 "읽기/쓰기" 메타 데이터 인터페이스를 사용 하는 쿼리가 실패 합니다.  
  
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
