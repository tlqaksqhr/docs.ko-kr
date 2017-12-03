---
title: "방법: ADO.NET Entity Framework 데이터 원본을 사용하여 데이터 서비스 만들기(WCF Data Services)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF Data Services, providers
- WCF Data Services, Entity Framework
ms.assetid: 6d11fec8-0108-42f5-8719-2a7866d04428
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 77a4b90b16a92e993d9283932b2a609f874c7568
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-create-a-data-service-using-an-adonet-entity-framework-data-source-wcf-data-services"></a>방법: ADO.NET Entity Framework 데이터 원본을 사용하여 데이터 서비스 만들기(WCF Data Services)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]에서는 엔터티 데이터를 데이터 서비스로 노출합니다. 이 엔터티 데이터는 데이터 소스가 관계형 데이터베이스일 때 [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)][!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)]에 의해 제공됩니다. 이 항목에서는 기존 데이터베이스를 기반으로 하는 [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] 웹 응용 프로그램에서 [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] 기반 데이터 모델을 만들고 이 데이터 모델을 사용하여 새 데이터 서비스를 만드는 방법을 보여 줍니다.  
  
 [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)]는 [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] 프로젝트 외부에서 [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] 모델을 생성할 수 있는 명령줄 도구도 제공합니다. 자세한 내용은 참조 [하는 방법: 모델 및 매핑 파일 생성을 사용 하 여 EdmGen.exe](../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)합니다.  
  
### <a name="to-add-an-entity-framework-model-that-is-based-on-an-existing-database-to-an-existing-web-application"></a>기존 웹 응용 프로그램에 기존 데이터베이스를 기반으로 하는 Entity Framework 모델을 추가하려면  
  
1.  에 **프로젝트** 메뉴를 클릭 하 여 **새 항목 추가**합니다.  
  
2.  에 **템플릿** 창에서 클릭는 **데이터** 범주를 선택한 후 **ADO.NET 엔터티 데이터 모델**합니다.  
  
3.  모델 이름을 입력 한 다음 클릭 **추가**합니다.  
  
     [!INCLUDE[adonet_edm](../../../../includes/adonet-edm-md.md)] 마법사의 첫 페이지가 표시됩니다.  
  
4.  에 **모델 콘텐츠 선택** 대화 상자에서 **데이터베이스에서 생성**합니다. **다음**을 클릭합니다.  
  
5.  클릭는 **새 연결** 단추입니다.  
  
6.  에 **연결 속성** 대화 상자에서 서버 이름을 입력, 인증 방법을 선택, 데이터베이스 이름을 입력 한 다음 클릭 **확인**합니다.  
  
     **데이터 연결 선택**대화 상자가 데이터베이스 연결 설정으로 업데이트 됩니다.  
  
7.  확인는 **이름으로 App.Config의 엔터티 연결 설정 저장:** 확인란이 선택 되어 있습니다. **다음**을 클릭합니다.  
  
8.  에 **데이터베이스 개체 선택** 대화 상자 모두 데이터베이스의 개체를 데이터 서비스에 노출 하도록 합니다.  
  
    > [!NOTE]
    >  데이터 모델에 포함된 개체는 데이터 서비스에 의해 자동으로 노출되지 않습니다. 서비스 자체에서 해당 개체를 명시적으로 노출해야 합니다. 자세한 내용은 참조 [데이터 서비스 구성](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md)합니다.  
  
9. 클릭 **마침** 마법사를 완료 합니다.  
  
     특정 데이터베이스를 기반으로 하는 기본 데이터 모델이 만들어집니다. [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)]에서는 데이터 모델을 사용자 지정할 수 있습니다. 자세한 내용은 [작업](http://msdn.microsoft.com/en-us/7166f1f1-4de8-4bd4-86b5-5e20a2ebaccb)을 참조하세요.  
  
### <a name="to-create-the-data-service-by-using-the-new-data-model"></a>새 데이터 모델을 사용하여 데이터 서비스를 만들려면  
  
1.  [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]에서 데이터 모델을 나타내는 .edmx 파일을 엽니다.  
  
2.  에 **모델 브라우저**모델을 마우스 오른쪽 단추로 클릭 하 여 **속성**, 다음 엔터티 컨테이너의 이름을 기록해 둡니다.  
  
3.  **솔루션 탐색기**의 이름을 마우스 오른쪽 단추로 클릭 하면 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 프로젝트를 마우스 클릭 **새 항목 추가**합니다.  
  
4.  에 **새 항목 추가** 대화 상자에서 **WCF 데이터 서비스**합니다.  
  
5.  서비스에 대 한 이름을 입력 한 다음 클릭 **확인**합니다.  
  
     [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]에서 새 서비스의 XML 태그와 코드 파일이 만들어집니다. 기본적으로 코드 편집기 창이 열립니다.  
  
6.  데이터 서비스 코드에서 데이터 서비스를 정의하는 클래스 정의의 `/* TODO: put your data source class name here */` 주석을 <xref:System.Data.Objects.ObjectContext> 클래스에서 상속되고 2단계에서 적어 둔 데이터 모델의 엔터티 컨테이너인 형식으로 바꿉니다.  
  
7.  데이터 서비스 코드에서 권한 있는 클라이언트가 데이터 서비스에서 노출하는 엔터티 집합에 액세스할 수 있도록 합니다. 자세한 내용은 참조 [데이터 서비스를 만드는](../../../../docs/framework/data/wcf/creating-the-data-service.md)합니다.  
  
8.  웹 브라우저를 사용 하 여 Northwind.svc 데이터 서비스를 테스트 하려면이 항목의 지침에 따라 [웹 브라우저에서 서비스 액세스](../../../../docs/framework/data/wcf/accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [WCF Data Services 정의](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)  
 [데이터 서비스 공급자](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)  
 [방법: 리플렉션 공급자를 사용 하 여 데이터 서비스 만들기](../../../../docs/framework/data/wcf/create-a-data-service-using-rp-wcf-data-services.md)  
 [방법: LINQ to SQL 데이터 원본을 사용 하 여 데이터 서비스 만들기](../../../../docs/framework/data/wcf/create-a-data-service-using-linq-to-sql-wcf.md)
