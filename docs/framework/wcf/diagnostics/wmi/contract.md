---
title: Contract1
ms.date: 03/30/2017
ms.assetid: aa00f6b3-7e1f-4213-841a-206463fca20b
ms.openlocfilehash: 12b45c08a3d8dc69e740ce77d0d2abd097907ac2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="contract"></a>계약
계약  
  
## <a name="syntax"></a>구문  
  
```  
class Contract  
{  
  sint32 AppDomainId;  
  Behavior Behaviors[];  
  string Name;  
  string Namespace;  
  Operation Operations[];  
  sint32 ProcessId;  
  Contract ref;  
  string SessionMode;  
  string Type;  
};  
```  
  
## <a name="methods"></a>메서드  
 Contract 클래스는 메서드를 정의하지 않습니다.  
  
## <a name="properties"></a>속성  
 Contract 클래스에는 다음 속성이 있습니다.  
  
### <a name="appdomainid"></a>AppDomainId  
 데이터 형식: sint32  
  
 액세스 형식: 읽기 전용  
  
 계약을 호스팅하는 appdomain의 appdomain ID입니다.  
  
### <a name="behaviors"></a>동작  
 데이터 형식: Behavior array  
  
 액세스 형식: 읽기 전용  
  
 이 계약과 연결된 동작입니다.  
  
### <a name="name"></a>이름  
 데이터 형식: string  
  
 액세스 형식: 읽기 전용  
  
 WSDL에 있는 계약의 이름입니다.  
  
### <a name="namespace"></a>네임스페이스  
 데이터 형식: string  
  
 액세스 형식: 읽기 전용  
  
 WSDL에 있는 `portType` 요소의 네임스페이스입니다.  
  
### <a name="operations"></a>작업  
 데이터 형식: Operation array  
  
 액세스 형식: 읽기 전용  
  
 이 계약의 작업입니다.  
  
### <a name="processid"></a>ProcessId  
 데이터 형식: sint32  
  
 액세스 형식: 읽기 전용  
  
 계약을 호스팅하는 프로세스의 프로세스 ID입니다.  
  
### <a name="ref"></a>ref  
 데이터 형식: Contract  
  
 액세스 형식: 읽기 전용  
  
 계약이 이중 계약인 경우 콜백의 형식입니다.  
  
### <a name="sessionmode"></a>SessionMode  
 데이터 형식: string  
  
 액세스 형식: 읽기 전용  
  
 계약에서 채널 세션을 사용하기 위해 이 계약과 연결된 바인딩이 필요한지 여부를 나타냅니다.  
  
### <a name="type"></a>형식  
 데이터 형식: string  
  
 액세스 형식: 읽기 전용  
  
 계약의 형식입니다.  
  
## <a name="requirements"></a>요구 사항  
  
|MOF|Servicemodel.mof에 선언되어 있습니다.|  
|---------|-----------------------------------|  
|네임스페이스|root\ServiceModel에 정의되어 있습니다.|  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceModel.Description.ContractDescription>
