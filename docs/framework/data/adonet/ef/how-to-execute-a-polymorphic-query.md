---
title: "방법: 다형성 쿼리 실행 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "ESQL"
  - "jsharp"
ms.assetid: 2f05da1e-845b-4f14-83e4-c6353a850553
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# 방법: 다형성 쿼리 실행
이 항목에서는 [OFTYPE](../../../../../docs/framework/data/adonet/ef/language-reference/oftype-entity-sql.md) 연산자를 사용하여 다형성 [!INCLUDE[esql](../../../../../includes/esql-md.md)] 쿼리를 실행하는 방법을 보여 줍니다.  
  
### 이 예제의 코드를 실행하려면  
  
1.  프로젝트에 [School Model](http://msdn.microsoft.com/ko-kr/859a9587-81ea-4a45-9bc0-f8d330e1adac)을 추가하고 Entity Framework를 사용하도록 프로젝트를 구성합니다.  자세한 내용은 [How to: Use the Entity Data Model Wizard](http://msdn.microsoft.com/ko-kr/dadb058a-c5d9-4c5c-8b01-28044112231d)을 참조하세요.  
  
2.  응용 프로그램의 코드 페이지에서 다음 `using` 문\(Visual Basic에서는 `Imports`\)을 추가합니다.  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
3.  [Walkthrough: Mapping Inheritance \- Table\-per\-Hierarchy](http://msdn.microsoft.com/ko-kr/49b685cf-9db8-4d6d-b885-8837ed238f55)의 단계를 수행하여 계층당 하나의 테이블 상속이 포함되도록 개념적 모델을 수정합니다.  
  
## 예제  
 다음 예제에서는 OFTYPE 연산자를 사용하여 `Courses` 컬렉션의 `OnsiteCourses`만으로 구성된 컬렉션을 가져와서 표시합니다.  
  
 [!code-csharp[DP EntityServices Concepts#PolymorphicQuery](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#polymorphicquery)]
 [!code-vb[DP EntityServices Concepts#PolymorphicQuery](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#polymorphicquery)]  
  
## 참고 항목  
 [Entity Framework용 EntityClient 공급자](../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md)   
 [@FSHO2@Entity SQL 언어](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)