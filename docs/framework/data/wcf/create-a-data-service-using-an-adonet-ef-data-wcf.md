---
title: "방법: ADO.NET Entity Framework 데이터 원본을 사용하여 데이터 서비스 만들기(WCF Data Services) | Microsoft Docs"
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
  - "WCF Data Services, Entity Framework"
  - "WCF Data Services, 공급자"
ms.assetid: 6d11fec8-0108-42f5-8719-2a7866d04428
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# 방법: ADO.NET Entity Framework 데이터 원본을 사용하여 데이터 서비스 만들기(WCF Data Services)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]에서는 엔터티 데이터를 데이터 서비스로 노출합니다.  이 엔터티 데이터는 데이터 소스가 관계형 데이터베이스일 때 [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)]에 의해 제공됩니다.  이 항목에서는 기존 데이터베이스를 기반으로 하는 [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] 웹 응용 프로그램에서 [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] 기반 데이터 모델을 만들고 이 데이터 모델을 사용하여 새 데이터 서비스를 만드는 방법을 보여 줍니다.  
  
 [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)]는 [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] 프로젝트 외부에서 [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] 모델을 생성할 수 있는 명령줄 도구도 제공합니다.  자세한 내용은 [방법: EdmGen.exe를 사용하여 모델 및 매핑 파일 생성](../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)을 참조하세요.  
  
### 기존 웹 응용 프로그램에 기존 데이터베이스를 기반으로 하는 Entity Framework 모델을 추가하려면  
  
1.  **프로젝트** 메뉴에서 **새 항목 추가**를 클릭합니다.  
  
2.  **템플릿** 창에서 **데이터** 범주를 클릭하고 **ADO.NET 엔터티 데이터 모델**을 선택합니다.  
  
3.  모델 이름을 입력하고 **추가**를 클릭합니다.  
  
     [!INCLUDE[adonet_edm](../../../../includes/adonet-edm-md.md)] 마법사의 첫 페이지가 표시됩니다.  
  
4.  **Model 콘텐츠 선택** 대화 상자에서 **데이터베이스에서 생성**을 선택합니다.  **다음**을 클릭합니다.  
  
5.  **새 연결** 단추를 클릭합니다.  
  
6.  **연결 속성** 대화 상자에서 서버 이름을 입력하고, 인증 방법을 선택하고, 데이터베이스 이름을 입력한 다음 **확인**을 클릭합니다.  
  
     **데이터 연결 선택** 대화 상자가 데이터베이스 연결 설정으로 업데이트됩니다.  
  
7.  **다른 이름으로 App.Config의 엔터티 연결 설정 저장:** 확인란이 선택되었는지 확인합니다.  **다음**을 클릭합니다.  
  
8.  **데이터베이스 개체 선택** 대화 상자에서 데이터 서비스에 노출할 데이터베이스 개체를 모두 선택합니다.  
  
    > [!NOTE]
    >  데이터 모델에 포함된 개체는 데이터 서비스에 의해 자동으로 노출되지 않습니다.  서비스 자체에서 해당 개체를 명시적으로 노출해야 합니다.  자세한 내용은 [데이터 서비스 구성](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md)을 참조하세요.  
  
9. **마침**을 클릭하여 마법사를 완료합니다.  
  
     특정 데이터베이스를 기반으로 하는 기본 데이터 모델이 만들어집니다.  [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)]에서는 데이터 모델을 사용자 지정할 수 있습니다.  자세한 내용은 [Tasks](http://msdn.microsoft.com/ko-kr/7166f1f1-4de8-4bd4-86b5-5e20a2ebaccb)을 참조하세요.  
  
### 새 데이터 모델을 사용하여 데이터 서비스를 만들려면  
  
1.  [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]에서 데이터 모델을 나타내는 .edmx 파일을 엽니다.  
  
2.  **Model 브라우저**에서 모델을 마우스 오른쪽 단추로 클릭하고 **속성**을 클릭한 다음 엔터티 컨테이너의 이름을 적어 둡니다.  
  
3.  **솔루션 탐색기**에서 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 프로젝트의 이름을 마우스 오른쪽 단추로 클릭한 다음 **새 항목 추가**를 클릭합니다.  
  
4.  **새 항목 추가** 대화 상자에서 **WCF Data Services**를 선택합니다.  
  
5.  서비스의 이름을 지정하고 **확인**을 클릭합니다.  
  
     [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]에서 새 서비스의 XML 태그와 코드 파일이 만들어집니다.  기본적으로 코드 편집기 창이 열립니다.  
  
6.  데이터 서비스 코드에서 데이터 서비스를 정의하는 클래스 정의의 `/* TODO: put your data source class name here */` 주석을 <xref:System.Data.Objects.ObjectContext> 클래스에서 상속되고 2단계에서 적어 둔 데이터 모델의 엔터티 컨테이너인 형식으로 바꿉니다.  
  
7.  데이터 서비스 코드에서 권한 있는 클라이언트가 데이터 서비스에서 노출하는 엔터티 집합에 액세스할 수 있도록 합니다.  자세한 내용은 [데이터 서비스 만들기](../../../../docs/framework/data/wcf/creating-the-data-service.md)을 참조하세요.  
  
8.  웹 브라우저를 사용하여 Northwind.svc 데이터 서비스를 테스트하려면 [웹 브라우저에서 서비스 액세스](../../../../docs/framework/data/wcf/accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md) 항목의 지침을 따릅니다.  
  
## 참고 항목  
 [WCF Data Services 정의](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)   
 [데이터 서비스 공급자](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)   
 [방법: 리플렉션 공급자를 사용하여 데이터 서비스 만들기](../../../../docs/framework/data/wcf/create-a-data-service-using-rp-wcf-data-services.md)   
 [방법: LINQ to SQL 데이터 소스를 사용하여 데이터 서비스 만들기](../../../../docs/framework/data/wcf/create-a-data-service-using-linq-to-sql-wcf.md)