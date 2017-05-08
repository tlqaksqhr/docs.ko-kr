---
title: "보안(LINQ to DataSet) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6116b2b8-75f4-4d8b-aea6-c13e55cda50b
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# 보안(LINQ to DataSet)
이 항목에서는 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]의 보안 문제에 대해 설명합니다.  
  
## 신뢰할 수 없는 구성 요소에 쿼리 전달  
 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 쿼리는 프로그램의 한 위치에서 작성한 다음 다른 위치에서 실행할 수 있습니다.  쿼리를 작성하는 위치에서는 호출 메서드가 속한 클래스의 전용 멤버나 지역 변수\/인수를 나타내는 기호와 같이 해당 위치에서 표시되는 모든 요소를 쿼리에서 참조할 수 있습니다.  쿼리 실행 중에는 작성 시 쿼리에서 참조한 멤버를 호출 코드에서 확인할 수 없는 경우에도 쿼리에서 이러한 멤버에 유효하게 액세스할 수 있습니다.  쿼리를 실행하는 코드는 액세스할 대상을 선택할 수 없으므로 멤버에 대한 자체적인 액세스가 불가합니다.  코드는 쿼리가 액세스하는 멤버에만 해당 쿼리를 통해서만 액세스할 수 있습니다.  
  
 이것은 쿼리에 대한 참조를 다른 코드 조각에 전달함으로써 쿼리를 받는 구성 요소를 신뢰하고 이러한 구성 요소에 쿼리가 참조하는 모든 공용 및 전용 멤버에 대한 액세스를 부여할 수 있음을 의미합니다.  일반적으로, 쿼리가 기밀로 유지해야 하는 정보를 노출하지 않도록 주의 깊게 작성된 경우가 아니라면 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 쿼리를 신뢰할 수 없는 구성 요소로 전달해서는 안 됩니다.  
  
## 외부 입력  
 응용 프로그램은 사용자나 다른 외부 에이전트로부터 외부 입력을 받아 그에 기반한 동작을 수행하는 경우가 많습니다.  [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]의 경우에는 응용 프로그램에서 외부 입력에 기반하는 특정 방식으로 쿼리를 작성하거나 쿼리에서 외부 입력을 사용할 수 있습니다. [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 쿼리에서는 리터럴을 사용할 수 있는 모든 위치에 매개 변수를 사용할 수 있습니다.  응용 프로그램 개발자는 외부 에이전트에서 쿼리로 직접 리터럴을 삽입하는 대신 매개 변수가 있는 쿼리를 사용해야 합니다.  
  
 사용자나 외부 에이전트에서 직접 또는 간접적으로 파생되는 모든 입력에는 인증되지 않은 작업을 수행하기 위해 대상 언어의 구문을 이용하는 콘텐츠가 있을 수 있습니다.  이러한 공격은 대상 언어가 Transact\-SQL인 공격 패턴에 따라 SQL 삽입 공격으로 이름이 붙여졌습니다.  쿼리에 직접 삽입되는 사용자 입력은 데이터베이스 테이블 삭제, 서비스 거부 유발 또는 수행되는 작업의 특성을 변경하는 데 사용될 수 있습니다.  쿼리는 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]에서 작성할 수 있지만 개체 모델 API를 통해 수행됩니다. [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 쿼리는 Transact\-SQL에서와 같이 문자열 조작이나 연결을 사용하여 작성되지 않으므로 일반적으로 SQL 삽입 공격을 쉽게 받지 않습니다.  
  
## 참고 항목  
 [프로그래밍 가이드](../../../../docs/framework/data/adonet/programming-guide-linq-to-dataset.md)