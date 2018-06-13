---
title: ASP.NET 웹 서비스를 WCF로 마이그레이션
ms.date: 03/30/2017
ms.assetid: 1adbb931-f0b1-47f3-9caf-169e4edc9907
ms.openlocfilehash: 7d43c66952d17a91e38ae1b086478b9416321b8a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33494564"
---
# <a name="migrating-aspnet-web-services-to-wcf"></a>ASP.NET 웹 서비스를 WCF로 마이그레이션
ASP.NET은 .NET Framework 클래스 라이브러리 및 웹 서비스 빌드를 위한 도구뿐 아니라 인터넷 정보 서비스(IIS) 내 호스팅 서비스에 대한 기능도 제공합니다. Windows Communication Foundation (WCF)는.NET Framework 클래스 라이브러리, 도구 및 웹 서비스에서 사용 된 프로토콜을 사용 하 여 통신 하도록 소프트웨어 엔터티를 사용 하도록 설정 하기 위한 호스팅 기능을 제공 합니다.  WCF로 마이그레이션 ASP.NET 웹 서비스에는 새로운 기능 및 WCF에 고유한 향상 된 기능을 활용 하도록 응용을 프로그램 수 있습니다.  
  
 WCF에 ASP.NET 웹 서비스를 기준으로 하는 몇 가지 중요 한 이점이 있습니다. 웹 서비스를 구축에 대해서만 ASP.NET 웹 서비스 도구 이지만, WCF 소프트웨어 엔터티 수 있는 다른 노드와 통신할 때 사용할 수 있는 도구를 제공 합니다. 따라서 여러 소프트웨어 통신 시나리오를 적용하는 데 개발자가 알아야 하는 기술의 수가 적어지기 때문에 결과적으로는 소프트웨어 개발 프로젝트를 완료하는 데 필요한 시간뿐 아니라 소프트웨어 개발 리소스 비용을 줄일 수 있습니다.  
  
 웹 서비스 개발 프로젝트에 대해서도 WCF ASP.NET 웹 서비스 지원 보다 더 많은 웹 서비스 프로토콜을 지원합니다. 이러한 추가 프로토콜은 무엇보다도 신뢰할 수 있는 세션 및 트랜잭션이 사용되는 더욱 정교한 솔루션을 제공합니다.  
  
 WCF는 ASP.NET 웹 서비스 보다 메시지 전송에 대 한 프로토콜을 지원 합니다. ASP.NET 웹 서비스는 HTTP(Hypertext Transfer Protocol)를 사용하여 메시지 보내기만 지원합니다. WCF는 전송 TCP (Control Protocol), 명명 된 파이프, Microsoft 메시지 큐 (MSMQ) 뿐 아니라 HTTP를 사용 하 여 메시지 보내기를 지원 합니다. 더 중요 한 WCF 추가 전송 프로토콜을 지원 하도록 확장할 수 있습니다. 따라서 WCF를 사용 하 여 개발 된 소프트웨어가 다른 소프트웨어와 있으므로 잠재적 투자 수익률 보다 광범위 한 작업을 수 있습니다.  
  
 WCF 배포 하기 위한 많은 다양 한 기능을 제공 하 고 제공 ASP.NET 웹 서비스 보다 응용 프로그램을 관리 합니다. WCF 구성 시스템을 제공 하는 ASP.NET, 외에도 구성 편집기를 제공 수신기 및 매개자, 추적 뷰어, 메시지 로깅, vast 수의 성능 카운터의 수에 관계 없이 다시 보낸 사람 으로부터 동작 추적 및 Windows Management Instrumentation을 지원 합니다.  
  
 를 사용 하는 몇 가지 옵션이 ASP.NET 웹 서비스 사용을 고려 하는 경우 이러한 잠재적 이점을의 ASP.NET 웹 기준으로 WCF 서비스를 가정 합니다.  
  
-   ASP.NET 웹 서비스를 사용 하는 WCF에서 제공 하는 이점을 계속 있습니다.  
  
-   WCF에서 몇 가지 미래 시간을 채택 하기 위해 ASP.NET 웹 서비스를 계속 사용 합니다. 이 섹션의 항목에는 향후 WCF 응용 프로그램 함께 새로운 ASP.NET 웹 서비스 응용 프로그램을 사용할 수에 대 한 가능성을 최대화 하는 방법을 설명 합니다. 이 섹션의 항목에는 또한 새로운 ASP.NET 웹 손쉽게 WCF로 마이그레이션하려는 서비스를 빌드하는 방법을 설명 합니다. 그러나 서비스 보안이 중요 하거나 신뢰성 또는 트랜잭션 보증이 필요 하거나 사용자 지정 하는 경우 관리 기능을 생성 해야 다음 WCF를 채택 하는 편이 더 나은지는 합니다. WCF는 이런 시나리오에 정확 하 게 설계 되었습니다.  
  
-   WCF 계속 기존 ASP.NET 웹 서비스 응용 프로그램 유지 관리 하면서 새 개발 작업에 적용 합니다. 이 선택이 최선의 선택일 가능성이 큽니다. 수정 사용 하도록 기존 응용 프로그램의 비용을 절약 하는 동안 WCF의 혜택을 생성 합니다. 이 시나리오에서는 WCF 응용 프로그램을 새 기존 ASP.NET 응용 프로그램에서 공존할 수 있습니다. 새 WCF 응용 프로그램은 기존의 ASP.NET 웹 서비스를 사용할 수 및 WCF를 사용 하 여 새 작업 기능을 통해 WCF ASP.NET 호환 모드 기존 ASP.NET 응용 프로그램을 프로그래밍할 수 있습니다.  
  
-   WCF를 채택 하 고 기존 ASP.NET 웹 서비스 응용 프로그램을 WCF로 마이그레이션. WCF에서 제공 하는 기능으로 기존 응용 프로그램을 향상 시키기 위해 하거나 새로운 내에서 기존 ASP.NET 웹 서비스의 기능, 더욱 강력한 WCF 응용 프로그램을 재현 하려면이 옵션을 선택할 수 있습니다.  
  
> [!NOTE]
>  WCF 서비스를 호스팅하는 경우 주의 해야 iis 5.x ASP.NET을 제거 합니다. WCF 서비스가 IIS에서 호스트 된 경우 ASP.NET을 제거 하는 경우에 5.x 서비스에 대 한 코드를 요청할 수 있습니다. IIS를 실행 하는 운영 체제에서 ASP.NET을 제거 하는 경우 5.x 및 WCF가 제거 하 고.svc 확장명을 가진 파일이 텍스트 파일로 간주 되어 소스 코드를 포함 하 여 내용을 요청자에 게 반환 됩니다.  
  
 이 섹션에서에서 이러한 옵션에 설명 하 고 ASP.NET 웹 서비스와 WCF 비교 하 여 ASP.NET 웹 서비스 코드를 WCF로 마이그레이션하는 방법에 대해 설명 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Windows Communication Foundation 채택 예상: 이후의 마이그레이션을 용이하게 함](../../../../docs/framework/wcf/feature-details/anticipating-adopting-wcf-migration.md)  
 [Windows Communication Foundation 채택 예상: 이후의 통합을 용이하게 함](../../../../docs/framework/wcf/feature-details/anticipating-adopting-the-wcf-easing-future-integration.md)  
 [Windows Communication Foundation 채택](../../../../docs/framework/wcf/feature-details/adopting-wcf.md)  
 [용도와 사용되는 표준을 기반으로 ASP.NET 웹 서비스와 WCF 비교](../../../../docs/framework/wcf/feature-details/comparing-aspnet-web-services-to-wcf-based-on-purpose-and-standards-used.md)  
 [개발을 기반으로 ASP.NET 웹 서비스와 WCF 비교](../../../../docs/framework/wcf/feature-details/comparing-aspnet-web-services-to-wcf-based-on-development.md)
