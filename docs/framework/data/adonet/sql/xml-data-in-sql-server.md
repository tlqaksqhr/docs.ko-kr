---
title: "SQL Server의 XML 데이터"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9849d319-f518-4e3d-a7cd-f8fdcaaa1d4d
caps.latest.revision: "5"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 712630938989e2187042e8ab143361da664e6bcf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="xml-data-in-sql-server"></a><span data-ttu-id="60bfe-102">SQL Server의 XML 데이터</span><span class="sxs-lookup"><span data-stu-id="60bfe-102">XML Data in SQL Server</span></span>
<span data-ttu-id="60bfe-103">SQL Server에서는 .NET Framework 내에 SQLXML의 기능을 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="60bfe-103">SQL Server exposes the functionality of SQLXML inside the .NET Framework.</span></span> <span data-ttu-id="60bfe-104">개발자는 SQL Server 인스턴스에서 XML 데이터에 액세스하고 데이터를 .NET Framework 환경으로 가져와 처리한 다음 업데이트를 다시 SQL Server로 보내는 응용 프로그램을 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60bfe-104">Developers can write applications that access XML data from an instance of SQL Server, bring the data into the .NET Framework environment, process the data, and send the updates back to SQL Server.</span></span> <span data-ttu-id="60bfe-105">SQL Server에서는 데이터 저장소 및 데이터 검색을 위한 매개 변수 값을 비롯하여 여러 가지 방식으로 XML 데이터를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60bfe-105">XML data can be used in several ways in SQL Server, including data storage, and as parameter values for retrieving data.</span></span> <span data-ttu-id="60bfe-106">**SqlXml** .NET Framework의 클래스는 SQL Server 내의 XML 열에 저장 된 데이터를 사용 하기 위한 클라이언트 쪽 지원을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="60bfe-106">The **SqlXml** class in the .NET Framework provides the client-side support for working with data stored in an XML column within SQL Server.</span></span> <span data-ttu-id="60bfe-107">자세한 내용은 SQL Server 온라인 설명서의 "SQLXML Managed Classes"를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="60bfe-107">For more information, see "SQLXML Managed Classes" in SQL Server Books Online.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="60bfe-108">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="60bfe-108">In This Section</span></span>  
 [<span data-ttu-id="60bfe-109">SQL XML 열 값</span><span class="sxs-lookup"><span data-stu-id="60bfe-109">SQL XML Column Values</span></span>](../../../../../docs/framework/data/adonet/sql/sql-xml-column-values.md)  
 <span data-ttu-id="60bfe-110">SQL Server에서 XML 데이터를 검색하고 검색한 데이터로 작업하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="60bfe-110">Demonstrates how to retrieve and work with XML data retrieved from SQL Server.</span></span>  
  
 [<span data-ttu-id="60bfe-111">XML 값을 매개 변수로 지정</span><span class="sxs-lookup"><span data-stu-id="60bfe-111">Specifying XML Values as Parameters</span></span>](../../../../../docs/framework/data/adonet/sql/specifying-xml-values-as-parameters.md)  
 <span data-ttu-id="60bfe-112">XML 데이터를 매개 변수로 명령에 전달하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="60bfe-112">Demonstrates how to pass XML data as a parameter to a command.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60bfe-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="60bfe-113">See Also</span></span>  
 [<span data-ttu-id="60bfe-114">SQL Server 및 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="60bfe-114">SQL Server and ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/index.md)  
 [<span data-ttu-id="60bfe-115">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="60bfe-115">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
