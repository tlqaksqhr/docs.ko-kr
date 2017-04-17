---
title: "데이터 정의 언어로 작업 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ec50083d-44f4-4093-9b23-5eacd601f96e
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# 데이터 정의 언어로 작업
[!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] 버전 4부터 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]에서는 DDL\(데이터 정의 언어\)을 지원합니다.  이렇게 하면 연결 문자열 및 저장소\(SSDL\) 모델의 메타데이터를 기반으로 데이터베이스 인스턴스를 만들거나 삭제할 수 있습니다.  
  
 <xref:System.Data.Objects.ObjectContext>의 다음 메서드는 연결 문자열과 SSDL 콘텐츠를 사용하여 데이터베이스를 만들거나 삭제하고, 데이터베이스가 있는지 확인하며, 생성된 DDL 스크립트를 확인합니다.  
  
-   <xref:System.Data.Objects.ObjectContext.CreateDatabase%2A>  
  
-   <xref:System.Data.Objects.ObjectContext.DeleteDatabase%2A>  
  
-   <xref:System.Data.Objects.ObjectContext.DatabaseExists%2A>  
  
-   <xref:System.Data.Objects.ObjectContext.CreateDatabaseScript%2A>  
  
> [!NOTE]
>  DDL 명령을 실행하려면 충분한 권한이 있어야 합니다.  
  
 위에 나열된 메서드는 대부분의 작업을 기본 ADO.NET 데이터 공급자에 위임합니다.  데이터베이스 개체를 생성하는 데 사용되는 명명 규칙이 쿼리 및 업데이트에 사용되는 규칙과 일치하는지 확인하는 것은 공급자의 책임입니다.  
  
 다음 예제에서는 기존 모델을 기반으로 데이터베이스를 생성하는 방법을 보여 줍니다.  또한 새 엔터티 개체를 개체 컨텍스트에 추가한 다음 데이터베이스에 저장합니다.  
  
## 절차  
  
#### 기존 모델을 기반으로 데이터베이스를 정의하려면  
  
1.  콘솔 응용 프로그램을 만듭니다.  
  
2.  응용 프로그램에 기존 모델을 추가합니다.  
  
    1.  `SchoolModel`이라는 빈 모델을 추가합니다.  빈 모델을 만들려면 [How to: Create a New .edmx File](http://msdn.microsoft.com/ko-kr/beb8189e-e51c-4051-839c-9902c224abf2) 항목을 참조하세요.  
  
     SchoolModel.edmx 파일이 프로젝트에 추가됩니다.  
  
    1.  [School Model](http://msdn.microsoft.com/ko-kr/859a9587-81ea-4a45-9bc0-f8d330e1adac) 항목에서 School 모델의 개념적 콘텐츠, 저장소 콘텐츠 및 매핑 콘텐츠를 복사합니다.  
  
    2.  SchoolModel.edmx 파일을 열고 콘텐츠를 `edmx:Runtime` 태그 안에 붙여 넣습니다.  
  
3.  다음 코드를 main 함수에 추가합니다.  이 코드에서는 데이터베이스 서버에 대한 연결 문자열을 초기화하고 DDL 스크립트를 확인하며, 데이터베이스를 만들고 새 엔터티를 컨텍스트에 추가한 다음 변경 내용을 데이터베이스에 저장합니다.  
  
     [!code-csharp[DP ObjectServices Concepts#DDL](../../../../../samples/snippets/csharp/VS_Snippets_Data/DP ObjectServices Concepts/CS/Source.cs#ddl)]
     [!code-vb[DP ObjectServices Concepts#DDL](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP ObjectServices Concepts/VB/Source.vb#ddl)]