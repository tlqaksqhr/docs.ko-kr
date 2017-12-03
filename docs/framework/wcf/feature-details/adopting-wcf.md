---
title: "Windows Communication Foundation 채택"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 49ba71e2-9468-4082-84c5-cf8daf95e34a
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e27ee5f2e1b2ad042fd8c0104e89b99eb5e4bc96
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="adopting-windows-communication-foundation"></a>Windows Communication Foundation 채택
ASP.NET을 사용하여 개발된 기존 응용 프로그램을 계속 유지 관리하면서 새 개발을 위해 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]를 사용하도록 선택할 수 있습니다. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 모든 시나리오에서 .NET Framework로 빌드된 응용 프로그램과 통신을 용이하게 하기 위한 가장 적절한 선택이며 ASP.NET이 해결할 수 없는 광범위한 소프트웨어 통신 문제 해결을 위한 표준 도구로써 역할을 수행할 수 있습니다.  
  
 새 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응용 프로그램을 기존의 ASP.NET 웹 서비스와 동일한 시스템에 배포할 수 있습니다. 기존의 ASP.NET 웹 서비스가 2.0 이전 버전의 .NET Framework를 사용하는 경우 ASP.NET IIS 등록 도구를 사용하여 .NET Framework 2.0을 새 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응용 프로그램을 호스팅할 IIS 응용 프로그램에 선택적으로 배포할 수 있습니다. 해당 도구에 설명 되어 [ASP.NET IIS 등록 도구 (Aspnet_regiis.exe)](http://go.microsoft.com/fwlink/?LinkId=94687), IIS 6.0 관리 콘솔에 사용자 인터페이스를 구현 합니다.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 ASP.NET 호환성 모드에서 실행하도록 구성된 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스를 IIS의 기존 ASP.NET 웹 서비스 응용 프로그램에 추가하여 새 기능을 기존 ASP.NET 웹 서비스에 추가하는 데 사용할 수 있습니다. ASP.NET 호환성 모드로 인해 새 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스 코드는 <xref:System.Web.HttpContext> 클래스를 사용하여 기존 ASP.NET 코드와 동일한 응용 프로그램 상태 정보에 액세스하고 업데이트할 수 있습니다. 또한 응용 프로그램은 동일한 클래스 라이브러리를 공유할 수도 있습니다.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트는 ASP.NET 웹 서비스를 사용할 수 있습니다. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]을 사용하여 구성한 <xref:System.ServiceModel.BasicHttpBinding> 서비스는 ASP.NET 웹 서비스 클라이언트에서 사용할 수 있습니다. ASP.NET 웹 서비스는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응용 프로그램과 함께 사용할 수 있으며 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 기존 ASP.NET 웹 서비스에 기능을 추가하는 데에도 사용할 수 있습니다. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 및 ASP.NET 웹 서비스를 함께 사용할 수 있도록 이러한 모든 방법을 제공하면 ASP.NET 웹 서비스가 아닌 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 제공하는 기능이 필요할 때에만 ASP.NET 웹 서비스를 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에 마이그레이션해야 하는 경우가 있습니다.  
  
 그러나 이러한 기능이 필요한 경우일지라도 몇몇 경우에는 특정 기술에서 다른 기술로 코드 마이그레이션하는 작업이 적절한 접근 방식이 아닐 수 있으므로 신중하게 고려해야 합니다. 새 기술을 채택하는 이유는 이전 기술로는 충족할 수 없는 새 요구 사항을 충족하기 위한 것이며, 이러한 경우 올바른 수행 작업은 새롭게 확장된 요구 사항 집합을 충족할 새 해결 방법을 디자인하는 것입니다. 새롭게 디자인할 경우 기존 시스템에 대한 사용자 경험과 시스템이 디자인된 이후 얻은 지식을 활용할 수 있습니다. 또한 새 플랫폼에서 기존 디자인을 재현하지 않고 새 기술의 전체 기능을 사용할 수도 있습니다. 새 디자인의 주요 요소를 프로토타입화하면 새 시스템 내에서 기존 시스템의 코드를 쉽게 다시 사용할 수 있습니다.  
  
 ASP.NET 웹 서비스에서 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]로 이식하는 것이 올바른 해결 방법인 일부 경우에 대해 다음 단원에서 처리하는 방법과 관련된 몇 가지 지침을 제공합니다. 서비스 마이그레이션 및 클라이언트 마이그레이션 방법에 대한 정보가 포함되어 있습니다.  
  
 기존 ASP.NET 웹 서비스를 WCF로 마이그레이션하는 방법에 대 한 전체 분석을 참조 하십시오 [ASP.NET 웹 서비스와 Windows Communication Foundation](http://go.microsoft.com/fwlink/?LinkID=71761)합니다. 이 단원에서는 ASP.NET 웹 서비스의 메타데이터에서 호환되는 WCF 서비스를 구현하는 방법 및 ASP.NET 웹 서비스와 클라이언트 코드를 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]로 마이그레이션하는 방법에 대해 설명합니다.  
  
## <a name="see-also"></a>참고 항목  
 [방법: 메타 데이터 검색 및 규격 서비스 구현](../../../../docs/framework/wcf/feature-details/how-to-retrieve-metadata-and-implement-a-compliant-service.md)  
 [방법: Windows Communication Foundation에 ASP.NET 웹 서비스 코드 마이그레이션](../../../../docs/framework/wcf/feature-details/migrate-asp-net-web-service-to-wcf.md)  
 [방법: ASP.NET 웹 서비스 클라이언트 코드를 Windows Communication Foundation으로 마이그레이션](../../../../docs/framework/wcf/feature-details/migrate-asp-net-web-service-client-to-wcf.md)
