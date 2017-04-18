---
title: "데이터 서비스 클라이언트 라이브러리 생성(WCF Data Services) | Microsoft Docs"
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
  - "서비스 참조 추가 대화 상자"
  - "클라이언트 응용 프로그램, WCF Data Services"
  - "WCF Data Services, 클라이언트 라이브러리"
ms.assetid: 314077c1-ac10-47e1-bed4-940b5462359d
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# 데이터 서비스 클라이언트 라이브러리 생성(WCF Data Services)
[!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)]을를 구현하는 데이터 서비스는 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 피드에서 노출하는 데이터 모델을 설명하는 서비스 메타데이터 문서를 반환할 수 있습니다.  자세한 내용은 [OData: 서비스 메타데이터 문서](http://go.microsoft.com/fwlink/?LinkId=186070)\(영문\)를 참조하세요. Visual Studio에서 **서비스 참조 추가** 대화 상자를 사용하여 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 기반 서비스에 대한 참조를 추가할 수 있습니다.  이 도구를 사용하여 클라이언트 프로젝트에서 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 피드가 반환하는 메타데이터에 대한 참조를 추가하는 경우 다음 작업을 수행합니다.  
  
-   데이터 서비스에서 서비스 메타데이터 문서를 요청하고 반환된 메타데이터를 해석합니다.  
  
    > [!NOTE]
    >  반환된 메타데이터는 클라이언트 프로젝트에 .edmx 파일로 저장됩니다.  이 .edmx 파일은 Entity Framework에서 사용되는 .edmx 파일과 동일한 형식을 사용하지 않기 때문에 엔터티 데이터 모델 디자이너를 사용하여 열 수 없습니다.  XML 편집기나 텍스트 편집기를 사용하여 이 메타데이터 파일을 볼 수 있습니다.  자세한 내용은 [\[MC\-EDMX\]: 데이터 서비스 패키징 형식의 엔터티 데이터 모델](http://go.microsoft.com/fwlink/?LinkID=178833)\(영문\) 사양을 참조하세요.  
  
-   <xref:System.Data.Services.Client.DataServiceContext>에서 상속된 엔터티 컨테이너 클래스로 서비스 표현을 생성합니다.  생성된 이 엔터티 컨테이너 클래스는 엔터티 데이터 모델 도구에서 생성하는 엔터티 컨테이너와 유사합니다.  자세한 내용은 [Object Services Overview \(Entity Framework\)](http://msdn.microsoft.com/ko-kr/43014cf9-c9cb-4538-bfbb-197820b60038)을 참조하세요.  
  
-   서비스 메타데이터에서 검색한 데이터 모델 형식에 대해 데이터 클래스를 생성합니다.  
  
-   프로젝트에 `System.Data.Services.Client` 어셈블리 참조를 추가합니다.  
  
 자세한 내용은 [방법: 데이터 서비스 참조 추가](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md)을 참조하세요.  
  
 명령 프롬프트에서 [DataSvcUtil.exe](../../../../docs/framework/data/wcf/wcf-data-service-client-utility-datasvcutil-exe.md) 도구를 사용하여 클라이언트 데이터 서비스 클래스를 생성할 수도 있습니다.  자세한 내용은 [방법: 수동으로 클라이언트 데이터 서비스 클래스 생성](../../../../docs/framework/data/wcf/how-to-manually-generate-client-data-service-classes-wcf-data-services.md)을 참조하세요.  
  
## 클라이언트 데이터 형식 매핑  
 Visual Studio의 **서비스 참조 추가** 대화 상자나 `DataSvcUtil.exe` 도구를 사용하여 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 피드를 기반으로 하는 클라이언트 데이터 클래스를 생성하는 경우 .NET Framework 데이터 형식은 다음과 같이 데이터 모델의 기본 형식에 매핑됩니다.  
  
|데이터 모델 형식|.NET Framework 데이터 형식|  
|---------------|---------------------------|  
|`Edm.Binary`|<xref:System.Byte> `[]`|  
|`Edm.Boolean`|<xref:System.Boolean>|  
|`Edm.Byte`|<xref:System.Byte>|  
|`Edm.DateTime`|<xref:System.DateTime>|  
|`Edm.Decimal`|<xref:System.Decimal>|  
|`Edm.Double`|<xref:System.Double>|  
|`Edm.Guid`|<xref:System.Guid>|  
|`Edm.Int16`|<xref:System.Int16>|  
|`Edm.Int32`|<xref:System.Int32>|  
|`Edm.Int64`|<xref:System.Int64>|  
|`Edm.SByte`|<xref:System.SByte>|  
|`Edm.Single`|<xref:System.Single>|  
|`Edm.String`|<xref:System.String>|  
  
 자세한 내용은 [OData: 기본 데이터 형식](http://go.microsoft.com/fwlink/?LinkId=186072)\(영문\)을 참조하세요.  
  
## 참고 항목  
 [WCF Data Services 클라이언트 라이브러리](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)   
 [빠른 시작](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)