---
title: "작업 사용자 지정: 개요 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a3546296-1443-4b88-aa6e-d41011041ba7
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# 작업 사용자 지정: 개요
기본적으로 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서는 매핑을 기반으로 하는 삽입, 업데이트 및 삭제 작업을 위한 동적 SQL을 생성합니다. 그러나 사용자는 일반적으로 사용자 고유의 비즈니스 논리를 추가하여 보안, 유효성 검사 등을 제공하기를 원합니다.  
  
 이러한 작업을 사용자 지정하는 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 기술에는 다음이 포함됩니다.  
  
## 로드 옵션  
 쿼리에서 데이터베이스에 연결할 때 검색되는 주 대상에 관련된 데이터의 양을 제어할 수 있습니다.  이 기능은 <xref:System.Data.Linq.DataLoadOptions>를 사용하여 대규모로 구현됩니다.  자세한 내용은 [지연된 로드와 즉시 로드 비교](../../../../../../docs/framework/data/adonet/sql/linq/deferred-versus-immediate-loading.md)을 참조하세요.  
  
## 부분 메서드  
 해당 기본 매핑에서 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]은 사용자 비즈니스 논리를 구현하는 데 도움이 되는 부분 메서드를 제공합니다.  자세한 내용은 [부분 메서드를 사용하여 비즈니스 논리 추가](../../../../../../docs/framework/data/adonet/sql/linq/adding-business-logic-by-using-partial-methods.md)을 참조하세요.  
  
## 저장 프로시저 및 사용자 정의 함수  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서는 저장 프로시저 및 사용자 정의 함수의 사용을 지원합니다.  저장 프로시저는 작업을 사용자 지정하는 데 자주 사용됩니다.  자세한 내용은 [저장 프로시저](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md)을 참조하세요.  
  
## 참고 항목  
 [삽입, 업데이트 및 삭제 작업 사용자 지정](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md)