---
title: "ASP.NET 웹 서비스를 WCF로 마이그레이션"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1adbb931-f0b1-47f3-9caf-169e4edc9907
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: e2051de2c0cef9a31337b320c347bb7d85dbadae
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="migrating-aspnet-web-services-to-wcf"></a>ASP.NET 웹 서비스를 WCF로 마이그레이션
ASP.NET은 .NET Framework 클래스 라이브러리 및 웹 서비스 빌드를 위한 도구뿐 아니라 인터넷 정보 서비스(IIS) 내 호스팅 서비스에 대한 기능도 제공합니다. [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]은 .NET Framework 클래스 라이브러리, 도구 및 호스팅 기능을 제공하여 소프트웨어 엔터티가 웹 서비스에서 사용하는 프로토콜을 포함하여 모든 프로토콜을 사용하여 통신할 수 있도록 합니다.  ASP.NET 웹 서비스를 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]로 마이그레이션하면 응용 프로그램에서 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]만의 새로운 기능 및 향상된 기능을 활용할 수 있습니다.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에는 ASP.NET 웹 서비스와 관련된 몇 가지 중요한 이점이 있습니다. ASP.NET 웹 서비스 도구는 웹 서비스를 빌드하는 데에만 사용할 수 있는 반면, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서는 소프트웨어 엔터티 간 통신을 수행해야 할 경우 사용할 수 있는 도구를 제공합니다. 따라서 여러 소프트웨어 통신 시나리오를 적용하는 데 개발자가 알아야 하는 기술의 수가 적어지기 때문에 결과적으로는 소프트웨어 개발 프로젝트를 완료하는 데 필요한 시간뿐 아니라 소프트웨어 개발 리소스 비용을 줄일 수 있습니다.  
  
 웹 서비스 개발 프로젝트의 경우에도 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서는 ASP.NET 웹 서비스보다 더 많은 웹 서비스 프로토콜을 지원합니다. 이러한 추가 프로토콜은 무엇보다도 신뢰할 수 있는 세션 및 트랜잭션이 사용되는 더욱 정교한 솔루션을 제공합니다.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서는 ASP.NET 웹 서비스보다 더 많은 메시지 전송 프로토콜을 지원합니다. ASP.NET 웹 서비스는 HTTP(Hypertext Transfer Protocol)를 사용하여 메시지 보내기만 지원합니다. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 HTTP뿐 아니라 TCP(Transmission Control Protocol), 명명된 파이프 및 MSMQ(Microsoft Message Queuing)를 사용하여 메시지를 보낼 수 있습니다. 더 중요한 것은 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]은 추가 전송 프로토콜을 지원할 수 있도록 확장할 수 있다는 점입니다. 따라서 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]로 개발된 소프트웨어는 여러 다른 소프트웨어와 함께 사용할 수 있으므로 잠재적 투자 수익을 높일 수 있습니다.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서는 ASP.NET 웹 서비스보다 더 다양한 응용 프로그램 배포 및 관리 기능을 제공합니다. ASP.NET에도 있는 구성 시스템 이외에 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서는 구성 편집기, 여러 매개자를 통해 발신자에서 수신자로의 동작 추적과 그 반대의 동작 추적, 추적 뷰어, 메시지 로깅, 다양한 성능 카운터 및 WMI(Windows Management Instrumentation) 지원 등을 제공합니다.  
  
 ASP.NET 웹 서비스와 비교하여 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]의 이러한 이점을 고려한다면 ASP.NET 웹 서비스를 현재 사용하고 있거나 사용 계획 중인 경우 다음과 같은 옵션이 있습니다.  
  
-   [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 제공하는 이점을 고려하지 않고 ASP.NET 웹 서비스를 계속 사용합니다.  
  
-   나중에 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]를 채택해 볼 것을 고려하고 ASP.NET 웹 서비스를 계속 사용합니다. 이 단원의 항목에서는 새로운 ASP.NET 웹 서비스 응용 프로그램을 나중에 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응용 프로그램과 함께 사용할 가능성을 최대화하는 방법에 대해 설명합니다. 또한 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]로 손쉽게 마이그레이션할 수 있도록 새로운 ASP.NET 웹 서비스를 빌드하는 방법에 대해서도 설명합니다. 그러나 서비스 보안이 중요하거나, 신뢰성 또는 트랜잭션 보증이 필요하거나, 사용자 지정 관리 기능을 생성해야 하는 경우 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]를 채택하는 것이 더 좋습니다. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]가 바로 이러한 시나리오에 꼭 맞게 디자인되었기 때문입니다.  
  
-   기존의 ASP.NET 웹 서비스 응용 프로그램을 계속 유지 관리하면서 새 개발을 위해 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]를 채택합니다. 이 선택이 최선의 선택일 가능성이 큽니다. WCF를 사용하기 위해 기존 응용 프로그램 수정에 필요한 비용을 절약하면서 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]의 이점은 누릴 수 있기 때문입니다. 이 시나리오의 경우 새 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응용 프로그램은 기존의 ASP.NET 응용 프로그램과 함께 사용할 수 있습니다. 새 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응용 프로그램은 기존의 ASP.NET 웹 서비스를 사용할 수 있으며, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ASP.NET 호환성 모드를 통해 새 작업 기능을 기존의 ASP.NET 응용 프로그램에 프로그래밍할 수 있습니다.  
  
-   [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]를 채택하고 기존 ASP.NET 웹 서비스 응용 프로그램을 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]로 마이그레이션합니다. 기존 응용 프로그램을 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 제공하는 기능을 사용하여 향상시키거나 더욱 강력한 새로운 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응용 프로그램 내에서 기존 ASP.NET 웹 서비스의 기능을 재현하려는 경우 적합한 선택입니다.  
  
> [!NOTE]
>  [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스가 IIS 5.x에서 호스팅될 때 ASP.NET을 제거하는 경우에는 주의해야 합니다. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스가 IIS 5.x에서 호스팅될 때 ASP.NET을 제거하는 경우 서비스 코드를 요청할 수 있습니다. IIS 5.x가 실행 중이고 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]가 제거된 운영 체제에서 ASP.NET을 제거하면 확장자가 .svc인 파일이 텍스트 파일로 간주되어 소스 코드를 포함하여 내용이 요청자에게 반환됩니다.  
  
 이 단원에서는 이러한 옵션에 대해 자세히 설명하고, ASP.NET 웹 서비스를 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]와 비교하여, ASP.NET 웹 서비스 코드를 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]로 마이그레이션하는 방법에 대한 지침을 제공합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Windows Communication Foundation 채택 예상: 이후의 마이그레이션을 용이 하 게 함](../../../../docs/framework/wcf/feature-details/anticipating-adopting-wcf-migration.md)  
 [Windows Communication Foundation 채택 예상: 이후의 통합 감속/가속](../../../../docs/framework/wcf/feature-details/anticipating-adopting-the-wcf-easing-future-integration.md)  
 [Windows Communication Foundation 채택](../../../../docs/framework/wcf/feature-details/adopting-wcf.md)  
 [WCF 기반 의도적으로 사용 되는 표준을 ASP.NET 웹 서비스 비교](../../../../docs/framework/wcf/feature-details/comparing-aspnet-web-services-to-wcf-based-on-purpose-and-standards-used.md)  
 [ASP.NET 웹 서비스 개발을 기반으로 wcf 비교](../../../../docs/framework/wcf/feature-details/comparing-aspnet-web-services-to-wcf-based-on-development.md)
