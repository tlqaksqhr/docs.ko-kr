---
title: "명령을 사용하여 데이터 수정 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f4160389-b9ff-4b74-b655-437c76dcd586
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# 명령을 사용하여 데이터 수정
.NET Framework 데이터 공급자를 사용하여 저장 프로시저나 CREATE TABLE 및 ALTER COLUMN과 같은 데이터 정의 언어 문을 실행하여 데이터베이스 또는 카탈로그의 스키마를 조작할 수 있습니다.  이러한 명령에서는 쿼리에서와 같이 행을 반환하지 않으므로 **Command** 개체가 **ExecuteNonQuery**를 제공하여 해당 행을 처리합니다.  
  
 **ExecuteNonQuery** 메서드를 사용하면 스키마를 수정하는 것 외에, 데이터를 수정하지만 행을 반환하지 않는 INSERT, UPDATE 및 DELETE 등의 SQL 문을 처리할 수도 있습니다.  
  
 **ExecuteNonQuery** 메서드는 행을 반환하지 않지만 **Command** 개체의 **Parameters** 컬렉션을 통해 입력 및 출력 매개 변수와 반환 값을 전달하고 반환할 수 있습니다.  
  
## 단원 내용  
 [데이터 소스의 데이터 업데이트](../../../../docs/framework/data/adonet/updating-data-in-a-data-source.md)  
 데이터베이스의 데이터를 수정하는 명령 또는 저장 프로시저를 실행하는 방법을 설명합니다.  
  
 [카탈로그 작업 수행](../../../../docs/framework/data/adonet/performing-catalog-operations.md)  
 데이터베이스 스키마를 수정하는 명령을 실행하는 방법을 설명합니다.  
  
## 참고 항목  
 [ADO.NET에서 데이터 검색 및 수정](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)   
 [명령 및 매개 변수](../../../../docs/framework/data/adonet/commands-and-parameters.md)   
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)