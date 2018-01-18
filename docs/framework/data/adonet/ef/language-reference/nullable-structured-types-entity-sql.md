---
title: "null 허용 구조적 형식(Entity SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ae006fa9-997e-45bb-8a04-a7f62026171e
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 29b0aa7f6f155de2c55f88b4c796ecc482d1cb84
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2018
---
# <a name="nullable-structured-types-entity-sql"></a>null 허용 구조적 형식(Entity SQL)
구조적 형식의 `null` 인스턴스는 존재하지 않는 인스턴스입니다. 이는 모든 속성에 `null` 값이 있는 기존 인스턴스와 다릅니다.  
  
 이 항목에서는 어떤 형식이 nullable이고 어떤 코드 패턴이 구조적 nullable 형식의 `null` 인스턴스를 생성하는지를 비롯하여 구조적 nullable형식에 대해 설명합니다.  
  
## <a name="kinds-of-nullable-structured-types"></a>구조적 Nullable 형식의 종류  
 구조적 nullable 형식에는 세 가지 종류가 있습니다.  
  
-   행 형식  
  
-   복합 형식  
  
-   엔터티 형식  
  
## <a name="code-patterns-that-produce-null-instances-of-structured-types"></a>구조적 형식의 Null 인스턴스를 생성하는 코드 패턴  
 다음 시나리오에서는 `null` 인스턴스를 생성합니다.  
  
-   `null`을 구조적 형식으로 모양 결정:  
  
    ```  
    TREAT (NULL AS StructuredType)  
    ```  
  
-   기본 형식을 파생 형식으로 업캐스트:  
  
    ```  
    TREAT (BaseType AS DerivedType)  
    ```  
  
-   False 조건에 대한 외부 조인:  
  
    ```  
    Collection1 LEFT OUTER JOIN Collection2  
    ON FalseCondition  
    ```  
  
     --또는  
  
    ```  
    Collection1 RIGHT OUTER JOIN Collection2  
    ON FalseCondition  
    ```  
  
     --또는  
  
    ```  
    Collection1 FULL OUTER JOIN Collection2  
    ON FalseCondition  
    ```  
  
-   `null` 참조 역참조:  
  
    ```  
    DEREF(NullRef)  
    ```  
  
-   빈 컬렉션에서 ANYELEMENT 가져오기:  
  
    ```  
    ANYELEMENT(EmptyCollection)  
    ```  
  
-   구조적 형식의 `null` 인스턴스 확인:  
  
    ```csharp  
    ...  
    for (int i = 0; i < reader.FieldCount; i++)  
    {  
        if (reader.IsDBNull(i))  
        {  
            Console.WriteLine("[NULL]");  
        }  
        else  
        {  
            Console.WriteLine(reader.GetValue(i).ToString());  
        }  
    }  
    ```  
  
## <a name="see-also"></a>참고 항목  
 [Entity SQL 개요](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
