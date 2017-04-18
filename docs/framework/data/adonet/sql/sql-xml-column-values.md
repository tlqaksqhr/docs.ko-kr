---
title: "SQL XML 열 값 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d97ce4da-f09c-4d1e-85b7-a0ccedd7246a
caps.latest.revision: 5
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 5
---
# SQL XML 열 값
[!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]에서는 `xml` 데이터 형식을 지원하므로 개발자가 <xref:System.Data.SqlClient.SqlCommand> 클래스의 표준 동작을 사용하여 이 형식이 포함된 결과 집합을 검색할 수 있습니다.  `xml` 열은 다른 열과 마찬가지 방식으로 검색할 수 있지만\(예: <xref:System.Data.SqlClient.SqlDataReader>로\) 열의 내용을 XML로 작업하려면 <xref:System.Xml.XmlReader>를 사용해야 합니다.  
  
## 예제  
 다음 콘솔 응용 프로그램에서는 **AdventureWorks** 데이터베이스의 **Sales.Store** 테이블에서 <xref:System.Data.SqlClient.SqlDataReader> 인스턴스까지 각각 `xml` 열이 포함된 두 개의 행을 선택합니다.  각 행에서 `xml` 열의 값은 <xref:System.Data.SqlClient.SqlDataReader>의 <xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A> 메서드를 사용하여 읽습니다.  값은 <xref:System.Xml.XmlReader>에 저장되어 있습니다.  <xref:System.Data.IDataRecord.GetValue%2A>는 `xml` 열의 값을 문자열로 반환하므로 내용을 <xref:System.Data.SqlTypes.SqlXml> 변수로 설정하려면 <xref:System.Data.IDataRecord.GetValue%2A> 메서드보다는 <xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A>을 사용해야 합니다.  
  
> [!NOTE]
>  **AdventureWorks** 샘플 데이터베이스는 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]를 설치할 때 기본적으로 설치되지 않으며  [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 설치 프로그램을 실행하여 설치할 수 있습니다.  
  
 [!code-csharp[DataWorks SqlClient.GetXmlDataReader#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.GetXmlDataReader/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.GetXmlDataReader#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.GetXmlDataReader/VB/source.vb#1)]  
  
## 참고 항목  
 <xref:System.Data.SqlTypes.SqlXml>   
 [SQL Server의 XML 데이터](../../../../../docs/framework/data/adonet/sql/xml-data-in-sql-server.md)   
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)