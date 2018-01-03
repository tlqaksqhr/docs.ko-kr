---
title: OracleType
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 18143304-d5c7-4c95-9995-678088d0c142
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 4b879bfca2586d528027e4c016703919bef1e1a2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="oracletypes"></a>OracleType
.NET Framework Data Provider for Oracle에는 Oracle 데이터 형식으로 작업하는 데 사용할 수 있는 여러 가지 구조가 들어 있습니다. 여기에는 <xref:System.Data.OracleClient.OracleNumber> 및 <xref:System.Data.OracleClient.OracleString>이 포함됩니다.  
  
> [!NOTE]
>  이러한 구조의 전체 목록은 <xref:System.Data.OracleClient>를 참조하세요.  
  
 다음은 C# 예제입니다.  
  
-   Oracle 테이블을 만들고 데이터와 함께 로드합니다.  
  
-   <xref:System.Data.OracleClient.OracleDataReader>를 사용하여 데이터에 액세스하고 여러 가지 <xref:System.Data.OracleClient.OracleType> 구조를 사용하여 데이터를 표시합니다.  
  
## <a name="creating-an-oracle-table"></a>Oracle 테이블 만들기  
 이 예제에서는 Oracle 테이블을 만들고 데이터와 함께 로드합니다. 반드시 이 예제를 실행한 후 다음 예제를 실행해야 합니다.  
  
```csharp  
public void Setup(string connectionString)  
   {  
   OracleConnection conn = new OracleConnection(connectionString);  
   try  
      {  
      conn.Open();  
      OracleCommand cmd = conn.CreateCommand();  
      cmd.CommandText ="CREATE TABLE OracleTypesTable " +  
        "(MyVarchar2 varchar2(3000),MyNumber number(28,4) " +  
        "PRIMARY KEY ,MyDate date, MyRaw raw(255))";  
      cmd.ExecuteNonQuery();  
      cmd.CommandText ="INSERT INTO OracleTypesTable VALUES " +  
        "( 'test', 2, to_date('2000-01-11 12:54:01','yyyy-mm-dd " +  
        "hh24:mi:ss'), '0001020304' )";  
      cmd.ExecuteNonQuery();  
      }  
   catch(Exception)  
   {  
   }  
   finally  
   {  
      conn.Close();  
   }  
}  
```  
  
## <a name="retrieving-data-from-the-oracle-table"></a>Oracle 테이블에서 데이터 검색  
 사용 하 여이 예제는 **OracleDataReader** 데이터에 액세스할 수 몇 가지를 사용 하 여 **OracleType** 구조 데이터를 표시 합니다.  
  
```csharp  
public void ReadOracleTypesExample(string connectionString)  
   {  
   OracleConnection myConnection =   
      new OracleConnection(connectionString);  
   myConnection.Open();  
   OracleCommand myCommand = myConnection.CreateCommand();  
  
   try  
      {  
      myCommand.CommandText = "SELECT * from OracleTypesTable";  
      OracleDataReader oracledatareader1 = myCommand.ExecuteReader();  
      oracledatareader1.Read();  
  
      //Using the oracle specific getters for each type is faster than  
      //using GetOracleValue.  
  
      //First column, MyVarchar2, is a VARCHAR2 data type in Oracle  
      //Server and maps to OracleString.  
      OracleString oraclestring1 =   
        oracledatareader1.GetOracleString(0);  
      Console.WriteLine("OracleString " + oraclestring1.ToString());  
  
      //Second column, MyNumber, is a NUMBER data type in Oracle Server  
      //and maps to OracleNumber.  
      OracleNumber oraclenumber1 =   
        oracledatareader1.GetOracleNumber(1);  
      Console.WriteLine("OracleNumber " + oraclenumber1.ToString());  
  
      //Third column, MyDate, is a DATA data type in Oracle Server  
      //and maps to OracleDateTime.  
      OracleDateTime oracledatetime1 =   
        oracledatareader1.GetOracleDateTime(2);  
      Console.WriteLine("OracleDateTime " + oracledatetime1.ToString());  
  
      //Fourth column, MyRaw, is a RAW data type in Oracle Server and  
      //maps to OracleBinary.  
      OracleBinary oraclebinary1 =   
        oracledatareader1.GetOracleBinary(3);  
      //Calling value on a null OracleBinary throws  
      //OracleNullValueException; therefore, check for a null value.  
      if (oraclebinary1.IsNull==false)  
      {  
         foreach(byte b in oraclebinary1.Value)  
         {  
            Console.WriteLine("byte " + b.ToString());  
         }  
      }  
      oracledatareader1.Close();  
   }  
   catch(Exception e)  
   {  
       Console.WriteLine(e.ToString());  
   }  
   finally  
   {  
       myConnection.Close();  
   }  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [Oracle 및 ADO.NET](../../../../docs/framework/data/adonet/oracle-and-adonet.md)  
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)
