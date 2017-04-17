---
title: "SQL-CLR 사용자 지정 형식 매핑 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d916c7fb-4b56-4214-acbe-5e23365047b2
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# SQL-CLR 사용자 지정 형식 매핑
SQL Server와 CLR\(공용 언어 런타임\) 간의 형식 매핑은 SQLMetal 명령줄 도구 또는 개체 관계형 디자이너\(O\/R 디자이너\)를 사용할 때 자동으로 지정됩니다.  
  
 사용자 지정 매핑을 수행하지 않는 경우 이러한 도구는 [SQL\-CLR 형식 매핑](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md)에 설명된 대로 기본 형식 매핑을 할당합니다.  기본 매핑과 다른 형식 매핑을 사용하려는 경우에는 해당 형식 매핑을 사용자 지정해야 합니다.  
  
 형식 매핑을 사용자 지정할 때는 중간 DBML 파일을 변경하는 것이 좋습니다.  그런 다음 SQLMetal 또는 O\/R 디자이너에서 코드 및 매핑 파일을 만들 때 사용자 지정된 DBML 파일을 사용해야 합니다.  
  
 코드 및 매핑 파일에서 <xref:System.Data.Linq.DataContext> 개체를 인스턴스화하면 <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=fullName> 메서드는 지정된 형식 매핑을 기반으로 데이터베이스를 생성합니다.  매핑에 CLR `type` 특성이 지정되지 않은 경우에는 기본 형식 매핑이 사용됩니다.  
  
## SQLMetal 또는 O\/R 디자이너 사용자 지정  
 SQLMetal 및 O\/R 디자이너를 사용할 때 코드 파일 내부 또는 외부의 형식 매핑 정보를 포함하는 개체 모델을 자동으로 만들 수 있습니다.  이러한 파일은 SQLMetal 또는 O\/R 디자이너에서 덮어쓰므로 매핑을 다시 만들 때마다 DBML 파일을 사용자 지정하여 사용자 형식 매핑을 지정하는 것이 좋습니다.  
  
 SQLMetal 또는 O\/R 디자이너를 사용하여 형식 매핑을 사용자 지정하려면 먼저 DBML 파일을 생성합니다.  그런 다음 코드 파일 또는 매핑 파일을 생성하기 전에 DBML 파일을 수정하여 원하는 형식 매핑을 확인합니다.  SQLMetal을 사용하는 경우 DBML 파일에서 `Type` 및 `DbType` 특성을 직접 변경하여 형식 매핑을 사용자 지정해야 합니다.  O\/R 디자이너를 사용하는 경우에는 디자이너 내부에서 변경할 수 있습니다.  O\/R 디자이너를 사용하는 방법에 대한 자세한 내용은 [LINQ to SQL 도구 Visual Studio에서](../Topic/LINQ%20to%20SQL%20Tools%20in%20Visual%20Studio2.md)를 참조하세요.  
  
> [!NOTE]
>  일부 형식 매핑의 경우 데이터베이스 관련 변환 과정에서 오버플로 또는 데이터 손실 예외가 발생할 수 있습니다.  사용자 지정을 수행하기 전에 [SQL\-CLR 형식 매핑](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md)에서 형식 매핑 런타임 동작 매트릭스를 신중하게 검토하세요.  
  
 SQLMetal 또는 O\/R 디자이너에서 형식 매핑 사용자 지정을 인식하게 하려면 코드 파일 또는 외부 매핑 파일을 생성할 때 사용자 지정 DBML 파일에 대한 경로가 이러한 도구에 제공되어야 합니다.  형식 매핑 사용자 지정을 위해 반드시 필요한 것은 아니지만, 항상 형식 매핑 정보를 코드 파일과 분리하고 추가 외부 형식 매핑 파일을 생성하는 것이 좋습니다.  이렇게 하면 유연성이 개선되어 코드 파일 재컴파일의 필요성이 줄어듭니다.  
  
## 데이터베이스 변경 내용 통합  
 데이터베이스를 변경할 경우 이러한 변경 내용이 반영되도록 DBML 파일을 업데이트해야 합니다.  DBML 파일을 업데이트하는 한 가지 방법은 자동으로 새 DBML 파일이 만들어지면 형식 매핑 사용자 지정을 다시 수행하는 것입니다.  또는 새 DBML 파일과 사용자 지정된 DBML 파일 간의 차이점을 비교하여 데이터베이스 변경 내용이 반영되도록 사용자 지정 DBML 파일을 수동으로 업데이트할 수 있습니다.  
  
## 참고 항목  
 [SQL\-CLR 형식 매핑](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md)   
 [LINQ to SQL의 코드 생성](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md)