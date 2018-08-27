---
title: IAssemblyCacheItem::CreateStream 메서드
ms.date: 03/30/2017
api_name:
- IAssemblyCacheItem.CreateStream
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCacheItem::CreateStream
helpviewer_keywords:
- CreateStream method [.NET Framework fusion]
- IAsssemblyCacheItem::CreateStream method [.NET Framework fusion]
ms.assetid: 697ab0f4-470c-4baa-a415-4a975c42d0d5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3a0b3242e8ae29b9d21dc50d3ea0476967e9746f
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2018
ms.locfileid: "42934087"
---
# <a name="iassemblycacheitemcreatestream-method"></a>IAssemblyCacheItem::CreateStream 메서드
지정한 이름 및 형식을 사용 하 여 스트림을 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT CreateStream (  
    [in]  DWORD dwFlags,  
    [in]  LPCWSTR pszStreamName,  
    [in]  DWORD dwFormat,  
    [in]  DWORD dwFormatFlags,  
    [out] IStream **ppIStream,  
    [in, optional] ULARGE_INTEGER *puliMaxSize  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `dwFlags`  
 [in] 같은 값이 지원에 정의 된 플래그입니다.  
  
 `pszStreamName`  
 [in] 만들 스트림의 이름입니다.  
  
 `dwFormat`  
 [in] 스트리밍할 수 파일의 형식입니다.  
  
 `dwFormatFlags`  
 [in] 같은 값이 지원에 정의 된 형식에 따른 플래그입니다.  
  
 `ppIStream`  
 [out] 반환 된 주소에 대 한 포인터 [IStream](/windows/desktop/api/objidl/nn-objidl-istream) 인스턴스.  
  
 `puliMaxSize`  
 [in, 선택 사항] 참조 하는 스트림의 최대 크기 `ppIStream`합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Fusion.h  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [IAssemblyCacheItem 인터페이스](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md)
