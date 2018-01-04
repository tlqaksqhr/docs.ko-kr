---
title: "계약"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF [WCF], contracts
- contracts [WCF]
- Windows Communication Foundation [WCF], contracts
ms.assetid: c8364183-4ac1-480b-804a-c5e6c59a5d7d
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9a45fc606ac962b4dc7aac8b49ed9a3c6c421ccd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="contracts"></a>계약
이 단원에서는 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 계약을 정의하고 구현하는 방법을 설명합니다. 서비스 계약에서는 끝점이 외부와 통신하는 내용을 지정합니다. 더 구체적으로 말하면, 단방향 및 이중 request/reply와 같은 기본 메시지 교환 패턴에 구성된 특정 메시지 집합에 대한 문입니다. 서비스 계약이 논리적으로 관련된 메시지 교환 집합인 경우 서비스 작업은 단일 메시지 교환이 됩니다. 예를 들어 `Hello` 작업에서는 호출자가 인사말을 알릴 수 있도록 단일 메시지를 수락해야 하며 작업 의례에 따라 메시지를 반환하거나 반환하지 않을 수 있습니다.  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]계약 및 다른 핵심 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 개념 참조 [기본적인 Windows Communication Foundation 개념](../../../../docs/framework/wcf/fundamental-concepts.md)합니다. 이 항목에서는 서비스 계약을 이해하는 데 중점을 둡니다. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]서비스를 사용 하는 클라이언트를 구축 하는 방법으로 서비스에 연결 하 계약 [WCF 클라이언트 개요](../../../../docs/framework/wcf/wcf-client-overview.md)합니다. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]클라이언트 채널, 클라이언트 아키텍처 및 기타 클라이언트 문제 참조 [클라이언트](../../../../docs/framework/wcf/feature-details/clients.md)합니다.  
  
## <a name="overview"></a>개요  
 이 항목에서는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스를 디자인하고 구현하기 위한 높은 수준의 개념적 기본 과정을 제공합니다. 특정 디자인 및 구현에 대한 자세한 내용은 하위 항목에서 제공됩니다. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응용 프로그램을 디자인하고 구현하기 전에 다음 사항에 대해 이해하는 것이 좋습니다.  
  
-   서비스 계약에 대한 정의, 작동 방식 및 생성 방법  
  
-   런타임 구성 또는 호스팅 환경에서 지원되지 않을 수 있는 계약 상태 최소 요구 사항  
  
## <a name="service-contracts"></a>서비스 계약  
 서비스 계약은 다음에 대한 정보를 제공하는 문입니다.  
  
-   한 서비스로 작업 그룹화  
  
-   교환되는 메시지와 관련된 작업 서명  
  
-   이러한 메시지의 데이터 형식  
  
-   작업의 위치  
  
-   서비스와의 통신을 지원하는 데 사용되는 특정 프로토콜 및 serialization 형식  
  
 예를 들어 구매 주문 계약에는 주문 정보 유형에 대한 입력을 수락하고 주문 식별자를 비롯한 성공 또는 실패 정보를 반환하는 `CreateOrder` 작업이 포함될 수 있습니다. 또한 주문 식별자를 수락하고 주문 상태 정보를 반환하는 `GetOrderStatus` 작업이 포함될 수 있습니다. 이러한 종류의 서비스 계약에서는 다음을 지정합니다.  
  
-   `CreateOrder` 및 `GetOrderStatus` 작업으로 구성된 구매 주문 계약  
  
-   입력 메시지와 출력 메시지를 지정한 작업  
  
-   이러한 메시지에서 전달할 수 있는 데이터  
  
-   메시지를 처리하는 데 필요한 통신 인프라에 대한 범주별 문 (예: 통신을 위해 보안이 필요한지 여부 및 필요한 보안 양식 등에 대한 세부 사항)  
  
 이러한 종류의 다른 플랫폼 (포함 하 여 Microsoft가 아닌 타사 플랫폼) 응용 프로그램에 정보를 전달 하기 위해 XML 서비스 계약은 공개적으로에서 표현 되는 표준 XML 형식 등 [WSDL 웹 서비스 설명 언어 ()](http://go.microsoft.com/fwlink/?LinkId=87004) 및 [XSD (XML 스키마)](http://go.microsoft.com/fwlink/?LinkId=87005), 등입니다. 여러 플랫폼의 개발자의 경우 언어 사양에 대해 이해하고 있고 이러한 언어는 서비스에서 지원하는 공용 양식, 형식 및 프로토콜에 대해 기술함으로써 상호 운용이 가능하도록 디자인되어 있으므로, 개발자는 이러한 공개 계약 정보를 사용하여 서비스와 통신할 수 있는 응용 프로그램을 만들 수 있습니다. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]어떻게 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 핸들이 종류의 정보를 참조 [메타 데이터](../../../../docs/framework/wcf/feature-details/metadata.md)합니다.  
  
 그러나 계약은 여러 방식으로 표현할 수 있습니다. WSDL 및 XSD는 액세스 가능한 방식으로 서비스를 기술하는 뛰어난 언어인 반면 직접 사용하기에 어렵고 서비스 계약 구현이 아닌 서비스에 대해서만 기술하는 언어입니다. 따라서 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응용 프로그램에서는 관리되는 특성, 인터페이스 및 클래스를 사용하여 서비스 구조를 정의하고 서비스를 구현합니다.  
  
 관리 되는 형식에 정의 되어 만들어진 계약은 변환 될 수 있습니다 (호출 또한 *내보낸*) 메타 데이터로-WSDL 및 XSD-클라이언트나 특히 다른 플랫폼에서 다른 서비스 구현자에서 필요로 하는 경우. 이를 통해 모든 클라이언트 응용 프로그램에 대해 공용 메타데이터를 사용하여 기술할 수 있는 간단한 프로그래밍 모델이 만들어집니다. 기본 SOAP 메시지, 전송 및 보안 관련 정보 등에 대한 세부 사항은 서비스 계약 형식 시스템으로의 변환 및 서비스 계약 형식 시스템에서 XML 형식 시스템으로의 필요한 변환이 자동으로 수행되는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에 남겨질 수 있습니다.  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]디자인 계약 참조 [서비스 계약 디자인](../../../../docs/framework/wcf/designing-service-contracts.md)합니다. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]참조 계약을 구현, [서비스 계약 구현](../../../../docs/framework/wcf/implementing-service-contracts.md)합니다.  
  
 또한 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서는 서비스 계약을 완전히 메시지 수준에서 개발하는 기능을 제공합니다. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]메시지 수준에서 개발할 때는 서비스 계약 참조 [메시지 계약을 사용 하 여](../../../../docs/framework/wcf/feature-details/using-message-contracts.md)합니다. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]SOAP XML이 아닌, 서비스를 개발, 참조 [POX 응용 프로그램과 상호 운용](../../../../docs/framework/wcf/feature-details/interoperability-with-pox-applications.md)합니다.  
  
### <a name="understanding-the-hierarchy-of-requirements"></a>요구 사항 계층 구조 이해  
 서비스 계약에서는 작업을 그룹화하고 MEP, 메시지 유형 및 메시지에서 전달하는 데이터 형식을 지정합니다. 또한 계약을 지원하기 위해 구현에 포함되어야 하는 런타임 동작의 범주를 나타냅니다(예: 메시지 암호화 및 서명을 요구할 수 있음). 그러나 서비스 계약 자체에서는 이러한 요구 사항이 어떻게 부합되는지 자세히 지정하지 않고 부합되어야 한다는 점만 지정합니다. 암호화 유형이나 메시지 서명 방법은 규격 서비스의 구현 및 구성에 따라 결정됩니다.  
  
 동작을 추가하기 위해 계약에서 런타임 구성 및 서비스 계약 구현의 특정 부분을 요구하는 방식에 유의해야 합니다. 사용할 서비스 노출을 위해 부합해야 하는 요구 사항은 이전의 요구 사항을 바탕으로 합니다. 계약에서 구현에 대한 요구 사항을 정하는 경우에는, 구현에서 서비스 실행을 위한 바인딩 및 구성을 더욱 많이 요구할 수 있습니다. 또한 호스트 응용 프로그램에서도 서비스 구성 및 바인딩을 통해 추가된 모든 요구 사항을 지원해야 합니다.  
  
 이러한 추가 요구 사항 프로세스는 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 서비스 응용 프로그램을 디자인, 구현, 구성 및 호스트하는 동안 유념해야 합니다. 예를 들어 세션 지원이 필요함을 계약에서 지정할 수 있습니다. 이 경우, 해당 계약 요구 사항을 지원하도록 바인딩을 구성해야 하며 그렇지 않으면 서비스 구현이 이루어지지 않습니다. 또는 통합 Windows 인증을 요구하는 서비스가 IIS(인터넷 정보 서비스)에서 호스트되는 경우 해당 서비스가 있는 웹 응용 프로그램에는 통합 Windows 인증을 사용하도록 설정되고 익명 지원은 해제되어야 합니다. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]참조 하는 기능 및 다른 서비스 호스트 응용 프로그램 유형의 영향 [호스팅](../../../../docs/framework/wcf/feature-details/hosting.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [끝점: 주소, 바인딩 및 계약](../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)  
 [서비스 계약 디자인](../../../../docs/framework/wcf/designing-service-contracts.md)  
 [서비스 계약 구현](../../../../docs/framework/wcf/implementing-service-contracts.md)
