---
title: "LINQ to Entities 쿼리의 함수 호출 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 12a525a9-727c-4464-a0c7-71a0ef541792
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# LINQ to Entities 쿼리의 함수 호출
이 단원의 항목에서는 LINQ to Entities 쿼리에서 함수를 호출하는 방법에 대해 설명합니다.  
  
 <xref:System.Data.Objects.EntityFunctions> 및 <xref:System.Data.Objects.SqlClient.SqlFunctions> 클래스를 사용하여 Entity Framework의 일부인 정식 함수와 데이터베이스 함수에 액세스할 수 있습니다.  자세한 내용은 [방법: 정식 함수 호출](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-canonical-functions.md) 및 [방법: 데이터베이스 함수 호출](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-database-functions.md)를 참조하세요.  
  
 사용자 지정 함수를 호출하는 과정은 다음의 기본적인 세 단계로 이루어집니다.  
  
1.  개념적 모델에서 함수를 정의하거나 저장소 모델에서 함수를 선언합니다.  
  
2.  응용 프로그램에 메서드를 추가하고 <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>를 사용하여 이 메서드를 모델의 함수에 매핑합니다.  
  
3.  LINQ to Entities 쿼리에서 함수를 호출합니다.  
  
 자세한 내용은 이 단원의 해당 항목을 참조하세요.  
  
## 단원 내용  
 [방법: 정식 함수 호출](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-canonical-functions.md)  
  
 [방법: 데이터베이스 함수 호출](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-database-functions.md)  
  
 [방법: 사용자 지정 데이터베이스 함수 호출](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-custom-database-functions.md)  
  
 [방법: 쿼리에서 모델 정의 함수 호출](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-model-defined-functions-in-queries.md)  
  
 [방법: 모델 정의 함수를 개체 메서드로 호출](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-model-defined-functions-as-object-methods.md)  
  
## 참고 항목  
 [LINQ to Entities의 쿼리](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)   
 [정식 함수](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md)   
 [.edmx File Overview](http://msdn.microsoft.com/ko-kr/f4c8e7ce-1db6-417e-9759-15f8b55155d4)   
 [How to: Define Custom Functions in the Conceptual Model](http://msdn.microsoft.com/ko-kr/0dad7b8b-58f6-4271-b238-f34810d68e5f)