---
title: "Oracle REF CURSOR | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c6b25b8b-0bdd-41b2-9c7c-661f070c2247
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Oracle REF CURSOR
.NET Framework Data Provider for Oracle에서는 Oracle **REF CURSOR** 데이터 형식을 지원합니다.  Oracle REF CURSOR를 사용하는 데이터 공급자를 사용할 경우 다음 동작을 고려해야 합니다.  
  
> [!NOTE]
>  일부 동작이 MSDAORA\(Microsoft OLE DB Provider for Oracle\)의 동작과 다릅니다.  
  
-   Data Provider for Oracle에서는 성능상의 이유로 명시적으로 데이터 형식을 지정하지 않는 한 MSDAORA에서처럼 **REF CURSOR** 데이터 형식을 자동으로 바인딩하지 않습니다.  
  
-   데이터 공급자는 REF CURSOR 매개 변수를 지정하는 데 사용되는 {resultset} 이스케이프를 포함하여 ODBC 이스케이프 시퀀스를 지원하지 않습니다.  
  
-   REF CURSOR를 반환하는 저장 프로시저를 실행하려면 **Cursor**의 <xref:System.Data.OracleClient.OracleType> 및 **Output**의 <xref:System.Data.OracleClient.OracleParameter.Direction%2A>과 함께 <xref:System.Data.OracleClient.OracleParameterCollection>에서 매개 변수를 정의해야 합니다.  데이터 공급자는 REF CURSOR를 출력 매개 변수로만 바인딩하는 것을 지원하며  REF CURSOR를 입력 매개 변수로 지원하지 않습니다.  
  
-   매개 변수 값에서 <xref:System.Data.OracleClient.OracleDataReader>를 가져오는 것은 지원되지 않습니다.  값의 형식은 명령이 실행된 후의 <xref:System.DBNull>입니다.  
  
-   <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A>를 호출하는 경우처럼 REF CURSOR와 함께 사용하는 유일한 **CommandBehavior** 열거형 값은 **CloseConnection**이며 나머지는 모두 무시됩니다.  
  
-   **OracleDataReader**에서 REF CURSOR의 순서는 **OracleParameterCollection**의 매개 변수 순서에 따라 결정됩니다.  <xref:System.Data.OracleClient.OracleParameter.ParameterName%2A> 속성은 무시됩니다.  
  
-   PL\/SQL **TABLE** 데이터 형식은 지원되지 않습니다.  그러나 REF CURSOR가 더 효율적입니다.  **TABLE** 데이터 형식을 사용해야 하는 경우 OLE DB .NET Data Provider와 MSDAORA를 함께 사용합니다.  
  
## 단원 내용  
 [REF CURSOR 예제](../../../../docs/framework/data/adonet/ref-cursor-examples.md)  
 REF CURSOR의 사용을 보여 주는 세 가지 예제가 들어 있습니다.  
  
 [OracleDataReader의 REF CURSOR 매개 변수](../../../../docs/framework/data/adonet/ref-cursor-parameters-in-an-oracledatareader.md)  
 REF CURSOR 매개 변수를 반환하는 PL\/SQL 저장 프로시저를 실행하여 값을 **OracleDataReader**로 읽는 방법을 보여 줍니다.  
  
 [OracleDataReader를 사용하여 여러 REF CURSOR에서 데이터 검색](../../../../docs/framework/data/adonet/retrieving-data-from-multiple-ref-cursors.md)  
 두 개의 REF CURSOR 매개 변수를 반환하는 PL\/SQL 저장 프로시저를 실행하여 **OracleDataReader**를 사용하여 값을 읽는 방법을 보여 줍니다.  
  
 [하나 이상의 REF CURSOR를 사용하여 데이터 집합 필터링](../../../../docs/framework/data/adonet/filling-a-dataset-using-one-or-more-ref-cursors.md)  
 두 개의 REF CURSOR 매개 변수를 반환하는 PL\/SQL 저장 프로시저를 실행하여 반환되는 행으로 <xref:System.Data.DataSet>을 채우는 방법을 보여 줍니다.  
  
## 참고 항목  
 [Oracle 및 ADO.NET](../../../../docs/framework/data/adonet/oracle-and-adonet.md)   
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)