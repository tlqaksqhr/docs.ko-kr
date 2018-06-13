---
title: 명령을 사용하여 데이터 수정
ms.date: 03/30/2017
ms.assetid: f4160389-b9ff-4b74-b655-437c76dcd586
ms.openlocfilehash: 9f13eb2079df959281a44086edf84c34f3c63a14
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33365046"
---
# <a name="using-commands-to-modify-data"></a><span data-ttu-id="c41cc-102">명령을 사용하여 데이터 수정</span><span class="sxs-lookup"><span data-stu-id="c41cc-102">Using Commands to Modify Data</span></span>
<span data-ttu-id="c41cc-103">.NET Framework 데이터 공급자를 사용하여 저장 프로시저나 CREATE TABLE 및 ALTER COLUMN과 같은 데이터 정의 언어 문을 실행하여 데이터베이스 또는 카탈로그의 스키마를 조작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c41cc-103">Using a .NET Framework data provider, you can execute stored procedures or data definition language statements (for example, CREATE TABLE and ALTER COLUMN) to perform schema manipulation on a database or catalog.</span></span> <span data-ttu-id="c41cc-104">이 명령은 쿼리에서와 같이 행을 반환 하지 않는 하므로 **명령** 개체를 제공는 **ExecuteNonQuery** 처리 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="c41cc-104">These commands do not return rows as a query would, so the **Command** object provides an **ExecuteNonQuery** to process them.</span></span>  
  
 <span data-ttu-id="c41cc-105">사용 하는 것 외에도 **ExecuteNonQuery** 스키마를 수정 하려면 사용할 수도 있습니다이 메서드는 반환 하지 않는 INSERT, UPDATE, 등과 같이 행 및 삭제 하지만 데이터를 수정 하는 SQL 문 처리할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="c41cc-105">In addition to using **ExecuteNonQuery** to modify schema, you can also use this method to process SQL statements that modify data but that do not return rows, such as INSERT, UPDATE, and DELETE.</span></span>  
  
 <span data-ttu-id="c41cc-106">행을 반환 하지는 않지만 **ExecuteNonQuery** 메서드, 입력 및 출력 매개 변수 및 반환 값 전달 하거나 통한 반환할 수 있습니다는 **매개 변수** 의 컬렉션은 **명령**  개체입니다.</span><span class="sxs-lookup"><span data-stu-id="c41cc-106">Although rows are not returned by the **ExecuteNonQuery** method, input and output parameters and return values can be passed and returned via the **Parameters** collection of the **Command** object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c41cc-107">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="c41cc-107">In This Section</span></span>  
 [<span data-ttu-id="c41cc-108">데이터 원본에서 데이터 업데이트</span><span class="sxs-lookup"><span data-stu-id="c41cc-108">Updating Data in a Data Source</span></span>](../../../../docs/framework/data/adonet/updating-data-in-a-data-source.md)  
 <span data-ttu-id="c41cc-109">데이터베이스의 데이터를 수정하는 명령 또는 저장 프로시저를 실행하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c41cc-109">Describes how to execute commands or stored procedures that modify data in a database.</span></span>  
  
 [<span data-ttu-id="c41cc-110">카탈로그 작업 수행</span><span class="sxs-lookup"><span data-stu-id="c41cc-110">Performing Catalog Operations</span></span>](../../../../docs/framework/data/adonet/performing-catalog-operations.md)  
 <span data-ttu-id="c41cc-111">데이터베이스 스키마를 수정하는 명령을 실행하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c41cc-111">Describes how to execute commands that modify database schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c41cc-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c41cc-112">See Also</span></span>  
 [<span data-ttu-id="c41cc-113">ADO.NET에서 데이터 검색 및 수정</span><span class="sxs-lookup"><span data-stu-id="c41cc-113">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [<span data-ttu-id="c41cc-114">명령 및 매개 변수</span><span class="sxs-lookup"><span data-stu-id="c41cc-114">Commands and Parameters</span></span>](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 [<span data-ttu-id="c41cc-115">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="c41cc-115">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
