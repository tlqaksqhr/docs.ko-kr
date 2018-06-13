---
title: IMetaDataTables::GetNextBlob 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetNextBlob
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetNextBlob
helpviewer_keywords:
- IMetaDataTables::GetNextBlob method [.NET Framework metadata]
- GetNextBlob method [.NET Framework metadata]
ms.assetid: 017c8ab4-4c09-4754-9935-5b0b49cabecb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: caf7faeea4bcec9b73f3c43f0923d308baebf6d0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33447622"
---
# <a name="imetadatatablesgetnextblob-method"></a>IMetaDataTables::GetNextBlob 메서드
테이블에 다음 이진 대형 개체 (BLOB)의 인덱스를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetNextBlob (  
    [in]  ULONG   ixBlob,  
    [out] ULONG   *pNext  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ixBlob`  
 [in] Blob의 열에서 반환 된 인덱스입니다.  
  
 `pNext`  
 [out] 추가 BLOB의 인덱스에 대 한 포인터입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** Cor.h  
  
 **라이브러리:** MsCorEE.dll에서 리소스로 사용  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [IMetaDataTables 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [IMetaDataTables2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
