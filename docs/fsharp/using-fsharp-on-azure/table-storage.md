---
title: 'F #을 사용 하 여 Azure 테이블 저장소 시작'
description: Azure 테이블 저장소 또는 Azure Cosmos DB를 사용 하 여 클라우드에서 구조화 된 데이터를 저장 합니다.
author: sylvanc
ms.date: 03/26/2018
ms.openlocfilehash: ac81bc88db1436aa4d5f576da61a90839df04b99
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33575403"
---
# <a name="get-started-with-azure-table-storage-and-the-azure-cosmos-db-table-api-using-f"></a><span data-ttu-id="08cd0-103">Azure 테이블 저장소 및 F #을 사용 하 여 Azure Cosmos DB 테이블 API 시작</span><span class="sxs-lookup"><span data-stu-id="08cd0-103">Get started with Azure Table storage and the Azure Cosmos DB Table API using F#</span></span> # 

<span data-ttu-id="08cd0-104">Azure 테이블 저장소는 클라우드에서 구조화 된 NoSQL 데이터를 저장 하는 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="08cd0-104">Azure Table storage is a service that stores structured NoSQL data in the cloud.</span></span> <span data-ttu-id="08cd0-105">테이블 저장소는 schemaless 디자인에 키/특성 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="08cd0-105">Table storage is a key/attribute store with a schemaless design.</span></span> <span data-ttu-id="08cd0-106">테이블 저장소 schemaless 이기 때문에 응용 프로그램 evolve 필요에 따라 데이터에 맞게 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="08cd0-106">Because Table storage is schemaless, it's easy to adapt your data as the needs of your application evolve.</span></span> <span data-ttu-id="08cd0-107">데이터에 대 한 액세스가 신속 하 고 모든 종류의 응용 프로그램에 대 한 비용 효율적인 합니다.</span><span class="sxs-lookup"><span data-stu-id="08cd0-107">Access to data is fast and cost-effective for all kinds of applications.</span></span> <span data-ttu-id="08cd0-108">테이블 저장소 일반적으로 보다 훨씬 낮습니다 비용에 유사한 데이터 볼륨에 대 한 기존의 SQL 합니다.</span><span class="sxs-lookup"><span data-stu-id="08cd0-108">Table storage is typically significantly lower in cost than traditional SQL for similar volumes of data.</span></span>

<span data-ttu-id="08cd0-109">웹 응용 프로그램, 주소록, 장치 정보 및 다른 유형의 서비스에 필요한 메타 데이터에 대 한 사용자 데이터와 같이 유연한 데이터 집합을 저장할 테이블 저장소를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08cd0-109">You can use Table storage to store flexible datasets, such as user data for web applications, address books, device information, and any other type of metadata that your service requires.</span></span> <span data-ttu-id="08cd0-110">테이블의 모든 엔터티 수를 저장할 수 있습니다 및 저장소 계정에는 임의 개수의 테이블 저장소 계정의 용량 제한까지 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08cd0-110">You can store any number of entities in a table, and a storage account may contain any number of tables, up to the capacity limit of the storage account.</span></span>

<span data-ttu-id="08cd0-111">Azure Cosmos DB premium 기능을 같은 하 게 해야 하 고 Azure 테이블 저장소에 대해 작성 된 응용 프로그램에 대 한 테이블 API를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="08cd0-111">Azure Cosmos DB provides the Table API for applications that are written for Azure Table storage and that require premium capabilities such as:</span></span>

- <span data-ttu-id="08cd0-112">턴키 글로벌 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="08cd0-112">Turnkey global distribution.</span></span>
- <span data-ttu-id="08cd0-113">전 세계 처리량 전용된입니다.</span><span class="sxs-lookup"><span data-stu-id="08cd0-113">Dedicated throughput worldwide.</span></span>
- <span data-ttu-id="08cd0-114">단일 자리 숫자 밀리초 대기 99 번째 백분위 수입니다.</span><span class="sxs-lookup"><span data-stu-id="08cd0-114">Single-digit millisecond latencies at the 99th percentile.</span></span>
- <span data-ttu-id="08cd0-115">고가용성을 보장 합니다.</span><span class="sxs-lookup"><span data-stu-id="08cd0-115">Guaranteed high availability.</span></span>
- <span data-ttu-id="08cd0-116">자동 보조 인덱싱하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08cd0-116">Automatic secondary indexing.</span></span>

<span data-ttu-id="08cd0-117">Azure 테이블 저장소에 대해 작성 된 응용 프로그램 코드 변경 없이 테이블 API를 사용 하 여 Azure Cosmos DB에 마이그레이션할 수 및 프리미엄 기능을 합니다.</span><span class="sxs-lookup"><span data-stu-id="08cd0-117">Applications written for Azure Table storage can migrate to Azure Cosmos DB by using the Table API with no code changes and take advantage of premium capabilities.</span></span> <span data-ttu-id="08cd0-118">테이블 API에는.NET, Java, Python 및 Node.js 용 클라이언트 Sdk를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08cd0-118">The Table API has client SDKs available for .NET, Java, Python, and Node.js.</span></span>

<span data-ttu-id="08cd0-119">자세한 내용은 참조 [Azure Cosmos DB 테이블 API 소개](https://docs.microsoft.com/azure/cosmos-db/table-introduction)합니다.</span><span class="sxs-lookup"><span data-stu-id="08cd0-119">For more information, see [Introduction to Azure Cosmos DB Table API](https://docs.microsoft.com/azure/cosmos-db/table-introduction).</span></span>

## <a name="about-this-tutorial"></a><span data-ttu-id="08cd0-120">이 자습서 정보</span><span class="sxs-lookup"><span data-stu-id="08cd0-120">About this tutorial</span></span>

<span data-ttu-id="08cd0-121">이 자습서에서는 Azure 테이블 저장소 또는 Azure Cosmos DB 테이블 API, 만들기 및 테이블을 삭제 및 삽입, 업데이트, 삭제 및 쿼리 하는 테이블 데이터를 포함 하 여 사용 하 여 몇 가지 일반적인 작업을 수행 하는 F # 코드를 작성 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="08cd0-121">This tutorial shows how to write F# code to do some common tasks using Azure Table storage or the Azure Cosmos DB Table API, including creating and deleting a table and inserting, updating, deleting, and querying table data.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="08cd0-122">전제 조건</span><span class="sxs-lookup"><span data-stu-id="08cd0-122">Prerequisites</span></span>

<span data-ttu-id="08cd0-123">이 가이드를 사용 하려면 먼저 [Azure 저장소 계정 만들기](/azure/storage/storage-create-storage-account) 또는 [Azure Cosmos DB 계정](https://azure.microsoft.com/try/cosmosdb/)합니다.</span><span class="sxs-lookup"><span data-stu-id="08cd0-123">To use this guide, you must first [create an Azure storage account](/azure/storage/storage-create-storage-account) or [Azure Cosmos DB account](https://azure.microsoft.com/try/cosmosdb/).</span></span>


## <a name="create-an-f-script-and-start-f-interactive"></a><span data-ttu-id="08cd0-124">만들기는 F # 스크립트와 시작 F # 대화형</span><span class="sxs-lookup"><span data-stu-id="08cd0-124">Create an F# Script and Start F# Interactive</span></span>

<span data-ttu-id="08cd0-125">이 문서에 있는 예제에서 F # 응용 프로그램 또는 F # 스크립트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08cd0-125">The samples in this article can be used in either an F# application or an F# script.</span></span> <span data-ttu-id="08cd0-126">F # 스크립트를 만들려면으로 파일 만들기는 `.fsx` 예를 들어 확장 `tables.fsx`, F # 개발 환경에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="08cd0-126">To create an F# script, create a file with the `.fsx` extension, for example `tables.fsx`, in your F# development environment.</span></span>

<span data-ttu-id="08cd0-127">를 사용 하 여 한 [패키지 관리자](package-management.md) 와 같은 [Paket](https://fsprojects.github.io/Paket/) 또는 [NuGet](https://www.nuget.org/) 를 설치 하는 `WindowsAzure.Storage` 패키지와 참조 `WindowsAzure.Storage.dll` 는 를사용하여스크립트에서`#r`지시문입니다.</span><span class="sxs-lookup"><span data-stu-id="08cd0-127">Next, use a [package manager](package-management.md) such as [Paket](https://fsprojects.github.io/Paket/) or [NuGet](https://www.nuget.org/) to install the `WindowsAzure.Storage` package and reference `WindowsAzure.Storage.dll` in your script using a `#r` directive.</span></span> <span data-ttu-id="08cd0-128">에 대해 다시 수행 `Microsoft.WindowsAzure.ConfigurationManager` Microsoft.Azure 네임 스페이스를 얻기 위해 합니다.</span><span class="sxs-lookup"><span data-stu-id="08cd0-128">Do it again for `Microsoft.WindowsAzure.ConfigurationManager` in order to get the Microsoft.Azure namespace.</span></span>

### <a name="add-namespace-declarations"></a><span data-ttu-id="08cd0-129">네임 스페이스 선언을 추가합니다</span><span class="sxs-lookup"><span data-stu-id="08cd0-129">Add namespace declarations</span></span>

<span data-ttu-id="08cd0-130">다음 추가 `open` 문을의 맨 위에 `tables.fsx` 파일:</span><span class="sxs-lookup"><span data-stu-id="08cd0-130">Add the following `open` statements to the top of the `tables.fsx` file:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L1-L5)]

### <a name="get-your-azure-storage-connection-string"></a><span data-ttu-id="08cd0-131">Azure 저장소 연결 문자열 가져오기</span><span class="sxs-lookup"><span data-stu-id="08cd0-131">Get your Azure Storage connection string</span></span>

<span data-ttu-id="08cd0-132">Azure 저장소 테이블 서비스에 연결 하는 경우이 자습서에 대 한 연결 문자열을 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="08cd0-132">If you're connecting to Azure Storage Table service, you'll need your connection string for this tutorial.</span></span> <span data-ttu-id="08cd0-133">Azure 포털에서 연결 문자열을 복사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08cd0-133">You can copy your connection string from the Azure portal.</span></span> <span data-ttu-id="08cd0-134">연결 문자열에 대 한 자세한 내용은 참조 [저장소 연결 문자열 구성](/azure/storage/storage-configure-connection-string)합니다.</span><span class="sxs-lookup"><span data-stu-id="08cd0-134">For more information about connection strings, see [Configure Storage Connection Strings](/azure/storage/storage-configure-connection-string).</span></span>

### <a name="get-your-azure-cosmos-db-connection-string"></a><span data-ttu-id="08cd0-135">Azure Cosmos DB 연결 문자열 가져오기</span><span class="sxs-lookup"><span data-stu-id="08cd0-135">Get your Azure Cosmos DB connection string</span></span>

<span data-ttu-id="08cd0-136">Azure Cosmos DB에 연결 하는 경우이 자습서에 대 한 연결 문자열을 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="08cd0-136">If you're connecting to Azure Cosmos DB, you'll need your connection string for this tutorial.</span></span> <span data-ttu-id="08cd0-137">Azure 포털에서 연결 문자열을 복사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08cd0-137">You can copy your connection string from the Azure portal.</span></span> <span data-ttu-id="08cd0-138">Cosmos DB 계정에 Azure 포털에서로 이동 **설정** > **연결 문자열**를 클릭 하 고는 **복사** 기본 연결을 복사 하는 단추 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="08cd0-138">In the Azure portal, in your Cosmos DB account, go to **Settings** > **Connection String**, and click the **Copy** button to copy your Primary Connection String.</span></span> 

<span data-ttu-id="08cd0-139">이 자습서에서는 다음 예제와 같은 스크립트에서 연결 문자열을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="08cd0-139">For the tutorial, enter your connection string in your script, like the following example:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L11-L11)]

<span data-ttu-id="08cd0-140">그러나이 방법은 **좋지** 를 실제 프로젝트.</span><span class="sxs-lookup"><span data-stu-id="08cd0-140">However, this is **not recommended** for real projects.</span></span> <span data-ttu-id="08cd0-141">저장소 계정 키 저장소 계정에 대 한 루트 암호와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="08cd0-141">Your storage account key is similar to the root password for your storage account.</span></span> <span data-ttu-id="08cd0-142">항상 저장소 계정 키를 보호 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="08cd0-142">Always be careful to protect your storage account key.</span></span> <span data-ttu-id="08cd0-143">하드 코딩을 다른 사용자에 게 액세스가 허용 되는 일반 텍스트 파일에 저장 하거나 다른 사용자에 게 배포 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="08cd0-143">Avoid distributing it to other users, hard-coding it, or saving it in a plain-text file that is accessible to others.</span></span> <span data-ttu-id="08cd0-144">노출 되었다고 판단 되 면 Azure 포털을 사용 하 여 키를 다시 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08cd0-144">You can regenerate your key using the Azure Portal if you believe it may have been compromised.</span></span>

<span data-ttu-id="08cd0-145">실제 응용 프로그램 저장소 연결 문자열을 유지 관리 하는 가장 좋은 방법은 구성 파일에는 합니다.</span><span class="sxs-lookup"><span data-stu-id="08cd0-145">For real applications, the best way to maintain your storage connection string is in a configuration file.</span></span> <span data-ttu-id="08cd0-146">구성 파일에서 연결 문자열을 페치 하려면이 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08cd0-146">To fetch the connection string from a configuration file, you can do this:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L13-L15)]

<span data-ttu-id="08cd0-147">Azure 구성 관리자를 사용 하는 것은 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="08cd0-147">Using Azure Configuration Manager is optional.</span></span> <span data-ttu-id="08cd0-148">.NET Framework 등의 API를 사용할 수도 있습니다 `ConfigurationManager` 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="08cd0-148">You can also use an API such as the .NET Framework's `ConfigurationManager` type.</span></span>

### <a name="parse-the-connection-string"></a><span data-ttu-id="08cd0-149">연결 문자열을 구문 분석</span><span class="sxs-lookup"><span data-stu-id="08cd0-149">Parse the connection string</span></span>

<span data-ttu-id="08cd0-150">연결 문자열을 구문 분석 하려면 다음을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="08cd0-150">To parse the connection string, use:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L21-L22)]

<span data-ttu-id="08cd0-151">반환 합니다.는 `CloudStorageAccount`합니다.</span><span class="sxs-lookup"><span data-stu-id="08cd0-151">This returns a `CloudStorageAccount`.</span></span>

### <a name="create-the-table-service-client"></a><span data-ttu-id="08cd0-152">테이블 서비스 클라이언트 만들기</span><span class="sxs-lookup"><span data-stu-id="08cd0-152">Create the Table service client</span></span>

<span data-ttu-id="08cd0-153">`CloudTableClient` 클래스를 사용 하면 테이블 및 테이블 저장소에 엔터티를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08cd0-153">The `CloudTableClient` class enables you to retrieve tables and entities in Table storage.</span></span> <span data-ttu-id="08cd0-154">서비스 클라이언트를 만드는 한 가지 방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="08cd0-154">Here's one way to create the service client:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L28-L29)]

<span data-ttu-id="08cd0-155">이제 데이터를 읽고 데이터를 테이블 저장소에 기록 하는 코드를 작성할 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="08cd0-155">Now you are ready to write code that reads data from and writes data to Table storage.</span></span>

### <a name="create-a-table"></a><span data-ttu-id="08cd0-156">테이블 만들기</span><span class="sxs-lookup"><span data-stu-id="08cd0-156">Create a table</span></span>

<span data-ttu-id="08cd0-157">이 예제에는 아직 없는 경우 테이블을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="08cd0-157">This example shows how to create a table if it does not already exist:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L35-L39)]

### <a name="add-an-entity-to-a-table"></a><span data-ttu-id="08cd0-158">테이블에 엔터티 추가</span><span class="sxs-lookup"><span data-stu-id="08cd0-158">Add an entity to a table</span></span>

<span data-ttu-id="08cd0-159">상속 되는 형식에 엔터티 `TableEntity`합니다.</span><span class="sxs-lookup"><span data-stu-id="08cd0-159">An entity has to have a type that inherits from `TableEntity`.</span></span> <span data-ttu-id="08cd0-160">확장할 수 있습니다 `TableEntity` , 원하는 어떤 방법으로든 있지만 형식이 *해야* 매개 변수 없는 생성자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08cd0-160">You can extend `TableEntity` in any way you like, but your type *must* have a parameter-less constructor.</span></span> <span data-ttu-id="08cd0-161">둘 다 있는 속성만 `get` 및 `set` Azure 테이블에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="08cd0-161">Only properties that have both `get` and `set` are stored in your Azure Table.</span></span>

<span data-ttu-id="08cd0-162">엔터티의 파티션과 행 키는 테이블의 엔터티를 고유 하 게 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="08cd0-162">An entity's partition and row key uniquely identify the entity in the table.</span></span> <span data-ttu-id="08cd0-163">동일한 파티션 키를 가진 엔터티가 다른 파티션 키를 사용 하는 것 보다 더 빠르게 쿼리할 수 있지만 다양 한 파티션 키를 사용 하 여 병렬 작업의 확장성을 높일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08cd0-163">Entities with the same partition key can be queried faster than those with different partition keys, but using diverse partition keys allows for greater scalability of parallel operations.</span></span>

<span data-ttu-id="08cd0-164">예로 `Customer` 를 사용 하 여 `lastName` 파티션 키로 및 `firstName` 행 키로 합니다.</span><span class="sxs-lookup"><span data-stu-id="08cd0-164">Here's an example of a `Customer` that uses the `lastName` as the partition key and the `firstName` as the row key.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L45-L52)]

<span data-ttu-id="08cd0-165">이제 추가 `Customer` 테이블에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08cd0-165">Now add `Customer` to the table.</span></span> <span data-ttu-id="08cd0-166">이렇게 하려면 만듭니다는 `TableOperation` 테이블에서 실행 하는입니다.</span><span class="sxs-lookup"><span data-stu-id="08cd0-166">To do so, create a `TableOperation` that executes on the table.</span></span> <span data-ttu-id="08cd0-167">이 경우에 만듭니다는 `Insert` 작업 합니다.</span><span class="sxs-lookup"><span data-stu-id="08cd0-167">In this case, you create an `Insert` operation.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L54-L55)]

### <a name="insert-a-batch-of-entities"></a><span data-ttu-id="08cd0-168">엔터티 일괄 처리를 삽입 합니다.</span><span class="sxs-lookup"><span data-stu-id="08cd0-168">Insert a batch of entities</span></span>

<span data-ttu-id="08cd0-169">엔터티 일괄 처리를 단일 쓰기 작업을 사용 하 여 테이블에 삽입할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08cd0-169">You can insert a batch of entities into a table using a single write operation.</span></span> <span data-ttu-id="08cd0-170">일괄 처리 작업을 사용 하면 단일 실행으로 작업을 결합할 수 있도록 하지만 몇 가지 제한 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08cd0-170">Batch operations allow you to combine operations into a single execution, but they have some restrictions:</span></span>

- <span data-ttu-id="08cd0-171">업데이트를 수행할 수 있습니다, 삭제 하 고 동일한 일괄 처리 작업에서 삽입 합니다.</span><span class="sxs-lookup"><span data-stu-id="08cd0-171">You can perform updates, deletes, and inserts in the same batch operation.</span></span>
- <span data-ttu-id="08cd0-172">일괄 처리 작업을 100 개까지 엔터티를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08cd0-172">A batch operation can include up to 100 entities.</span></span>
- <span data-ttu-id="08cd0-173">일괄 처리 작업의 모든 엔터티가 동일한 파티션 키에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="08cd0-173">All entities in a batch operation must have the same partition key.</span></span>
- <span data-ttu-id="08cd0-174">일괄 작업에서 쿼리를 수행 하는 가능 하지만 일괄 처리에서 유일한 작업 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="08cd0-174">While it is possible to perform a query in a batch operation, it must be the only operation in the batch.</span></span>

<span data-ttu-id="08cd0-175">두 삽입 일괄 처리 작업으로 결합 하는 일부 코드는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="08cd0-175">Here's some code that combines two inserts into a batch operation:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L62-L71)]

### <a name="retrieve-all-entities-in-a-partition"></a><span data-ttu-id="08cd0-176">파티션의 모든 엔터티 검색</span><span class="sxs-lookup"><span data-stu-id="08cd0-176">Retrieve all entities in a partition</span></span>

<span data-ttu-id="08cd0-177">파티션에서 모든 엔터티의 테이블을 쿼리를 사용 하 여 한 `TableQuery` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="08cd0-177">To query a table for all entities in a partition, use a `TableQuery` object.</span></span> <span data-ttu-id="08cd0-178">여기에서 필터링 할 엔터티에 대 한 "Smith"은 파티션 키입니다.</span><span class="sxs-lookup"><span data-stu-id="08cd0-178">Here, you filter for entities where "Smith" is the partition key.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L77-L82)]

<span data-ttu-id="08cd0-179">이제 결과 인쇄 합니다.</span><span class="sxs-lookup"><span data-stu-id="08cd0-179">You now print the results:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L84-L85)]


### <a name="retrieve-a-range-of-entities-in-a-partition"></a><span data-ttu-id="08cd0-180">다양 한 파티션에 엔터티를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="08cd0-180">Retrieve a range of entities in a partition</span></span>

<span data-ttu-id="08cd0-181">파티션의 모든 엔터티를 쿼리 하려는 하지 않는 경우에 행 키 필터와 파티션 키 필터를 결합 하 여 범위를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08cd0-181">If you don't want to query all the entities in a partition, you can specify a range by combining the partition key filter with a row key filter.</span></span> <span data-ttu-id="08cd0-182">여기에서는 두 개의 필터를 사용 하면 "Smith" 파티션에 있는 모든 엔터티를 가져올 위치 행 키 (이름) 문자로 시작 알파벳의 "M" 보다 이전입니다.</span><span class="sxs-lookup"><span data-stu-id="08cd0-182">Here, you use two filters to get all entities in the "Smith" partition where the row key (first name) starts with a letter earlier than "M" in the alphabet.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L91-L100)]

<span data-ttu-id="08cd0-183">이제 결과 인쇄 합니다.</span><span class="sxs-lookup"><span data-stu-id="08cd0-183">You now print the results:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L102-L103)]

### <a name="retrieve-a-single-entity"></a><span data-ttu-id="08cd0-184">단일 엔터티를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="08cd0-184">Retrieve a single entity</span></span>

<span data-ttu-id="08cd0-185">단일, 특정 엔터티를 검색 하는 쿼리를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08cd0-185">You can write a query to retrieve a single, specific entity.</span></span> <span data-ttu-id="08cd0-186">사용 하는 여기에서 `TableOperation` "Ben Smith" 고객을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08cd0-186">Here, you use a `TableOperation` to specify the customer "Ben Smith".</span></span> <span data-ttu-id="08cd0-187">컬렉션을 대신 얻게는 `Customer`합니다.</span><span class="sxs-lookup"><span data-stu-id="08cd0-187">Instead of a collection, you get back a `Customer`.</span></span> <span data-ttu-id="08cd0-188">쿼리에서 파티션 키와 행 키를 지정 하는 테이블 서비스에서 단일 엔터티를 검색 하는 가장 빠른 방법은.</span><span class="sxs-lookup"><span data-stu-id="08cd0-188">Specifying both the partition key and the row key in a query is the fastest way to retrieve a single entity from the Table service.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L109-L111)]

<span data-ttu-id="08cd0-189">이제 결과 인쇄 합니다.</span><span class="sxs-lookup"><span data-stu-id="08cd0-189">You now print the results:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L113-L115)]


### <a name="replace-an-entity"></a><span data-ttu-id="08cd0-190">엔터티를 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="08cd0-190">Replace an entity</span></span>

<span data-ttu-id="08cd0-191">엔터티를 업데이트 하려면 테이블 서비스에서 검색, 엔터티 개체를 수정 하 고 다음 변경 내용을 사용 하 여 테이블 서비스에 다시 저장 된 `Replace` 작업 합니다.</span><span class="sxs-lookup"><span data-stu-id="08cd0-191">To update an entity, retrieve it from the Table service, modify the entity object, and then save the changes back to the Table service using a `Replace` operation.</span></span> <span data-ttu-id="08cd0-192">이렇게 하면 작업이 실패 하는 경우, 검색 된 이후 서버에서 엔터티가 변경 되지 않은 엔터티는 서버에서 완전히 대체 됩니다.</span><span class="sxs-lookup"><span data-stu-id="08cd0-192">This causes the entity to be fully replaced on the server, unless the entity on the server has changed since it was retrieved, in which case the operation fails.</span></span> <span data-ttu-id="08cd0-193">이 오류는 응용 프로그램에서 다른 소스 로부터 변경 내용을 실수로 덮어쓰지 않도록 되려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="08cd0-193">This failure is to prevent your application from inadvertently overwriting changes from other sources.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L121-L128)]

### <a name="insert-or-replace-an-entity"></a><span data-ttu-id="08cd0-194">삽입 또는 바꾸기 기능 엔터티</span><span class="sxs-lookup"><span data-stu-id="08cd0-194">Insert-or-replace an entity</span></span>

<span data-ttu-id="08cd0-195">경우에 따라 엔터티 테이블에 있는지에 대해 모릅니다.</span><span class="sxs-lookup"><span data-stu-id="08cd0-195">Sometimes, you don't know whether an entity exists in the table.</span></span> <span data-ttu-id="08cd0-196">그렇지 않으면에 저장 된 현재 값은 더 이상 필요 하지 않으며</span><span class="sxs-lookup"><span data-stu-id="08cd0-196">And if it does, the current values stored in it are no longer needed.</span></span> <span data-ttu-id="08cd0-197">사용할 수 있습니다 `InsertOrReplace` 엔터티를 만들거나 해당 상태에 관계 없이, 있는 경우 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="08cd0-197">You can use `InsertOrReplace` to create the entity, or replace it if it exists, regardless of its state.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L134-L141)]

### <a name="query-a-subset-of-entity-properties"></a><span data-ttu-id="08cd0-198">엔터티 속성의 하위 집합을 쿼리</span><span class="sxs-lookup"><span data-stu-id="08cd0-198">Query a subset of entity properties</span></span>

<span data-ttu-id="08cd0-199">테이블 쿼리 전체가 아닌 엔터티에서 몇 개의 속성을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08cd0-199">A table query can retrieve just a few properties from an entity instead of all of them.</span></span> <span data-ttu-id="08cd0-200">투영 이라는이 방법을 큰 엔터티를 위해 특별히 쿼리 성능을 향상 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08cd0-200">This technique, called projection, can improve query performance, especially for large entities.</span></span> <span data-ttu-id="08cd0-201">만 전자 메일 주소를 사용 하 여 반환 여기서 `DynamicTableEntity` 및 `EntityResolver`합니다.</span><span class="sxs-lookup"><span data-stu-id="08cd0-201">Here, you return only email addresses using `DynamicTableEntity` and `EntityResolver`.</span></span> <span data-ttu-id="08cd0-202">참고가이 코드는 테이블 서비스 계정을 사용 하는 경우에 실행 되므로 프로젝션 로컬 저장소 에뮬레이터에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="08cd0-202">Note that projection is not supported on the local storage emulator, so this code runs only when you're using an account on the Table service.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L147-L158)]

### <a name="retrieve-entities-in-pages-asynchronously"></a><span data-ttu-id="08cd0-203">페이지에서 엔터티를 비동기적으로 검색</span><span class="sxs-lookup"><span data-stu-id="08cd0-203">Retrieve entities in pages asynchronously</span></span>

<span data-ttu-id="08cd0-204">많은 엔터티를 읽고 있는 모두 반환을 기다리지 않고 검색 된 때 처리 하려는 경우에 조각화 된 쿼리를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08cd0-204">If you are reading a large number of entities, and you want to process them as they are retrieved rather than waiting for them all to return, you can use a segmented query.</span></span> <span data-ttu-id="08cd0-205">여기에서 있습니다 결과 페이지에서 사용 하 여 반환 비동기 워크플로 반환할 결과의 큰 집합에 대 한 대기 하는 동안 실행이 차단 되지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="08cd0-205">Here, you return results in pages by using an async workflow so that execution is not blocked while you're waiting for a large set of results to return.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L163-L178)]

<span data-ttu-id="08cd0-206">하면 이제이 계산이 동기적으로 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="08cd0-206">You now execute this computation synchronously:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L180-L180)]

### <a name="delete-an-entity"></a><span data-ttu-id="08cd0-207">엔터티 삭제</span><span class="sxs-lookup"><span data-stu-id="08cd0-207">Delete an entity</span></span>

<span data-ttu-id="08cd0-208">검색 한 후 엔터티를 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08cd0-208">You can delete an entity after you have retrieved it.</span></span> <span data-ttu-id="08cd0-209">엔터티를 업데이트할와 마찬가지로이 실패 하면 엔터티 것으로 검색 한 이후 변경 된 경우.</span><span class="sxs-lookup"><span data-stu-id="08cd0-209">As with updating an entity, this fails if the entity has changed since you retrieved it.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L186-L187)]

### <a name="delete-a-table"></a><span data-ttu-id="08cd0-210">테이블 삭제</span><span class="sxs-lookup"><span data-stu-id="08cd0-210">Delete a table</span></span>

<span data-ttu-id="08cd0-211">저장소 계정에서 테이블을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08cd0-211">You can delete a table from a storage account.</span></span> <span data-ttu-id="08cd0-212">삭제 된 테이블 삭제 후 일정 기간에 대 한 다시 만들어야 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="08cd0-212">A table that has been deleted will be unavailable to be re-created for a period of time following the deletion.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L193-L193)]

## <a name="next-steps"></a><span data-ttu-id="08cd0-213">다음 단계</span><span class="sxs-lookup"><span data-stu-id="08cd0-213">Next steps</span></span>

<span data-ttu-id="08cd0-214">테이블 저장소의 기본 사항 학습 한, 했으므로 더 복잡 한 저장소 작업 및 Azure Cosmos DB 테이블 API에 대 한 자세한 내용은 다음이 링크를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="08cd0-214">Now that you've learned the basics of Table storage, follow these links to learn about more complex storage tasks and the Azure Cosmos DB Table API.</span></span>

- [<span data-ttu-id="08cd0-215">Azure Cosmos DB 테이블 API 소개</span><span class="sxs-lookup"><span data-stu-id="08cd0-215">Introduction to Azure Cosmos DB Table API</span></span>](https://docs.microsoft.com/azure/cosmos-db/table-introduction)
- [<span data-ttu-id="08cd0-216">.NET 참조 용 저장소 클라이언트 라이브러리</span><span class="sxs-lookup"><span data-stu-id="08cd0-216">Storage Client Library for .NET reference</span></span>](https://docs.microsoft.com/dotnet/api/overview/azure/storage?view=azure-dotnet)
- [<span data-ttu-id="08cd0-217">Azure 저장소 형식 공급자</span><span class="sxs-lookup"><span data-stu-id="08cd0-217">Azure Storage Type Provider</span></span>](http://fsprojects.github.io/AzureStorageTypeProvider/)
- [<span data-ttu-id="08cd0-218">Azure 저장소 팀 블로그</span><span class="sxs-lookup"><span data-stu-id="08cd0-218">Azure Storage Team Blog</span></span>](http://blogs.msdn.com/b/windowsazurestorage/)
- [<span data-ttu-id="08cd0-219">연결 문자열 구성</span><span class="sxs-lookup"><span data-stu-id="08cd0-219">Configuring Connection Strings</span></span>](https://docs.microsoft.com/azure/storage/common/storage-configure-connection-string)
- [<span data-ttu-id="08cd0-220">.NET에서 Azure 테이블 저장소 시작</span><span class="sxs-lookup"><span data-stu-id="08cd0-220">Getting Started with Azure Table Storage in .NET</span></span>](https://azure.microsoft.com/resources/samples/storage-table-dotnet-getting-started/)
