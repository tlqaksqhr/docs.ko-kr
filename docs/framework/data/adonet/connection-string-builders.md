---
title: "연결 문자열 작성기"
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
ms.assetid: 8434b608-c4d3-43d3-8ae3-6d8c6b726759
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: beec0aba34bc38ba310aa87dadeeaa4b41c82649
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2018
---
# <a name="connection-string-builders"></a><span data-ttu-id="5f4f7-102">연결 문자열 작성기</span><span class="sxs-lookup"><span data-stu-id="5f4f7-102">Connection String Builders</span></span>
<span data-ttu-id="5f4f7-103">이전 버전의 [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)]컴파일 시간 실행 시 잘못 된 키워드가 생성 되도록 연결 된 문자열 값이 발생 하지 않은 있는 연결 문자열의 검사는 <xref:System.ArgumentException>합니다.</span><span class="sxs-lookup"><span data-stu-id="5f4f7-103">In earlier versions of [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)], compile-time checking of connection strings with concatenated string values did not occur, so that at run time, an incorrect keyword generated an <xref:System.ArgumentException>.</span></span> <span data-ttu-id="5f4f7-104">[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 데이터 공급자는 각각 다른 연결 문자열 키워드 구문을 지원하므로 수동으로 유효한 연결 문자열을 구성하는 것이 어렵습니다.</span><span class="sxs-lookup"><span data-stu-id="5f4f7-104">Each of the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] data providers supported different syntax for connection string keywords, which made constructing valid connection strings difficult if done manually.</span></span> <span data-ttu-id="5f4f7-105">이 문제를 해결하기 위해 [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] 2.0에는 각 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 데이터 공급자에 사용할 수 있는 새로운 연결 문자열 작성기가 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5f4f7-105">To address this problem, [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] 2.0 introduced new connection string builders for each [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] data provider.</span></span> <span data-ttu-id="5f4f7-106">각 데이터 공급자에는 <xref:System.Data.Common.DbConnectionStringBuilder>에서 상속되는 강력한 형식의 연결 문자열 작성기 클래스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f4f7-106">Each data provider includes a strongly typed connection string builder class that inherits from <xref:System.Data.Common.DbConnectionStringBuilder>.</span></span> <span data-ttu-id="5f4f7-107">다음 표에는 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 데이터 공급자와 그와 관련된 연결 문자열 작성기 클래스가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f4f7-107">The following table lists the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] data providers and their associated connection string builder classes.</span></span>  
  
|<span data-ttu-id="5f4f7-108">공급자</span><span class="sxs-lookup"><span data-stu-id="5f4f7-108">Provider</span></span>|<span data-ttu-id="5f4f7-109">ConnectionStringBuilder 클래스</span><span class="sxs-lookup"><span data-stu-id="5f4f7-109">ConnectionStringBuilder class</span></span>|  
|--------------|-----------------------------------|  
|<xref:System.Data.SqlClient>|<xref:System.Data.SqlClient.SqlConnectionStringBuilder?displayProperty=nameWithType>|  
|<xref:System.Data.OleDb>|<xref:System.Data.OleDb.OleDbConnectionStringBuilder?displayProperty=nameWithType>|  
|<xref:System.Data.Odbc>|<xref:System.Data.Odbc.OdbcConnectionStringBuilder?displayProperty=nameWithType>|  
|<xref:System.Data.OracleClient>|<xref:System.Data.OracleClient.OracleConnectionStringBuilder?displayProperty=nameWithType>|  
  
## <a name="connection-string-injection-attacks"></a><span data-ttu-id="5f4f7-110">연결 문자열 삽입 공격</span><span class="sxs-lookup"><span data-stu-id="5f4f7-110">Connection String Injection Attacks</span></span>  
 <span data-ttu-id="5f4f7-111">연결 문자열 삽입 공격은 사용자 입력에 대해 동적 문자열 연결을 사용하여 연결 문자열을 작성할 때 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f4f7-111">A connection string injection attack can occur when dynamic string concatenation is used to build connection strings that are based on user input.</span></span> <span data-ttu-id="5f4f7-112">문자열의 유효성이 확인되지 않고 악의적인 텍스트 또는 문자를 이스케이프할 수 없는 경우 공격자가 서버에서 중요한 데이터 또는 기타 리소스에 액세스할 가능성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f4f7-112">If the string is not validated and malicious text or characters not escaped, an attacker can potentially access sensitive data or other resources on the server.</span></span> <span data-ttu-id="5f4f7-113">예를 들어 공격자가 세미콜론을 입력한 다음 값을 추가하여 공격을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f4f7-113">For example, an attacker could mount an attack by supplying a semicolon and appending an additional value.</span></span> <span data-ttu-id="5f4f7-114">연결 문자열은 "최신 항목 사용" 알고리즘을 사용하여 구문 분석되므로 악의적인 입력이 올바른 값을 대체할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f4f7-114">The connection string is parsed by using a "last one wins" algorithm, and the hostile input is substituted for a legitimate value.</span></span>  
  
 <span data-ttu-id="5f4f7-115">연결 문자열 작성기 클래스는 모호한 작업을 제거하고 구문 오류 및 보안 취약점으로부터 보호하도록 디자인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5f4f7-115">The connection string builder classes are designed to eliminate guesswork and protect against syntax errors and security vulnerabilities.</span></span> <span data-ttu-id="5f4f7-116">즉, 각 데이터 공급자에서 허용하는 알려진 키/값 쌍에 해당하는 메서드와 속성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5f4f7-116">They provide methods and properties corresponding to the known key/value pairs permitted by each data provider.</span></span> <span data-ttu-id="5f4f7-117">각 클래스는 고정된 동의어 컬렉션을 유지하며 동의어를 그에 해당하는 잘 알려진 키 이름으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f4f7-117">Each class maintains a fixed collection of synonyms and can translate from a synonym to the corresponding well-known key name.</span></span> <span data-ttu-id="5f4f7-118">또한, 유효한 키/값 쌍에 대한 검사를 수행하며 유효하지 않은 쌍이 있는 경우 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="5f4f7-118">Checks are performed for valid key/value pairs and an invalid pair throws an exception.</span></span> <span data-ttu-id="5f4f7-119">뿐만 아니라 삽입된 값을 안전한 방식으로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="5f4f7-119">In addition, injected values are handled in a safe manner.</span></span>  
  
 <span data-ttu-id="5f4f7-120">다음 예제에서는 <xref:System.Data.SqlClient.SqlConnectionStringBuilder>에서 `Initial Catalog` 설정에 삽입된 추가 값을 처리하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5f4f7-120">The following example demonstrates how the <xref:System.Data.SqlClient.SqlConnectionStringBuilder> handles an inserted extra value for the `Initial Catalog` setting.</span></span>  
  
```vb  
Dim builder As New System.Data.SqlClient.SqlConnectionStringBuilder  
builder("Data Source") = "(local)"  
builder("Integrated Security") = True  
builder("Initial Catalog") = "AdventureWorks;NewValue=Bad"  
Console.WriteLine(builder.ConnectionString)  
```  
  
```csharp  
System.Data.SqlClient.SqlConnectionStringBuilder builder =  
  new System.Data.SqlClient.SqlConnectionStringBuilder();  
builder["Data Source"] = "(local)";  
builder["integrated Security"] = true;  
builder["Initial Catalog"] = "AdventureWorks;NewValue=Bad";  
Console.WriteLine(builder.ConnectionString);  
```  
  
 <span data-ttu-id="5f4f7-121">출력을 통해 <xref:System.Data.SqlClient.SqlConnectionStringBuilder>에서 추가 값을 연결 문자열에 새로운 키/값 쌍으로 추가하는 대신 큰따옴표로 묶어 올바르게 이스케이프 처리했음을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f4f7-121">The output shows that the <xref:System.Data.SqlClient.SqlConnectionStringBuilder> handled this correctly by escaping the extra value in double quotation marks instead of appending it to the connection string as a new key/value pair.</span></span>  
  
```  
data source=(local);Integrated Security=True;  
initial catalog="AdventureWorks;NewValue=Bad"  
```  
  
## <a name="building-connection-strings-from-configuration-files"></a><span data-ttu-id="5f4f7-122">구성 파일에서 연결 문자열 작성</span><span class="sxs-lookup"><span data-stu-id="5f4f7-122">Building Connection Strings from Configuration Files</span></span>  
 <span data-ttu-id="5f4f7-123">연결 문자열의 특정 요소가 이미 알려져 있는 경우 해당 요소를 구성 파일에 저장하고 런타임에 검색하여 완전한 연결 문자열을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f4f7-123">If certain elements of a connection string are known beforehand, they can be stored in a configuration file and retrieved at run time to construct a complete connection string.</span></span> <span data-ttu-id="5f4f7-124">예를 들어 데이터베이스 이름은 미리 알고 있는 경우가 많지만 서버 이름은 그렇지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5f4f7-124">For example, the name of the database might be known in advance, but not the name of the server.</span></span> <span data-ttu-id="5f4f7-125">또는 연결 문자열에 다른 값을 삽입할 수 없도록 런타임에 사용자가 이름과 암호를 입력하도록 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f4f7-125">Or you might want a user to supply a name and password at run time without being able to inject other values into the connection string.</span></span>  
  
 <span data-ttu-id="5f4f7-126">연결 문자열 작성기의 오버로드된 생성자 중 하나는 <xref:System.String>을 인수로 사용하므로 작성기를 사용하면 부분 연결 문자열을 제공하여 이러한 사용자 입력을 통해 연결 문자열을 완성하는 것이 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="5f4f7-126">One of the overloaded constructors for a connection string builder takes a <xref:System.String> as an argument, which enables you to supply a partial connection string that can then be completed from user input.</span></span> <span data-ttu-id="5f4f7-127">이 부분 연결 문자열을 구성 파일에 저장한 후 런타임에 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f4f7-127">The partial connection string can be stored in a configuration file and retrieved at run time.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5f4f7-128"><xref:System.Configuration> 네임스페이스를 사용하면 <xref:System.Web.Configuration.WebConfigurationManager>(웹 응용 프로그램의 경우) 및 <xref:System.Configuration.ConfigurationManager>(Windows 응용 프로그램의 경우)를 통해 구성 파일에 프로그래밍 방식으로 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f4f7-128">The <xref:System.Configuration> namespace allows programmatic access to configuration files that use the <xref:System.Web.Configuration.WebConfigurationManager> for Web applications and the <xref:System.Configuration.ConfigurationManager> for Windows applications.</span></span> <span data-ttu-id="5f4f7-129">연결 문자열 및 구성 파일 사용에 대 한 자세한 내용은 참조 [연결 문자열 및 구성 파일](../../../../docs/framework/data/adonet/connection-strings-and-configuration-files.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5f4f7-129">For more information about working with connection strings and configuration files, see [Connection Strings and Configuration Files](../../../../docs/framework/data/adonet/connection-strings-and-configuration-files.md).</span></span>  
  
### <a name="example"></a><span data-ttu-id="5f4f7-130">예</span><span class="sxs-lookup"><span data-stu-id="5f4f7-130">Example</span></span>  
 <span data-ttu-id="5f4f7-131">이 예제에서는 구성 파일에서 부분 연결 문자열을 검색한 후 <xref:System.Data.SqlClient.SqlConnectionStringBuilder.DataSource%2A>의 <xref:System.Data.SqlClient.SqlConnectionStringBuilder.UserID%2A>, <xref:System.Data.SqlClient.SqlConnectionStringBuilder.Password%2A> 및 <xref:System.Data.SqlClient.SqlConnectionStringBuilder> 속성을 설정하여 완성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5f4f7-131">This example demonstrates retrieving a partial connection string from a configuration file and completing it by setting the <xref:System.Data.SqlClient.SqlConnectionStringBuilder.DataSource%2A>, <xref:System.Data.SqlClient.SqlConnectionStringBuilder.UserID%2A>, and <xref:System.Data.SqlClient.SqlConnectionStringBuilder.Password%2A> properties of the <xref:System.Data.SqlClient.SqlConnectionStringBuilder>.</span></span> <span data-ttu-id="5f4f7-132">구성 파일은 다음과 같이 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f4f7-132">The configuration file is defined as follows.</span></span>  
  
```xml  
<connectionStrings>  
  <clear/>  
  <add name="partialConnectString"   
    connectionString="Initial Catalog=Northwind;"  
    providerName="System.Data.SqlClient" />  
</connectionStrings>  
```  
  
> [!NOTE]
>  <span data-ttu-id="5f4f7-133">코드를 실행하려면 프로젝트에서 `System.Configuration.dll`에 대한 참조를 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f4f7-133">You must set a reference to the `System.Configuration.dll` in your project for the code to run.</span></span>  
  
 [!code-csharp[DataWorks SqlConnectionStringBuilder.UserNamePwd#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlConnectionStringBuilder.UserNamePwd/CS/source.cs#1)]
 [!code-vb[DataWorks SqlConnectionStringBuilder.UserNamePwd#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlConnectionStringBuilder.UserNamePwd/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="5f4f7-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5f4f7-134">See Also</span></span>  
 [<span data-ttu-id="5f4f7-135">연결 문자열</span><span class="sxs-lookup"><span data-stu-id="5f4f7-135">Connection Strings</span></span>](../../../../docs/framework/data/adonet/connection-strings.md)  
 [<span data-ttu-id="5f4f7-136">개인 정보 및 데이터 보안</span><span class="sxs-lookup"><span data-stu-id="5f4f7-136">Privacy and Data Security</span></span>](../../../../docs/framework/data/adonet/privacy-and-data-security.md)  
 [<span data-ttu-id="5f4f7-137">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="5f4f7-137">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
