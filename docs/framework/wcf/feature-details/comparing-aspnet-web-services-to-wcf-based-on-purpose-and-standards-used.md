---
title: "용도와 사용되는 표준을 기반으로 ASP.NET 웹 서비스와 WCF 비교"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d3890278-fa9b-4902-91ea-8da73b7143cc
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1b43fe9cf66fc9ccf72d12c6a617a1b4c0b44def
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="comparing-aspnet-web-services-to-wcf-based-on-purpose-and-standards-used"></a>용도와 사용되는 표준을 기반으로 ASP.NET 웹 서비스와 WCF 비교
ASP.NET Web 서비스는 HTTP에서 SOAP(Simple Object Access Protocol)를 사용하여 메시지를 보내고 받는 응용 프로그램을 빌드하기 위해 개발되었습니다. 메시지 구조는 XML 스키마를 사용하여 정의할 수 있으며 메시지를 .NET Framework 개체로 또는 그 반대로 쉽게 serialize하기 위한 도구가 제공됩니다. 이 기술은 자동으로 메타데이터를 생성하여 WSDL(웹 서비스 기술 언어)로 웹 서비스를 설명할 수 있으며 WSDL에서 웹 서비스용 클라이언트를 생성하기 위한 두 번째 도구가 제공됩니다.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 .NET Framework 응용 프로그램이 다른 소프트웨어 엔터티와 메시지를 교환할 수 있도록 합니다. 기본적으로 SOAP가 사용되지만 메시지는 임의의 형식일 수 있으며 모든 전송 프로토콜을 사용하여 전달할 수 있습니다. 메시지 구조는 XML 스키마를 사용하여 정의할 수 있으며 메시지를 .NET Framework 개체로 또는 그 반대로 쉽게 serialize하기 위한 다양한 옵션이 제공됩니다. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 자동으로 메타데이터를 생성하여 이 기술로 빌드된 응용 프로그램을 WSDL로 설명할 수 있습니다. 또한 WSDL에서 이러한 응용 프로그램용 클라이언트를 생성하기 위한 도구를 제공합니다.  
  
 ASP.NET 웹 서비스에서 지원 되는 표준은에 문서화 된 [XML 웹 서비스를 사용 하 여 ASP.NET을 만든](http://go.microsoft.com/fwlink/?LinkId=94872)합니다. 지 원하는 표준의 더 광범위 한 목록 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 에 나열 되어 [웹 서비스 프로토콜에서 지 원하는 시스템 제공 상호 운용성 바인딩](../../../../docs/framework/wcf/feature-details/web-services-protocols-supported-by-system-provided-interoperability-bindings.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [개발을 기반으로 ASP.NET 웹 서비스와 WCF 비교](../../../../docs/framework/wcf/feature-details/comparing-aspnet-web-services-to-wcf-based-on-development.md)
