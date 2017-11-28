---
title: "컨텍스트 연결"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e443ca86-9243-4234-a822-ed10a53a9de0
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: a41c9a526895057a6c7e785abbaaa4e4cd2c490f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="the-context-connection"></a><span data-ttu-id="b9468-102">컨텍스트 연결</span><span class="sxs-lookup"><span data-stu-id="b9468-102">The Context Connection</span></span>
<span data-ttu-id="b9468-103">내부 데이터 액세스 문제는 매우 일반적인 시나리오입니다.</span><span class="sxs-lookup"><span data-stu-id="b9468-103">The problem of internal data access is a fairly common scenario.</span></span> <span data-ttu-id="b9468-104">즉, CLR(공용 언어 런타임) 저장 프로시저나 함수가 실행 중인 서버와 동일한 서버에 액세스하려는 상황을 말합니다.</span><span class="sxs-lookup"><span data-stu-id="b9468-104">That is, you wish to access the same server on which your common language runtime (CLR) stored procedure or function is executing.</span></span> <span data-ttu-id="b9468-105">한 가지 옵션은 <xref:System.Data.SqlClient.SqlConnection>을 사용하여 연결을 만들고 로컬 서버를 가리키는 연결 문자열을 지정한 다음 연결을 여는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b9468-105">One option is to create a connection using <xref:System.Data.SqlClient.SqlConnection>, specify a connection string that points to the local server, and open the connection.</span></span> <span data-ttu-id="b9468-106">이를 수행하려면 로그인에 사용할 자격 증명을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9468-106">This requires specifying credentials for logging in.</span></span> <span data-ttu-id="b9468-107">이 경우 연결이 저장 프로시저나 함수가 아닌 다른 데이터베이스 세션에서 이루어지거나, `SET` 옵션이 서로 다르거나, 연결이 개별 트랜잭션에서 이루어지거나, 임시 테이블에 나타나지 않는 등의 상황이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="b9468-107">The connection is in a different database session than the stored procedure or function, it may have different `SET` options, it is in a separate transaction, it does not see your temporary tables, and so on.</span></span> <span data-ttu-id="b9468-108">관리되는 저장 프로시저나 함수 코드가 SQL Server 프로세스에서 실행되면 해당 서버에 연결된 누군가가 SQL 문을 실행하여 이를 호출했기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="b9468-108">If your managed stored procedure or function code is executing in the SQL Server process, it is because someone connected to that server and executed a SQL statement to invoke it.</span></span> <span data-ttu-id="b9468-109">대개는 저장 프로시저나 함수가 해당 연결의 컨텍스트에서 해당 트랜잭션, `SET` 옵션 등과 함께 실행되기를 원할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b9468-109">You probably want the stored procedure or function to execute in the context of that connection, along with its transaction, `SET` options, and so on.</span></span> <span data-ttu-id="b9468-110">이를 컨텍스트 연결이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9468-110">This is called the context connection.</span></span>  
  
 <span data-ttu-id="b9468-111">컨텍스트 연결을 사용하면 Transact-SQL 문을 처음 코드를 호출한 곳과 동일한 컨텍스트에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9468-111">The context connection lets you execute Transact-SQL statements in the same context that your code was invoked in the first place.</span></span> <span data-ttu-id="b9468-112">자세한 내용을 보려면 현재 사용하고 있는 SQL Server 버전에 해당하는 SQL Server 온라인 설명서 버전을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b9468-112">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="b9468-113">**SQL Server 온라인 설명서**</span><span class="sxs-lookup"><span data-stu-id="b9468-113">**SQL Server Books Online**</span></span>  
  
1.  [<span data-ttu-id="b9468-114">컨텍스트 연결</span><span class="sxs-lookup"><span data-stu-id="b9468-114">The Context Connection</span></span>](http://go.microsoft.com/fwlink/?LinkId=115395)  
  
## <a name="see-also"></a><span data-ttu-id="b9468-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b9468-115">See Also</span></span>  
 [<span data-ttu-id="b9468-116">관리 코드에서 SQL Server 2005 개체 만들기</span><span class="sxs-lookup"><span data-stu-id="b9468-116">Creating SQL Server 2005 Objects In Managed Code</span></span>](http://msdn.microsoft.com/en-us/5358a825-e19b-49aa-8214-674ce5fed1da)  
 [<span data-ttu-id="b9468-117">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="b9468-117">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
