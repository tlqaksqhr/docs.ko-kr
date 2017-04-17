---
title: "데이터를 서비스로 노출(WCF Data Services) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-oob"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "시작, WCF Data Services"
  - "WCF Data Services, 구성"
  - "WCF Data Services, 시작"
ms.assetid: df0bbcee-f66f-4a88-abb4-4e73c8b9c908
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# 데이터를 서비스로 노출(WCF Data Services)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]는 Visual Studio와 통합되므로 데이터를 [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] 피드로 노출하는 서비스를 보다 쉽게 정의할 수 있습니다.  [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 피드를 노출하는 데이터 서비스를 만들려면 다음 기본 단계를 수행해야 합니다.  
  
1.  **데이터 모델** **정의**.  [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]는 [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md)를 기반으로 하는 데이터 모델을 기본적으로 지원합니다.  자세한 내용은 [방법: ADO.NET Entity Framework 데이터 원본을 사용하여 데이터 서비스 만들기](../../../../docs/framework/data/wcf/create-a-data-service-using-an-adonet-ef-data-wcf.md)을 참조하세요.  
  
     또한 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]는 <xref:System.Linq.IQueryable%601> 인터페이스 인스턴스를 반환하는 CLR\(공용 언어 런타임\) 개체를 기반으로 하는 데이터 모델을 지원합니다.  이렇게 하면 .NET Framework의 목록, 어레이 및 컬렉션에 기반하여 데이터 서비스를 배포할 수 있습니다. 이러한 데이터 구조에 생성, 업데이트 및 삭제 작업을 활성화하려면 <xref:System.Data.Services.IUpdatable> 인터페이스도 구현해야 합니다.  자세한 내용은 [방법: 리플렉션 공급자를 사용하여 데이터 서비스 만들기](../../../../docs/framework/data/wcf/create-a-data-service-using-rp-wcf-data-services.md)을 참조하세요.  
  
     고급 시나리오를 위해 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]에 포함된 공급자 집합을 사용하면 런타임에 바인딩된 데이터 형식을 기반으로 데이터 모델을 정의할 수 있습니다.  자세한 내용은 [사용자 지정 데이터 서비스 공급자](../../../../docs/framework/data/wcf/custom-data-service-providers-wcf-data-services.md)을 참조하세요.  
  
2.  **데이터 서비스를 만듭니다.** 가장 기본적인 데이터 서비스는 <xref:System.Data.Services.DataService%601> 클래스에서 상속하는 클래스를 엔터티 컨테이너의 네임스페이스로 정규화된 이름인 `T` 형식으로 노출합니다.  자세한 내용은 [WCF Data Services 정의](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)을 참조하세요.  
  
3.  **데이터 서비스 구성.**기본적으로 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]는 엔터티 컨테이너에 의해 노출되는 리소스에 대한 액세스를 비활성화합니다. <xref:System.Data.Services.DataServiceConfiguration> 인터페이스를 사용하면 리소스 및 서비스 작업을 구성 및 액세스하고, 지원되는 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 버전을 지정하고, 단일 응답에서 반환될 수 있는 최대 엔터티 수, 일괄 처리 동작과 같은 기타 서비스 전체 동작을 정의할 수 있습니다. 자세한 내용은 [데이터 서비스 구성](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md)을 참조하세요.  
  
 Northwind 샘플 데이터베이스를 기반으로 하는 간단한 데이터 서비스를 만드는 방법의 예제는 [빠른 시작](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)를 참조하세요.  
  
## 참고 항목  
 [시작](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md)   
 [개요](../../../../docs/framework/data/wcf/wcf-data-services-overview.md)