---
title: ServiceMetadataBehavior
ms.date: 03/30/2017
ms.assetid: 0f194476-72f1-467e-bdce-674306316e64
ms.openlocfilehash: e96a732f8b3b4d78d597429905cc7dd290dcc606
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33486002"
---
# <a name="servicemetadatabehavior"></a>ServiceMetadataBehavior
ServiceMetadataBehavior  
  
## <a name="syntax"></a>구문  
  
```  
class ServiceMetadataBehavior : Behavior  
{  
  string ExternalMetadataLocation;  
  boolean HttpGetEnabled;  
  string HttpGetUrl;  
  boolean HttpsGetEnabled;  
  string HttpsGetUrl;  
};  
```  
  
## <a name="methods"></a>메서드  
 ServiceMetadataBehavior 클래스는 메서드를 정의하지 않습니다.  
  
## <a name="properties"></a>속성  
 ServiceMetadataBehavior 클래스에는 다음과 같은 속성이 있습니다.  
  
### <a name="externalmetadatalocation"></a>ExternalMetadataLocation  
 데이터 형식: string  
  
 액세스 형식: 읽기 전용  
  
 서비스가 메타데이터 요청을 리디렉션하는 위치를 설정합니다.  
  
### <a name="httpgetenabled"></a>HttpGetEnabled  
 데이터 형식: boolean  
  
 액세스 형식: 읽기 전용  
  
 `HttpGetUrl` 특성으로 제어되는 주소에서 서비스가 WSDL을 게시할지 여부를 제어합니다.  
  
### <a name="httpgeturl"></a>HttpGetUrl  
 데이터 형식: string  
  
 액세스 형식: 읽기 전용  
  
 HTTP를 사용한 검색을 위해 서비스 WSDL이 게시되는 위치를 설정합니다.  
  
### <a name="httpsgetenabled"></a>HttpsGetEnabled  
 데이터 형식: boolean  
  
 액세스 형식: 읽기 전용  
  
 `HttpsGetUrl` 특성으로 제어되는 주소에서 서비스가 HTTPS를 통해 WSDL을 게시할지 여부를 제어합니다.  
  
### <a name="httpsgeturl"></a>HttpsGetUrl  
 데이터 형식: string  
  
 액세스 형식: 읽기 전용  
  
 HTTPS를 사용한 검색을 위해 서비스 WSDL이 게시되는 위치를 설정합니다.  
  
## <a name="requirements"></a>요구 사항  
  
|MOF|Servicemodel.mof에 선언되어 있습니다.|  
|---------|-----------------------------------|  
|네임스페이스|root\ServiceModel에 정의되어 있습니다.|  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceModel.Description.ServiceMetadataBehavior>
