---
title: "Oracle BFILE | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 341bbf84-4734-4d44-8723-ccedee954e21
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Oracle BFILE
.NET Framework Data Provider for Oracle에는 Oracle <xref:System.Data.OracleClient.OracleType> 데이터 형식 작업에 사용되는 <xref:System.Data.OracleClient.OracleBFile> 클래스가 포함되어 있습니다.  
  
 Oracle **BFILE** 데이터 형식은 최대 4GB의 이진 데이터에 대한 참조가 포함되어 있는 Oracle **LOB** 데이터 형식입니다.  Oracle **BFILE**은 데이터가 서버가 아닌 운영 체제의 물리적 파일에 저장된다는 점에서 다른 Oracle **LOB** 데이터 형식과 다릅니다.  **BFILE** 데이터 형식은 데이터에 대해 읽기 전용 액세스를 제공합니다.  
  
 **LOB** 데이터 형식과 구별되는 **BFILE** 데이터 형식의 기타 특성은 다음과 같습니다.  
  
-   구조화되지 않은 데이터를 포함합니다.  
  
-   서버측 청크를 지원합니다.  
  
-   참조 복사 의미를 사용합니다.  예를 들어, **BFILE**에 대해 복사 작업을 수행하면 파일에 대한 참조인 **BFILE** 로케이터만 복사되며  파일의 데이터는 복사되지 않습니다.  
  
 **BFILE** 데이터 형식은 크기가 커서 데이터베이스에 저장하기에는 부적절한 LOB를 참조하는 데 사용해야 합니다.  **BFILE** 데이터 형식을 사용하면 **LOB** 데이터 형식에 비해 더 많은 클라이언트, 서버 및 통신 오버헤드가 수반됩니다.  따라서 작은 용량의 데이터만 가져와야 할 경우에는 **BFILE**에 액세스하는 것이 효율적입니다.  반면에 전체 개체를 가져와야 하는 경우에는 데이터베이스 상주 LOB에 액세스 하는 것이 효율적입니다.  
  
 NULL이 아닌 각 **OracleBFile** 개체는 원본으로 사용하는 물리적 파일의 위치를 정의하는 엔터티 두 개와 연결되어 있습니다.  
  
1.  파일 시스템의 디렉터리에 대한 데이터베이스 별칭인 Oracle DIRECTORY 개체입니다.  
  
2.  DIRECTORY 개체와 연관된 디렉터리에 위치하는 원본 파일 이름입니다.  
  
## 예제  
 다음 C\# 예제에서는 Oracle 테이블에 **BFILE**을 만든 다음 이를 **OracleBFile** 개체의 형태로 검색하는 방법을 보여 줍니다.  이 예제에서는 <xref:System.Data.OracleClient.OracleDataReader> 개체와 **OracleBFile** **Seek** 및 **Read** 메서드를 사용하는 방법도 설명합니다.  이 샘플을 사용하려면 우선 Oracle 서버에 "c:\\\\bfiles"라는 디렉터리와 "MyFile.jpg"라는 파일을 만들어야 합니다.  
  
```csharp  
using System;  
using System.IO;  
using System.Data;  
using System.Data.OracleClient;  
  
public class Sample  
{  
   public static void Main(string[] args)  
   {  
      OracleConnection connection = new OracleConnection(  
        "Data Source=Oracle8i;Integrated Security=yes");  
      connection.Open();  
  
      OracleCommand command = connection.CreateCommand();  
      command.CommandText =   
        "CREATE or REPLACE DIRECTORY MyDir as 'c:\\bfiles'";  
      command.ExecuteNonQuery();  
      command.CommandText =   
        "DROP TABLE MyBFileTable";  
      try {  
        command.ExecuteNonQuery();  
      }  
      catch {  
      }  
      command.CommandText =   
        "CREATE TABLE MyBFileTable(col1 number, col2 BFILE)";  
      command.ExecuteNonQuery();  
      command.CommandText =   
        "INSERT INTO MyBFileTable values ('2', BFILENAME('MyDir', " +  
        "'MyFile.jpg'))";  
      command.ExecuteNonQuery();  
      command.CommandText = "SELECT * FROM MyBFileTable";  
  
        byte[] buffer = new byte[100];  
  
      OracleDataReader reader = command.ExecuteReader();  
      using (reader) {  
          if (reader.Read()) {  
                OracleBFile bFile = reader.GetOracleBFile(1);  
                using (bFile) {  
                  bFile.Seek(0, SeekOrigin.Begin);  
                  bFile.Read(buffer, 0, 100);  
              }  
          }  
      }  
  
      connection.Close();  
   }  
  
}  
```  
  
## 참고 항목  
 [Oracle 및 ADO.NET](../../../../docs/framework/data/adonet/oracle-and-adonet.md)   
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)