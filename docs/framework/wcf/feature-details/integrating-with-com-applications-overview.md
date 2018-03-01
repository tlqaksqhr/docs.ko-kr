---
title: "COM 응용 프로그램과 통합 개요"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- COM [WCF], integration overview
ms.assetid: 02c5697f-6e2e-47d6-b715-f3a28aebfbd5
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5b20ae5329f08e9391fd7b93218c44c3c1978a48
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="integrating-with-com-applications-overview"></a>COM 응용 프로그램과 통합 개요
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]은 관리 코드 개발자에게 연결된 응용 프로그램을 만들 수 있는 풍부한 환경을 제공합니다. 하지만 관리되지 않는 COM 기반 코드에 이미 상당한 투자를 하여 마이그레이션을 원하지 않을 시에는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스 모니커를 사용하여 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 웹 서비스를 기존 코드에 바로 통합할 수도 있습니다. 서비스 모니커는 Office VBA, Visual Basic 6.0 또는 Visual C++ 6.0과 같은 다양한 범위의 COM 기반 개발 환경에서 사용할 수 있습니다.  
  
> [!NOTE]
>  서비스 모니커에서는 모든 통신에 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 통신 채널을 사용합니다. 이 채널의 보안 및 ID 메커니즘은 표준 COM 및 DCOM 프록시에 사용되는 메커니즘과 다릅니다. 또한 서비스 모니커에서는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 통신 채널을 사용하기 때문에 모든 호출에 대한 기본 시간 제한은 1분입니다.  
  
 관리되지 않는 개발자에게 `GetObject` 웹 서비스 호출을 위한 강력한 형식의 COM별 접근 방식을 제공하려면 서비스 모니커를 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 함수와 함께 사용합니다. 이를 위해서는 사용할 바인딩 및 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 웹 서비스 계약에 대한 로컬 COM 노출 정의가 필요합니다. 처음 메서드를 호출할 때 COM 프로그래머에 대해 이 채널이 투명하게 생성되지만, 다른 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트와 마찬가지로 서비스 모니커는 서비스에 대한 형식화된 채널을 생성합니다.  
  
 또한 다른 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트와 공통적으로, 모니커를 사용하면 응용 프로그램에서 서비스와 통신할 주소, 바인딩 및 계약을 지정합니다. 계약은 다음 방법 중 하나로 지정할 수 있습니다.  
  
-   형식화된 계약 – 계약이 클라이언트 컴퓨터에 COM 노출 형식으로 등록됩니다.  
  
-   WSDL 계약 – 계약이 WSDL 문서 형식으로 제공됩니다.  
  
-   MEX 계약 – 계약이 MEX(메타데이터 교환) 끝점에서 런타임에 검색됩니다.  
  
## <a name="parameters-supported-by-the-service-moniker"></a>서비스 모니커에서 지원하는 매개 변수  
 다음 표에서는 서비스 모니커에서 지원하는 매개 변수를 보여 줍니다.  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`address`|서비스의 URL 위치입니다.|  
|`binding`|응용 프로그램 구성의 바인딩 섹션 이름입니다.|  
|`bindingConfiguration`|명명된 바인딩 섹션 내의 명명된 바인딩 인스턴스입니다.|  
|`contract`|MEX에서 서비스 계약이나 계약 이름을 나타내는 IID(인터페이스 식별자)입니다.|  
|`wsdl`|계약 정의에 대한 대체 형식을 제공하는 WSDL 문서입니다.|  
|`spnIdentity`|서비스와의 통신에 사용되는 SPN(서비스 사용자 이름) ID입니다.|  
|`upnIdentity`|서비스와의 통신에 사용되는 UPN(User Principal Name) ID입니다.|  
|`dnsIdentity`|서비스와의 통신에 사용되는 DNS ID입니다.|  
|`mexAddress`|서비스의 MEX(메타데이터 교환) 끝점에 대한 URL 위치입니다.|  
|`mexBinding`|MEX 끝점과 연결하기 위한 응용 프로그램 구성의 바인딩 섹션 이름입니다.|  
|`mexBindingConfiguration`|MEX 끝점과 연결하기 위한 명명된 바인딩 섹션 내의 명명된 바인딩 인스턴스입니다.|  
|`bindingNamespace`|검색된 MEX의 바인딩 섹션 이름에 대한 네임스페이스입니다.|  
|`contractNamespace`|검색된 MEX의 계약에 대한 네임스페이스입니다.|  
|`mexSpnIdentity`|MEX 끝점과의 통신에 사용되는 SPN(서버 사용자 이름) ID입니다.|  
|`mexUpnIdentity`|MEX 끝점과의 통신에 사용되는 UPN(User Principal Name) ID입니다.|  
|`mexDnsIdentity`|MEX 끝점과의 통신에 사용되는 DNS ID입니다.|  
|`serializer`|"xml" 또는 "datacontract" serializer 사용을 지정합니다.|  
  
> [!NOTE]
>  서비스 모니커를 완전한 COM 기반 클라이언트와 함께 사용하더라도 서비스 모니커를 사용하려면 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 및 지원 .NET Framework 2.0이 클라이언트 컴퓨터에 설치되어 있어야 합니다. 또한 서비스 모니커를 사용하는 클라이언트 응용 프로그램에서 올바른 버전의 .NET Framework 런타임을 로드해야 하는 점도 중요합니다. Office 응용 프로그램에서 모니커를 사용할 때 올바른 프레임워크 버전이 로드되도록 하기 위해 구성 파일이 필요할 수 있습니다. 예를 들어 Excel을 사용하는 경우, 다음 텍스트가 Excel.exe 파일과 동일한 디렉터리의 Excel.exe.config라는 파일에 있어야 합니다.  
>   
>  `<?xml version="1.0" encoding="utf-8"?>`  
>   
>  `<configuration xmlns=` `http://schemas.microsoft.com/.NetConfiguration/v2.0` `>`  
>   
>  `<startup>`  
>   
>  `<requiredRuntime version="v2.0.50727" />`  
>   
>  `</startup>`  
>   
>  `</configuration>`  
  
## <a name="see-also"></a>참고 항목  
 [방법: 서비스 모니커 등록 및 구성](../../../../docs/framework/wcf/feature-details/how-to-register-and-configure-a-service-moniker.md)
