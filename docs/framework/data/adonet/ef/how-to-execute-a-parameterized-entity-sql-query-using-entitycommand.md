---
title: "방법: EntityCommand를 사용하여 매개 변수가 있는 Entity SQL 쿼리 실행 | Microsoft Docs"
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
ms.assetid: e93fea43-7e03-4d7d-9fee-2517b8b88cba
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# 방법: EntityCommand를 사용하여 매개 변수가 있는 Entity SQL 쿼리 실행
이 항목에서는 <xref:System.Data.EntityClient.EntityCommand> 개체를 사용하여 매개 변수가 있는 [!INCLUDE[esql](../../../../../includes/esql-md.md)] 쿼리를 실행하는 방법을 보여 줍니다.  
  
### 이 예제의 코드를 실행하려면  
  
1.  프로젝트에 [AdventureWorks Sales Model](http://msdn.microsoft.com/ko-kr/f16cd988-673f-4376-b034-129ca93c7832)을 추가하고 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]를 사용하도록 프로젝트를 구성합니다.  자세한 내용은 [How to: Use the Entity Data Model Wizard](http://msdn.microsoft.com/ko-kr/dadb058a-c5d9-4c5c-8b01-28044112231d)을 참조하세요.  
  
2.  응용 프로그램의 코드 페이지에서 다음 `using` 문\(Visual Basic에서는 `Imports`\)을 추가합니다.  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
## 예제  
 다음 예제에서는 두 개의 매개 변수가 있는 쿼리 문자열을 생성하는 방법을 보여 줍니다.  그런 다음 <xref:System.Data.EntityClient.EntityCommand>를 만들고 두 매개 변수를 이 <xref:System.Data.EntityClient.EntityCommand>의 <xref:System.Data.EntityClient.EntityParameter> 컬렉션에 추가한 후 `Contact` 항목 컬렉션을 반복합니다.  
  
 [!code-csharp[DP EntityServices Concepts#ParameterizedQueryWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#parameterizedquerywithentitycommand)]
 [!code-vb[DP EntityServices Concepts#ParameterizedQueryWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#parameterizedquerywithentitycommand)]  
  
## 참고 항목  
 [How to: Execute a Parameterized Query](http://msdn.microsoft.com/ko-kr/42048f03-c65c-4d98-b50a-3e7d537a63e8)   
 [@FSHO2@Entity SQL 언어](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)