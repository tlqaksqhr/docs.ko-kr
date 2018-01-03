---
title: "SQL XML 열 값"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: d97ce4da-f09c-4d1e-85b7-a0ccedd7246a
caps.latest.revision: "5"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 087a0583c8655f28fcc308768bf75fcaa1d36ef9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="sql-xml-column-values"></a><span data-ttu-id="641a2-102">SQL XML 열 값</span><span class="sxs-lookup"><span data-stu-id="641a2-102">SQL XML Column Values</span></span>
[!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]<span data-ttu-id="641a2-103">에서는 `xml` 데이터 형식을 지원하므로 개발자가 <xref:System.Data.SqlClient.SqlCommand> 클래스의 표준 동작을 사용하여 이 형식이 포함된 결과 집합을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="641a2-103"> supports the `xml` data type, and developers can retrieve result sets including this type using standard behavior of the <xref:System.Data.SqlClient.SqlCommand> class.</span></span> <span data-ttu-id="641a2-104">`xml` 열은 다른 열과 마찬가지 방식으로 검색할 수 있지만(예: <xref:System.Data.SqlClient.SqlDataReader>로) 열의 내용을 XML로 작업하려면 <xref:System.Xml.XmlReader>를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="641a2-104">An `xml` column can be retrieved just as any column is retrieved (into a <xref:System.Data.SqlClient.SqlDataReader>, for example) but if you want to work with the content of the column as XML, you must use an <xref:System.Xml.XmlReader>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="641a2-105">예</span><span class="sxs-lookup"><span data-stu-id="641a2-105">Example</span></span>  
 <span data-ttu-id="641a2-106">다음 콘솔 응용 프로그램 선택 하는 두 개의 행을 포함 하는 `xml` 열에서는 **Sales.Store** 테이블에 **AdventureWorks** 데이터베이스를 <xref:System.Data.SqlClient.SqlDataReader> 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="641a2-106">The following console application selects two rows, each containing an `xml` column, from the **Sales.Store** table in the **AdventureWorks** database to a <xref:System.Data.SqlClient.SqlDataReader> instance.</span></span> <span data-ttu-id="641a2-107">각 행에서 `xml` 열의 값은 <xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A>의 <xref:System.Data.SqlClient.SqlDataReader> 메서드를 사용하여 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="641a2-107">For each row, the value of the `xml` column is read using the <xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A> method of <xref:System.Data.SqlClient.SqlDataReader>.</span></span> <span data-ttu-id="641a2-108">값은 <xref:System.Xml.XmlReader>에 저장되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="641a2-108">The value is stored in an <xref:System.Xml.XmlReader>.</span></span> <span data-ttu-id="641a2-109"><xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A>는 <xref:System.Data.IDataRecord.GetValue%2A> 열의 값을 문자열로 반환하므로 내용을 <xref:System.Data.SqlTypes.SqlXml> 변수로 설정하려면 <xref:System.Data.IDataRecord.GetValue%2A> 메서드보다는 `xml`을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="641a2-109">Note that you must use <xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A> rather than the <xref:System.Data.IDataRecord.GetValue%2A> method if you want to set the contents to a <xref:System.Data.SqlTypes.SqlXml> variable; <xref:System.Data.IDataRecord.GetValue%2A> returns the value of the `xml` column as a string.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="641a2-110">**AdventureWorks** 설치할 때 기본적으로 예제 데이터베이스 설치 되지는 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="641a2-110">The **AdventureWorks** sample database is not installed by default when you install [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="641a2-111">[!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 설치 프로그램을 실행하여 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="641a2-111">You can install it by running [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] Setup.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.GetXmlDataReader#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.GetXmlDataReader/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.GetXmlDataReader#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.GetXmlDataReader/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="641a2-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="641a2-112">See Also</span></span>  
 <xref:System.Data.SqlTypes.SqlXml>  
 [<span data-ttu-id="641a2-113">SQL Server의 XML 데이터</span><span class="sxs-lookup"><span data-stu-id="641a2-113">XML Data in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/xml-data-in-sql-server.md)  
 [<span data-ttu-id="641a2-114">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="641a2-114">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
