---
title: "저장 프로시저만 사용하여 작업 사용자 지정 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 441e8ef3-998c-4d12-8825-ce66a178f90f
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# 저장 프로시저만 사용하여 작업 사용자 지정
저장 프로시저만을 사용한 데이터 액세스는 일반적인 시나리오입니다.  
  
## 예제  
  
### 설명  
 동적 SQL을 실행시키는 첫 번째 쿼리를 저장 프로시저를 래핑하는 메서드 호출로 대체하여 [저장 프로시저를 사용하여 작업 사용자 지정](../../../../../../docs/framework/data/adonet/sql/linq/customizing-operations-by-using-stored-procedures.md)에 제공된 예제를 수정할 수 있습니다.  
  
 다음 예제와 같이 `CustomersByCity`는 메서드로 가정합니다.  
  
### 코드  
 [!code-csharp[DLinqOverrideDefaultSproc#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefaultSproc/cs/northwind.cs#4)]
 [!code-vb[DLinqOverrideDefaultSproc#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefaultSproc/vb/northwind.vb#4)]  
  
 다음 코드는 동적 SQL 없이 실행됩니다.  
  
 [!code-csharp[DLinqOverrideDefaultSproc#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefaultSproc/cs/Program.cs#5)]
 [!code-vb[DLinqOverrideDefaultSproc#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefaultSproc/vb/Module1.vb#5)]  
  
## 참고 항목  
 [기본 동작을 재정의할 때의 요구 사항](../../../../../../docs/framework/data/adonet/sql/linq/responsibilities-of-the-developer-in-overriding-default-behavior.md)