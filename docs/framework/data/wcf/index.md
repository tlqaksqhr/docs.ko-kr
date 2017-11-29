---
title: WCF Data Services 4.5
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Astoria
- WCF Data Services, getting started
ms.assetid: 73d2bec3-7c92-4110-b905-11bb0462357a
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d1ef95ac84872b2cc39ec3a93abab10c39cd7738
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="wcf-data-services-45"></a>WCF Data Services 4.5
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)](이전의 “ADO.NET Data Services”)는 [REST(Representational State Transfer)](http://go.microsoft.com/fwlink/?LinkId=113919)의 의미 체계를 사용하여 웹 또는 인트라넷을 통해 데이터를 노출하고 사용하기 위해 [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)]을 사용하는 서비스를 만들 수 있도록 하는 .NET Framework의 구성 요소입니다. [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]는 URI로 주소를 지정할 수 있는 리소스로 데이터를 노출합니다. 데이터는 표준 HTTP 동사인 GET, PUT, POST 및 DELETE를 사용하여 액세스되고 변경됩니다. [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]는 [엔터티 데이터 모델](../../../../docs/framework/data/adonet/entity-data-model.md)의 엔터티-관계 규칙을 사용하여 리소스를 연결로 관련된 엔터티 집합으로 노출합니다.  
  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]는 리소스 주소 지정 및 업데이트를 위해 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 프로토콜을 사용합니다. 이를 통해 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]를 지원하는 모든 클라이언트에서 이러한 서비스에 액세스할 수 있습니다. [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]를 사용하면 XML로 데이터를 교환 및 업데이트하기 위한 표준 집합인 Atom, AJAX 응용 프로그램에서 광범위하게 사용되는 텍스트 기반 데이터 교환 형식인 JSON(JavaScript Object Notation) 등 잘 알려진 전송 형식을 사용하여 리소스를 요청하고 리소스에 데이터를 쓸 수 있습니다.  
  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]에서는 다양한 원본에서 제공되는 데이터를 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 피드로 노출할 수 있습니다. Visual Studio 도구를 사용하면 ADO.NET Entity Framework 데이터 모델을 사용하여 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 기반 서비스를 보다 쉽게 만들 수 있습니다. 또한 CLR(공용 언어 런타임) 클래스와 런타임에 바인딩된 데이터나 형식화되지 않은 데이터를 기반으로 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 피드를 만들 수 있습니다.  
  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]에는 일반 .NET Framework 클라이언트 응용 프로그램용 라이브러리와 Silverlight 기반 응용 프로그램용 라이브러리 등 클라이언트 라이브러리 집합도 포함되어 있습니다. 이러한 클라이언트 라이브러리는 .NET Framework 및 Silverlight와 같은 환경에서 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 피드에 액세스할 때 개체 기반 프로그래밍 모델을 제공합니다.  
  
## <a name="where-should-i-start"></a>시작 지점  
 가장 관심이 있는 항목에 따라 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]에 대한 다음 항목 중 하나에서 시작하는 것이 좋습니다.  
  
 바로 시작  
 -   [빠른 시작](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)  
  
-   [시작](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md)  
  
-   [Silverlight 빠른 시작](http://go.microsoft.com/fwlink/?LinkID=192782)  
  
-   [Windows Phone 개발을 위한 Silverlight 빠른 시작](http://go.microsoft.com/fwlink/?LinkID=214535)  
  
 코드 보기  
 -   [빠른 시작](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)  
  
-   [방법: 데이터 서비스 쿼리 실행](../../../../docs/framework/data/wcf/how-to-execute-data-service-queries-wcf-data-services.md)  
  
-   [방법: Windows Presentation Foundation 요소에 데이터 바인딩](../../../../docs/framework/data/wcf/bind-data-to-wpf-elements-wcf-data-services.md)  
  
 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]에 대한 자세한 정보  
 -   [백서: OData 소개](http://go.microsoft.com/fwlink/?LinkId=220867)  
  
-   [Open Data Protocol 웹 사이트](http://go.microsoft.com/fwlink/?LinkID=184554)  
  
-   [OData: SDK](http://go.microsoft.com/fwlink/?LinkID=185248)  
  
-   [OData: 질문과 대답](http://go.microsoft.com/fwlink/?LinkId=185867)  
  
 비디오 보기  
 -   [WCF Data Services 초보자 가이드](http://go.microsoft.com/fwlink/?LinkId=220864)  
  
-   [WCF Data Services 개발자 비디오](http://go.microsoft.com/fwlink/?LinkId=220861)  
  
-   [OData: 개발자 웹 사이트](http://go.microsoft.com/fwlink/?LinkId=185866)  
  
 종단 간 샘플  
 -   [MSDN 샘플 갤러리의 WCF Data Services 설명서 샘플](http://go.microsoft.com/fwlink/?LinkID=220865)  
  
-   [MSDN 샘플 갤러리의 기타 WCF Data Services 샘플](http://go.microsoft.com/fwlink/?LinkId=220866)  
  
-   [OData: SDK](http://go.microsoft.com/fwlink/?LinkID=185248)  
  
 Visual Studio와의 통합 방식  
 -   [데이터 서비스 클라이언트 라이브러리 생성](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md)  
  
-   [데이터 서비스 만들기](../../../../docs/framework/data/wcf/creating-the-data-service.md)  
  
-   [Entity Framework 공급자](../../../../docs/framework/data/wcf/entity-framework-provider-wcf-data-services.md)  
  
 수행 가능 작업  
 -   [개요](../../../../docs/framework/data/wcf/wcf-data-services-overview.md)  
  
-   [백서: OData 소개](http://go.microsoft.com/fwlink/?LinkId=220867)  
  
-   [응용 프로그램 시나리오](../../../../docs/framework/data/wcf/application-scenarios-wcf-data-services.md)  
  
 Silverlight 사용  
 -   [Silverlight 빠른 시작](http://go.microsoft.com/fwlink/?LinkID=192782)  
  
-   [WCF Data Services(Silverlight)](http://go.microsoft.com/fwlink/?LinkID=143149)  
  
-   [Silverlight 시작](http://go.microsoft.com/fwlink/?LinkId=148366)  
  
 Windows Phone 응용 프로그램 만들기  
 -   [Windows Phone 개발을 위한 Silverlight 빠른 시작](http://go.microsoft.com/fwlink/?LinkID=214535)  
  
-   [Windows Phone용 OData(Open Data Protocol) 클라이언트](http://go.microsoft.com/fwlink/?LinkID=208749)  
  
 LINQ 사용  
 -   [데이터 서비스 쿼리](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md)  
  
-   [LINQ 고려 사항](../../../../docs/framework/data/wcf/linq-considerations-wcf-data-services.md)  
  
-   [방법: 데이터 서비스 쿼리 실행](../../../../docs/framework/data/wcf/how-to-execute-data-service-queries-wcf-data-services.md)  
  
 추가 정보  
 -   [WCF Data Services 팀 블로그](http://go.microsoft.com/fwlink/?LinkID=150511)  
  
-   [리소스](../../../../docs/framework/data/wcf/wcf-data-services-resources.md)  
  
-   [WCF Data Services 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=220868)  
  
-   [Open Data Protocol 웹 사이트](http://go.microsoft.com/fwlink/?LinkID=184554)  
  
## <a name="in-this-section"></a>단원 내용  
 [개요](../../../../docs/framework/data/wcf/wcf-data-services-overview.md)  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]에서 사용할 수 있는 기능에 대한 개요를 제공합니다.  
  
 [WCF Data Services의 새로운 기능](http://msdn.microsoft.com/en-us/cf22cad5-b8d9-472b-8d7c-b863b64eaae8)  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]의 새로운 기능과 새로운 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 기능의 지원에 대해 설명합니다.  
  
 [시작](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md)  
 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]를 사용하여 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] 피드를 노출하고 사용하는 방법에 대해 설명합니다.  
  
 [WCF Data Services 정의](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)  
 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 피드를 노출하는 데이터 서비스를 만들고 구성하는 방법에 대해 설명합니다.  
  
 [WCF Data Services 클라이언트 라이브러리](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)  
 클라이언트 라이브러리를 통해 .NET Framework 클라이언트 응용 프로그램에서 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 피드를 사용하는 방법에 대해 설명합니다.  
  
## <a name="see-also"></a>참고 항목  
 [REST(Representational State Transfer)](http://go.microsoft.com/fwlink/?LinkId=113919)
