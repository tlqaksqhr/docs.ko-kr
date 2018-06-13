---
title: Windows Communication Foundation 채택
ms.date: 03/30/2017
ms.assetid: 49ba71e2-9468-4082-84c5-cf8daf95e34a
ms.openlocfilehash: bcd6543e6cd47dc723b308acebec6f492fa14fb1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33489133"
---
# <a name="adopting-windows-communication-foundation"></a>Windows Communication Foundation 채택
ASP.NET을 사용 하 여 개발을 계속 기존 응용 프로그램 유지 관리 하는 동안 새로운 개발에 대 한 Windows Communication Foundation (WCF)를 사용할 수 있습니다. WCF는 모든 시나리오에서.NET Framework로 빌드된 응용 프로그램과 통신을 지 원하는 가장 적합 한 선택 하도록 만들어졌으므로 역할을 다양 한 방식으로 소프트웨어 통신 문제를 해결 하기 위한 표준 도구로 해당 ASP.NET 할 수 없습니다.  
  
 새 WCF 응용 프로그램은 기존의 ASP.NET 웹 서비스와 동일한 컴퓨터에 배포할 수 있습니다. 기존 ASP.NET 웹 서비스의.NET Framework 버전 2.0 이전 버전을 사용 하는 경우 선택적으로는 새 WCF 응용 프로그램을 호스트할 수은 IIS 응용 프로그램에.NET Framework 2.0을 배포 하는 ASP.NET IIS 등록 도구를 사용할 수 있습니다. 해당 도구에 설명 되어 [ASP.NET IIS 등록 도구 (Aspnet_regiis.exe)](http://go.microsoft.com/fwlink/?LinkId=94687), IIS 6.0 관리 콘솔에 사용자 인터페이스를 구현 합니다.  
  
 WCF 기존 ASP.NET 웹 서비스 응용 프로그램 IIS에서 ASP.NET 호환 모드에서 실행 되도록 구성 하는 WCF 서비스를 추가 하 여 기존 ASP.NET 웹 서비스에 새 기능 추가 데 사용할 수 있습니다. ASP.NET 호환성 모드로 인해 새 WCF 서비스에 대 한 코드에 액세스 하 고 업데이트할 수 기존 ASP.NET 코드와 동일한 응용 프로그램 상태 정보를 사용 하 여는 <xref:System.Web.HttpContext> 클래스입니다. 또한 응용 프로그램은 동일한 클래스 라이브러리를 공유할 수도 있습니다.  
  
 WCF 클라이언트는 ASP.NET 웹 서비스를 사용할 수 있습니다. 으로 구성 된 WCF 서비스는 <xref:System.ServiceModel.BasicHttpBinding> ASP.NET 웹 서비스 클라이언트에서 사용할 수 있습니다. ASP.NET 웹 서비스는 WCF 응용 프로그램을 함께 존재할 수 있습니다 및 기능을 추가할 기존 ASP.NET 웹 서비스에도 WCF를 사용할 수 있습니다. 모든는 WCF 및 ASP.NET 웹 서비스 함께 사용할 수 있습니다 이러한 방법을 제공, WCF 및 하지 ASP.NET 웹 서비스에서 제공 하는 기능이 필요한 경우에 ASP.NET 웹 서비스를 WCF로 마이그레이션 하려는 수 있습니다.  
  
 그러나 이러한 기능이 필요한 경우일지라도 몇몇 경우에는 특정 기술에서 다른 기술로 코드 마이그레이션하는 작업이 적절한 접근 방식이 아닐 수 있으므로 신중하게 고려해야 합니다. 새 기술을 채택하는 이유는 이전 기술로는 충족할 수 없는 새 요구 사항을 충족하기 위한 것이며, 이러한 경우 올바른 수행 작업은 새롭게 확장된 요구 사항 집합을 충족할 새 해결 방법을 디자인하는 것입니다. 새롭게 디자인할 경우 기존 시스템에 대한 사용자 경험과 시스템이 디자인된 이후 얻은 지식을 활용할 수 있습니다. 또한 새 플랫폼에서 기존 디자인을 재현하지 않고 새 기술의 전체 기능을 사용할 수도 있습니다. 새 디자인의 주요 요소를 프로토타입화하면 새 시스템 내에서 기존 시스템의 코드를 쉽게 다시 사용할 수 있습니다.  
  
 몇몇 경우에는 ASP.NET 웹 서비스에서 WCF로 이식 하는 경우 올바른 솔루션은 이며 다음 섹션 진행 방법에 대해 몇 가지 지침을 제공 합니다. 서비스 마이그레이션 및 클라이언트 마이그레이션 방법에 대한 정보가 포함되어 있습니다.  
  
 기존 ASP.NET 웹 서비스를 WCF로 마이그레이션하는 방법에 대 한 전체 분석을 참조 하십시오 [ASP.NET 웹 서비스와 Windows Communication Foundation](http://go.microsoft.com/fwlink/?LinkID=71761)합니다. 이 섹션에서는 ASP.NET 웹 서비스에 대 한 메타 데이터에서 규격 WCF 서비스를 구현 하는 방법 및 ASP.NET 웹 서비스 및 클라이언트 코드를 WCF로 마이그레이션하는 방법을 설명 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [방법: 메타데이터 검색 및 규격 서비스 구현](../../../../docs/framework/wcf/feature-details/how-to-retrieve-metadata-and-implement-a-compliant-service.md)  
 [방법: ASP.NET 웹 서비스 코드를 Windows Communication Foundation으로 마이그레이션](../../../../docs/framework/wcf/feature-details/migrate-asp-net-web-service-to-wcf.md)  
 [방법: ASP.NET 웹 서비스 클라이언트 코드를 Windows Communication Foundation으로 마이그레이션](../../../../docs/framework/wcf/feature-details/migrate-asp-net-web-service-client-to-wcf.md)
