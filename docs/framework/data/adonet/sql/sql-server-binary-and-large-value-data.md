---
title: SQL Server 이진 및 큰 값 데이터
ms.date: 03/30/2017
ms.assetid: e00827b3-7511-4b2d-91d7-851ca86cc6b5
ms.openlocfilehash: c0202f6dc17d36fafb28206e17b71fc6d68d88c5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33363408"
---
# <a name="sql-server-binary-and-large-value-data"></a><span data-ttu-id="3dc0d-102">SQL Server 이진 및 큰 값 데이터</span><span class="sxs-lookup"><span data-stu-id="3dc0d-102">SQL Server Binary and Large-Value Data</span></span>
<span data-ttu-id="3dc0d-103">SQL Server에서는 `max`, `varchar` 및 `nvarchar` 데이터 형식의 저장소 용량을 확장하는 `varbinary` 지정자를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="3dc0d-103">SQL Server provides the `max` specifier, which expands the storage capacity of the `varchar`, `nvarchar`, and `varbinary` data types.</span></span> <span data-ttu-id="3dc0d-104">`varchar(max)``nvarchar(max)`, 및 `varbinary(max)` 이라고 *큰 값 데이터 형식*합니다.</span><span class="sxs-lookup"><span data-stu-id="3dc0d-104">`varchar(max)`, `nvarchar(max)`, and `varbinary(max)` are collectively called *large-value data types*.</span></span> <span data-ttu-id="3dc0d-105">큰 값 데이터 형식을 사용하면 데이터를 최대 2^31-1바이트까지 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3dc0d-105">You can use the large-value data types to store up to 2^31-1 bytes of data.</span></span>  
  
 <span data-ttu-id="3dc0d-106">SQL Server 2008에서는 데이터 형식은 아니고 열에 정의할 수 있는 특성인 FILESTREAM 특성을 지원합니다. 이 특성을 사용하면 큰 값 데이터를 데이터베이스가 아니라 파일 시스템에 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3dc0d-106">SQL Server 2008 introduces the FILESTREAM attribute, which is not a data type, but rather an attribute that can be defined on a column, allowing large-value data to be stored on the file system instead of in the database.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3dc0d-107">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="3dc0d-107">In This Section</span></span>  
 [<span data-ttu-id="3dc0d-108">ADO.NET에서 큰 값(최대값) 데이터 수정</span><span class="sxs-lookup"><span data-stu-id="3dc0d-108">Modifying Large-Value (max) Data in ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/modifying-large-value-max-data.md)  
 <span data-ttu-id="3dc0d-109">큰 값 데이터 형식을 사용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3dc0d-109">Describes how to work with the large-value data types.</span></span>  
  
 [<span data-ttu-id="3dc0d-110">FILESTREAM 데이터</span><span class="sxs-lookup"><span data-stu-id="3dc0d-110">FILESTREAM Data</span></span>](../../../../../docs/framework/data/adonet/sql/filestream-data.md)  
 <span data-ttu-id="3dc0d-111">FILESTREAM 특성을 사용하여 SQL Server 2008에 저장된 큰 값 데이터로 작업하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3dc0d-111">Describes how to work with large-value data stored in SQL Server 2008 with the FILESTREAM attribute.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3dc0d-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3dc0d-112">See Also</span></span>  
 [<span data-ttu-id="3dc0d-113">SQL Server 데이터 형식 및 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="3dc0d-113">SQL Server Data Types and ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-data-types.md)  
 [<span data-ttu-id="3dc0d-114">ADO.NET에서 SQL Server 데이터 작업</span><span class="sxs-lookup"><span data-stu-id="3dc0d-114">SQL Server Data Operations in ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-data-operations.md)  
 [<span data-ttu-id="3dc0d-115">ADO.NET에서 데이터 검색 및 수정</span><span class="sxs-lookup"><span data-stu-id="3dc0d-115">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [<span data-ttu-id="3dc0d-116">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="3dc0d-116">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
