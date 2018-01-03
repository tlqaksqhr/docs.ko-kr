---
title: "방법: 동적으로 데이터베이스 만들기"
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
ms.assetid: fb7f23c4-4572-4c38-9898-a287807d070c
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 27986236c6b693b2c89157229cd79f0de64266e0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-dynamically-create-a-database"></a><span data-ttu-id="20bcf-102">방법: 동적으로 데이터베이스 만들기</span><span class="sxs-lookup"><span data-stu-id="20bcf-102">How to: Dynamically Create a Database</span></span>
<span data-ttu-id="20bcf-103">LINQ to SQL에서 개체 모델은 관계형 데이터베이스에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="20bcf-103">In LINQ to SQL, an object model is mapped to a relational database.</span></span> <span data-ttu-id="20bcf-104">매핑은 특성 기반 매핑 또는 외부 매핑 파일을 사용하여 설정되며 이러한 매핑을 통해 관계형 데이터베이스의 구조를 설명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20bcf-104">Mapping is enabled by using attribute-based mapping or an external mapping file to describe the structure of the relational database.</span></span> <span data-ttu-id="20bcf-105">두 경우 모두 관계형 데이터베이스에 대한 정보가 충분하므로 <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> 메서드를 사용하여 데이터베이스의 새 인스턴스를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20bcf-105">In both scenarios, there is enough information about the relational database that you can create a new instance of the database using the <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="20bcf-106"><xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> 메서드는 개체 모델에 인코딩된 정보의 범위 내에서만 데이터베이스 복제본을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="20bcf-106">The <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> method creates a replica of the database only to the extent of the information encoded in the object model.</span></span> <span data-ttu-id="20bcf-107">개체 모델의 특성 및 매핑 파일이 기존 데이터베이스 구조에 대한 모든 사항을 인코딩하지는 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20bcf-107">Mapping files and attributes from your object model might not encode everything about the structure of an existing database.</span></span> <span data-ttu-id="20bcf-108">매핑 정보는 사용자 정의 함수, 저장 프로시저, 트리거 또는 CHECK 제약 조건의 내용을 나타내지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="20bcf-108">Mapping information does not represent the contents of user-defined functions, stored procedures, triggers, or check constraints.</span></span> <span data-ttu-id="20bcf-109">다양한 데이터베이스에서 이 동작으로 충분합니다.</span><span class="sxs-lookup"><span data-stu-id="20bcf-109">This behavior is sufficient for a variety of databases.</span></span>  
  
 <span data-ttu-id="20bcf-110">Microsoft SQL Server 2008과 같은 데이터 공급자를 사용할 수 있는 경우에는 특히 <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> 메서드를 다양한 시나리오에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20bcf-110">You can use the <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> method in any number of scenarios, especially if a known data provider like Microsoft SQL Server 2008 is available.</span></span> <span data-ttu-id="20bcf-111">일반적인 시나리오는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="20bcf-111">Typical scenarios include the following:</span></span>  
  
-   <span data-ttu-id="20bcf-112">고객 시스템에 자동으로 설치되는 응용 프로그램을 빌드하는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="20bcf-112">You are building an application that automatically installs itself on a customer system.</span></span>  
  
-   <span data-ttu-id="20bcf-113">오프라인 상태를 저장하기 위해 로컬 데이터베이스가 필요한 클라이언트 응용 프로그램을 빌드하는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="20bcf-113">You are building a client application that needs a local database to save its offline state.</span></span>  
  
 <span data-ttu-id="20bcf-114">또한 연결 문자열에 따라 .mdf 파일을 사용하거나 카탈로그 이름을 사용하여 SQL Server에서 <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> 메서드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20bcf-114">You can also use the <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> method with SQL Server by using an .mdf file or a catalog name, depending on your connection string.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="20bcf-115">에서는 연결 문자열을 사용하여 만들려는 데이터베이스와 해당 데이터베이스를 만들 대상 서버를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="20bcf-115"> uses the connection string to define the database to be created and on which server the database is to be created.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="20bcf-116">가능한 경우 연결 문자열에 암호를 사용할 필요가 없도록 Windows 통합 보안을 사용하여 데이터베이스에 연결하세요.</span><span class="sxs-lookup"><span data-stu-id="20bcf-116">Whenever possible, use Windows Integrated Security to connect to the database so that passwords are not required in the connection string.</span></span>  
  
## <a name="example"></a><span data-ttu-id="20bcf-117">예</span><span class="sxs-lookup"><span data-stu-id="20bcf-117">Example</span></span>  
 <span data-ttu-id="20bcf-118">다음 코드에서는 MyDVDs.mdf라는 새 데이터베이스를 만드는 방법에 대한 예를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="20bcf-118">The following code provides an example of how to create a new database named MyDVDs.mdf.</span></span>  
  
 [!code-csharp[DLinqSubmittingChanges#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#5)]
 [!code-vb[DLinqSubmittingChanges#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#5)]  
  
## <a name="example"></a><span data-ttu-id="20bcf-119">예</span><span class="sxs-lookup"><span data-stu-id="20bcf-119">Example</span></span>  
 <span data-ttu-id="20bcf-120">다음과 같이 개체 모델을 사용하여 데이터베이스를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20bcf-120">You can use the object model to create a database by doing the following:</span></span>  
  
 [!code-csharp[DLinqSubmittingChanges#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#6)]
 [!code-vb[DLinqSubmittingChanges#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#6)]  
  
## <a name="example"></a><span data-ttu-id="20bcf-121">예</span><span class="sxs-lookup"><span data-stu-id="20bcf-121">Example</span></span>  
 <span data-ttu-id="20bcf-122">고객 시스템에 자동으로 설치되는 응용 프로그램을 빌드하는 경우에는 해당 데이터베이스가 이미 있는지 확인하여 새 데이터베이스를 만들기 전에 이를 삭제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="20bcf-122">When building an application that automatically installs itself on a  customer system, see if the database already exists and drop it before creating a new one.</span></span> <span data-ttu-id="20bcf-123"><xref:System.Data.Linq.DataContext> 클래스는 이 프로세스를 구현하는 데 도움이 되는 <xref:System.Data.Linq.DataContext.DatabaseExists%2A> 메서드와 <xref:System.Data.Linq.DataContext.DeleteDatabase%2A> 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="20bcf-123">The <xref:System.Data.Linq.DataContext> class provides the <xref:System.Data.Linq.DataContext.DatabaseExists%2A> and <xref:System.Data.Linq.DataContext.DeleteDatabase%2A> methods to help you with this process.</span></span>  
  
 <span data-ttu-id="20bcf-124">다음 예제에서는 이러한 메서드를 사용하여 이를 구현하는 한 가지 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="20bcf-124">The following example shows one way these methods can be used to implement this approach:</span></span>  
  
 [!code-csharp[DLinqSubmittingChanges#7](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#7)]
 [!code-vb[DLinqSubmittingChanges#7](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#7)]  
  
## <a name="see-also"></a><span data-ttu-id="20bcf-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="20bcf-125">See Also</span></span>  
 [<span data-ttu-id="20bcf-126">특성 기반 매핑</span><span class="sxs-lookup"><span data-stu-id="20bcf-126">Attribute-Based Mapping</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md)  
 [<span data-ttu-id="20bcf-127">외부 매핑</span><span class="sxs-lookup"><span data-stu-id="20bcf-127">External Mapping</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md)  
 [<span data-ttu-id="20bcf-128">SQL-CLR 형식 매핑</span><span class="sxs-lookup"><span data-stu-id="20bcf-128">SQL-CLR Type Mapping</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md)  
 [<span data-ttu-id="20bcf-129">배경 정보</span><span class="sxs-lookup"><span data-stu-id="20bcf-129">Background Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)  
 [<span data-ttu-id="20bcf-130">데이터 변경 및 변경 내용 전송</span><span class="sxs-lookup"><span data-stu-id="20bcf-130">Making and Submitting Data Changes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)
