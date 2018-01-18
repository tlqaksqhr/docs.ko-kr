---
title: "LocalDB에 대한 SqlClient 지원"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cf796898-5575-46f2-ae6e-21e5aa8c4123
caps.latest.revision: "14"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: a3d643ac386aebf51673f937b3f47e73c749b78f
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2018
---
# <a name="sqlclient-support-for-localdb"></a><span data-ttu-id="3b9b7-102">LocalDB에 대한 SqlClient 지원</span><span class="sxs-lookup"><span data-stu-id="3b9b7-102">SqlClient Support for LocalDB</span></span>
<span data-ttu-id="3b9b7-103">[!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] (코드명 Denali)부터는 LocalDB라고 하는 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]의 경량 버전을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b9b7-103">Beginning in [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] code name Denali, a lightweight version of [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)], called LocalDB, will be available.</span></span> <span data-ttu-id="3b9b7-104">이 항목에서는 LocalDB 데이터베이스에 연결하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3b9b7-104">This topic discusses how to connect to a LocalDB database.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3b9b7-105">설명</span><span class="sxs-lookup"><span data-stu-id="3b9b7-105">Remarks</span></span>  
 <span data-ttu-id="3b9b7-106">LocalDB 설치 및 LocalDB 인스턴스 구성 방법을 비롯한 LocalDB에 대한 자세한 내용은 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 온라인 설명서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3b9b7-106">For more information about LocalDB, including how to install LocalDB and configure your LocalDB instance, see [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
 <span data-ttu-id="3b9b7-107">LocalDB로 할 수 있는 작업:</span><span class="sxs-lookup"><span data-stu-id="3b9b7-107">To summarize what you can do with LocalDB:</span></span>  
  
-   <span data-ttu-id="3b9b7-108">sqllocaldb.exe 또는 app.config 파일로 LocalDB 인스턴스를 만들고 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="3b9b7-108">Create and start LocalDB instances with sqllocaldb.exe or your app.config file.</span></span>  
  
-   <span data-ttu-id="3b9b7-109">sqlcmd.exe를 사용하여 LocalDB 인스턴스에서 데이터베이스를 추가하고 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="3b9b7-109">Use sqlcmd.exe to add and modify databases in a LocalDB instance.</span></span> <span data-ttu-id="3b9b7-110">예를 들어, `sqlcmd -S (localdb)\myinst`을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="3b9b7-110">For example, `sqlcmd -S (localdb)\myinst`.</span></span>  
  
-   <span data-ttu-id="3b9b7-111">`AttachDBFilename` 연결 문자열 키워드를 사용하여 데이터베이스를 LocalDB 인스턴스에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3b9b7-111">Use the `AttachDBFilename` connection string keyword to add a database to your LocalDB instance.</span></span> <span data-ttu-id="3b9b7-112">`AttachDBFilename`을 사용할 때 `Database` 연결 문자열 키워드에 데이터베이스 이름을 지정하지 않은 응용 프로그램을 닫으면 LocalDB 인스턴스에서 데이터베이스가 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b9b7-112">When using `AttachDBFilename`, if you do not specify the name of the database with the `Database` connection string keyword, the database will be removed from the LocalDB instance when the application closes.</span></span>  
  
-   <span data-ttu-id="3b9b7-113">연결 문자열에서 LocalDB 인스턴스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3b9b7-113">Specify a LocalDB instance in your connection string.</span></span> <span data-ttu-id="3b9b7-114">예를 들어 인스턴스 이름이 `myInstance`이면 연결 문자열에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b9b7-114">For example, your instance name is `myInstance`, the connection string would include:</span></span>  
  
    ```  
    server=(localdb)\\myInstance  
    ```  
  
 <span data-ttu-id="3b9b7-115">`User Instance=True` 는 LocalDB 데이터베이스에 연결할 때는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3b9b7-115">`User Instance=True` is not allowed when connecting to a LocalDB database.</span></span>  
  
 <span data-ttu-id="3b9b7-116">[Microsoft SQL Server 2012 기능 팩](http://www.microsoft.com/download/en/details.aspx?id=29065)에서 LocalDB를 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b9b7-116">You can download LocalDB from [Microsoft SQL Server 2012 Feature Pack](http://www.microsoft.com/download/en/details.aspx?id=29065).</span></span> <span data-ttu-id="3b9b7-117">sqlcmd.exe를 사용하여 LocalDB 인스턴스에서 데이터를 수정할 경우 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 2012의 sqlcmd가 필요합니다. sqlcmd는 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 2012 기능 팩에서도 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b9b7-117">If you will use sqlcmd.exe to modify data in your LocalDB instance, you will need sqlcmd from [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 2012, which you can also get from the [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 2012 Feature Pack.</span></span>  
  
## <a name="programmatically-create-a-named-instance"></a><span data-ttu-id="3b9b7-118">프로그래밍 방식으로 명명된 인스턴스 만들기</span><span class="sxs-lookup"><span data-stu-id="3b9b7-118">Programmatically Create a Named Instance</span></span>  
 <span data-ttu-id="3b9b7-119">응용 프로그램에서는 명명된 인스턴스를 만들고 다음과 같이 데이터베이스를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b9b7-119">An application can create a named instance and specify a database as follows:</span></span>  
  
-   <span data-ttu-id="3b9b7-120">예를 들어 다음과 같이 app.config 파일에 만들 LocalDB 인스턴스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3b9b7-120">Specify the LocalDB instances to create in the app.config file, as follows.</span></span>  <span data-ttu-id="3b9b7-121">인스턴스의 버전 번호는 LocalDB 설치의 버전 번호와 동일해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b9b7-121">The version number of the instance should be the same as the version number of your LocalDB installation.</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
      <configSections>  
        <section  
        name="system.data.localdb"  
        type="System.Data.LocalDBConfigurationSection,System.Data,Version=4.0.0.0,Culture=neutral,PublicKeyToken=b77a5c561934e089"/>  
      </configSections>  
      <system.data.localdb>  
        <localdbinstances>  
          <add name="myInstance" version="11.0" />  
        </localdbinstances>  
      </system.data.localdb>  
    </configuration>  
    ```  
  
-   <span data-ttu-id="3b9b7-122">`server` 연결 문자열 키워드를 사용하여 인스턴스의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3b9b7-122">Specify the name of the instance using the `server` connection string keyword.</span></span>  <span data-ttu-id="3b9b7-123">`server` 연결 문자열 키워드에 지정된 인스턴스 이름은 app.config 파일에 지정된 이름과 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b9b7-123">The instance name specified in the `server` connection string keyword must match the name specified in the app.config file.</span></span>  
  
-   <span data-ttu-id="3b9b7-124">`AttachDBFilename` 연결 문자열 키워드를 사용하여 .MDF 파일을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3b9b7-124">Use the `AttachDBFilename` connection string keyword to specify the .MDF file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b9b7-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3b9b7-125">See Also</span></span>  
 [<span data-ttu-id="3b9b7-126">SQL Server 기능 및 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="3b9b7-126">SQL Server Features and ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-features-and-adonet.md)  
 [<span data-ttu-id="3b9b7-127">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="3b9b7-127">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
