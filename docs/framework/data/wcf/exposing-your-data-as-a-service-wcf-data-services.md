---
title: "서비스로 데이터 노출(WCF Data Services)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF Data Services, configuring
- getting started, WCF Data Services
- WCF Data Services, getting started
ms.assetid: df0bbcee-f66f-4a88-abb4-4e73c8b9c908
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 122d05d5e4bd7690f32b22453dccbfaab2fb7f13
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="exposing-your-data-as-a-service-wcf-data-services"></a>서비스로 데이터 노출(WCF Data Services)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]데이터를 노출 하는 서비스를 보다 쉽게 정의할 수 있도록 Visual Studio와 통합 되어 [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] 피드입니다. 노출 하는 데이터 서비스 만들기는 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 피드에 필요한 다음과 같은 기본 단계:  
  
1.  **정의** **데이터 모델**합니다. [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]기본적으로 기반으로 하는 데이터 모델을 지원는 [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md)합니다. 자세한 내용은 참조 [하는 방법: ADO.NET Entity Framework 데이터 소스를 사용 하 여 데이터 서비스 만들기](../../../../docs/framework/data/wcf/create-a-data-service-using-an-adonet-ef-data-wcf.md)합니다.  
  
     또한 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]는 <xref:System.Linq.IQueryable%601> 인터페이스 인스턴스를 반환하는 CLR(공용 언어 런타임) 개체를 기반으로 하는 데이터 모델을 지원합니다. 따라서 .NET Framework의 목록, 배열 및 컬렉션을 기반으로 하는 데이터 서비스를 배포할 수 있습니다. 이러한 데이터 구조에 대해 만들기, 업데이트 및 삭제 작업을 수행하려면 <xref:System.Data.Services.IUpdatable> 인터페이스도 구현해야 합니다. 자세한 내용은 참조 [하는 방법: 리플렉션 공급자를 사용 하 여 데이터 서비스 만들기](../../../../docs/framework/data/wcf/create-a-data-service-using-rp-wcf-data-services.md)합니다.  
  
     더 고급 시나리오에 대 한 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] 런타임에 바인딩된 데이터 형식을 기반으로 데이터 모델을 정의할 수 있도록 하는 공급자의 집합을 포함 합니다. 자세한 내용은 참조 [사용자 지정 데이터 서비스 공급자](../../../../docs/framework/data/wcf/custom-data-service-providers-wcf-data-services.md)합니다.  
  
2.  **데이터 서비스를 만듭니다.** 가장 기본적인 데이터 서비스는 <xref:System.Data.Services.DataService%601> 클래스에서 상속하는 클래스를 엔터티 컨테이너의 네임스페이스로 정규화된 이름인 `T` 형식으로 노출합니다. 자세한 내용은 [Defining WCF Data Services](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)의 개발 및 배포에 대한 정보를 제공합니다.  
  
3.  **데이터 서비스를 구성 합니다.** 기본적으로 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] 는 엔터티 컨테이너에 의해 노출되는 리소스에 액세스할 수 없도록 설정되어 있습니다. <xref:System.Data.Services.DataServiceConfiguration> 인터페이스를 사용하면 리소스 및 서비스 작업에 대한 액세스를 구성하고 지원되는 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 버전을 지정할 수 있으며 일괄 처리 동작 또는 단일 응답에 반환될 수 있는 최대 엔터티 수와 같은 서비스 전반적인 기타 동작을 정의할 수 있습니다. 자세한 내용은 참조 [데이터 서비스 구성](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md)합니다.  
  
 Northwind 샘플 데이터베이스를 기반으로 하는 간단한 데이터 서비스를 만드는 방법의 예제를 보려면 [퀵 스타트](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [시작](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md)  
 [개요](../../../../docs/framework/data/wcf/wcf-data-services-overview.md)
