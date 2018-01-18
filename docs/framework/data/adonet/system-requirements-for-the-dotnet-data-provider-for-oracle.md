---
title: ".NET Framework Data Provider for Oracle의 시스템 요구 사항"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 054f76b9-1737-43f0-8160-84a00a387217
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 75a42962b0f4c8cd19f1cce5f9223d82e32ff369
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2018
---
# <a name="system-requirements-for-the-net-framework-data-provider-for-oracle"></a><span data-ttu-id="e0c43-102">.NET Framework Data Provider for Oracle의 시스템 요구 사항</span><span class="sxs-lookup"><span data-stu-id="e0c43-102">System Requirements for the .NET Framework Data Provider for Oracle</span></span>
<span data-ttu-id="e0c43-103">.NET Framework Data Provider for Oracle에는 MDAC(Microsoft Data Access Components) 버전 2.6 이상이 필요하며</span><span class="sxs-lookup"><span data-stu-id="e0c43-103">The .NET Framework Data Provider for Oracle requires Microsoft Data Access Components (MDAC) version 2.6 or later.</span></span> <span data-ttu-id="e0c43-104">MDAC 2.8 SP1을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e0c43-104">MDAC 2.8 SP1 is recommended.</span></span>  
  
 <span data-ttu-id="e0c43-105">또한 Oracle 8i Release 3(8.1.7) Client 이상이 설치되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0c43-105">You must also have Oracle 8i Release 3 (8.1.7) Client or later installed.</span></span>  
  
 <span data-ttu-id="e0c43-106">UTF16은 Oracle 9i에 새로 도입된 기능이므로 Oracle 9i 버전 이전의 Oracle Client 소프트웨어는 UTF16 데이터베이스에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e0c43-106">Oracle Client software prior to version Oracle 9i cannot access UTF16 databases because UTF16 is a new feature in Oracle 9i.</span></span> <span data-ttu-id="e0c43-107">이 기능을 사용하려면 클라이언트 소프트웨어를 Oracle 9i 이상으로 업그레이드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0c43-107">To use this feature, you must upgrade your client software to Oracle 9i or later.</span></span>  
  
## <a name="working-with-the-data-provider-for-oracle-and-unicode-data"></a><span data-ttu-id="e0c43-108">Data Provider for Oracle 및 유니코드 데이터 사용</span><span class="sxs-lookup"><span data-stu-id="e0c43-108">Working with the Data Provider for Oracle and Unicode Data</span></span>  
 <span data-ttu-id="e0c43-109">다음은 .NET Framework Data Provider for Oracle 및 Oracle 클라이언트 라이브러리를 사용할 때 고려해야 하는 유니코드 관련 문제 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="e0c43-109">Following is a list of Unicode-related issues that you should consider when working with the .NET Framework Data Provider for Oracle and Oracle client libraries.</span></span> <span data-ttu-id="e0c43-110">자세한 내용은 Oracle 설명서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e0c43-110">For more information, see your Oracle documentation.</span></span>  
  
### <a name="setting-the-unicode-value-in-a-connection-string-attribute"></a><span data-ttu-id="e0c43-111">연결 문자열 특성에 유니코드 값 설정</span><span class="sxs-lookup"><span data-stu-id="e0c43-111">Setting the Unicode Value in a Connection String Attribute</span></span>  
 <span data-ttu-id="e0c43-112">Oracle을 사용하는 경우 다음과 같은 연결 문자열 특성을 사용하여</span><span class="sxs-lookup"><span data-stu-id="e0c43-112">When working with Oracle, you can use the connection string attribute</span></span>  
  
```  
Unicode=True   
```  
  
 <span data-ttu-id="e0c43-113">UTF-16 모드에서 Oracle 클라이언트 라이브러리를 초기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0c43-113">to initialize the Oracle client libraries in UTF-16 mode.</span></span> <span data-ttu-id="e0c43-114">이렇게 하면 Oracle 클라이언트 라이브러리에서 멀티바이트 문자열 대신 UCS-2와 매우 유사한 UTF-16을 받아들이게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0c43-114">This causes the Oracle client libraries to accept UTF-16 (which is very similar to UCS-2) instead of multi-byte strings.</span></span> <span data-ttu-id="e0c43-115">따라서 Data Provider for Oracle에서 추가 변환 작업 없이도 언제든지 Oracle 코드 페이지를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0c43-115">This allows the Data Provider for Oracle to always work with any Oracle code page without additional translation work.</span></span> <span data-ttu-id="e0c43-116">이 구성은 Oracle 9i 클라이언트를 사용하여 대체 문자 집합 AL16UTF16으로 Oracle 9i 데이터베이스와 통신하는 경우에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0c43-116">This configuration only works if you are using Oracle 9i clients to communicate with an Oracle 9i database with the alternate character set of AL16UTF16.</span></span> <span data-ttu-id="e0c43-117">유니코드 변환에 필요한 추가 리소스가 Oracle 9i 클라이언트가 Oracle 9i 서버와 통신할 경우 **CommandText** Oracle9i 서버에서 사용 하는 값을 적절 한 멀티 바이트 문자 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="e0c43-117">When an Oracle 9i client communicates with an Oracle 9i server, additional resources are required to convert the Unicode **CommandText** values to the appropriate multi-byte character set that the Oracle9i server uses.</span></span> <span data-ttu-id="e0c43-118">하지만 연결 문자열에 `Unicode=True`를 추가하여 안전한 구성을 얻게 된다는 사실을 알면 이러한 노력을 피할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0c43-118">This can be avoided when you know that you have the safe configuration by adding `Unicode=True` to your connection string.</span></span>  
  
### <a name="mixing-versions-of-oracle-client-and-oracle-server"></a><span data-ttu-id="e0c43-119">혼합 버전의 Oracle 클라이언트 및 Oracle 서버</span><span class="sxs-lookup"><span data-stu-id="e0c43-119">Mixing Versions of Oracle Client and Oracle Server</span></span>  
 <span data-ttu-id="e0c43-120">Oracle 8i 클라이언트에 액세스할 수 없습니다 **NCHAR**, **NVARCHAR2**, 또는 **NCLOB** AL16UTF16 변수로 서버의 국가별 문자 집합이 지정 된 경우 Oracle 9i 데이터베이스의 데이터 ( 기본 설정은 Oracle 9i)입니다.</span><span class="sxs-lookup"><span data-stu-id="e0c43-120">Oracle 8i clients cannot access **NCHAR**, **NVARCHAR2**, or **NCLOB** data in Oracle 9i databases when the server's national character set is specified as AL16UTF16 (the default setting for Oracle 9i).</span></span> <span data-ttu-id="e0c43-121">Oracle 9i까지는 UTF-16 문자 집합에 대한 지원이 도입되지 않았기 때문에 Oracle 8i 클라이언트에서는 이를 읽을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e0c43-121">Because support for the UTF-16 character set was not introduced until Oracle 9i, Oracle 8i clients cannot read it.</span></span>  
  
### <a name="working-with-utf-8-data"></a><span data-ttu-id="e0c43-122">UTF-8 데이터 사용</span><span class="sxs-lookup"><span data-stu-id="e0c43-122">Working with UTF-8 Data</span></span>  
 <span data-ttu-id="e0c43-123">대체 문자 집합을 설정하려면 레지스트리 키 HKEY_LOCAL_MACHINE\SOFTWARE\ORACLE\HOMEID\NLS_LANG을 UTF8로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e0c43-123">To set the alternate character set, set the Registry Key HKEY_LOCAL_MACHINE\SOFTWARE\ORACLE\HOMEID\NLS_LANG to UTF8.</span></span> <span data-ttu-id="e0c43-124">자세한 내용은 플랫폼에서 Oracle 설치 설명을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e0c43-124">See the Oracle Installation notes on your platform for more information.</span></span> <span data-ttu-id="e0c43-125">기본 설정은 Oracle Client 소프트웨어를 설치하는 언어의 기본 문자 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="e0c43-125">The default setting is the primary character set of the language from which you are installing the Oracle Client software.</span></span> <span data-ttu-id="e0c43-126">언어를 연결하는 데이터베이스의 국가별 언어 문자 집합과 일치하도록 설정하지 않으면 매개 변수 및 열 바인딩 과정에 국가별 문자 집합이 아닌 기본 데이터베이스 문자 집합으로 데이터를 주고 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0c43-126">Not setting the language to match the national language character set of the database to which you are connecting will cause parameter and column bindings to send or receive data in your primary database character set, not the national character set.</span></span>  
  
### <a name="oraclelob-can-only-update-full-characters"></a><span data-ttu-id="e0c43-127">전체 문자만 업데이트할 수 있는 OracleLob</span><span class="sxs-lookup"><span data-stu-id="e0c43-127">OracleLob Can Only Update Full Characters.</span></span>  
 <span data-ttu-id="e0c43-128">사용 효율성을 위해는 <xref:System.Data.OracleClient.OracleLob> 개체는.NET Framework Stream 클래스에서 상속 하 고 제공 **ReadByte** 및 **WriteByte** 메서드.</span><span class="sxs-lookup"><span data-stu-id="e0c43-128">For usability reasons, the <xref:System.Data.OracleClient.OracleLob> object inherits from the .NET Framework Stream class, and provides **ReadByte** and **WriteByte** methods.</span></span> <span data-ttu-id="e0c43-129">또한 구현 메서드를 같은 **CopyTo** 및 **Erase**, 해당의 Oracle 섹션에서 작동 **LOB** 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="e0c43-129">It also implements methods, such as **CopyTo** and **Erase**, that work on sections of Oracle **LOB** objects.</span></span> <span data-ttu-id="e0c43-130">Oracle 클라이언트 소프트웨어는 다양 한 문자를 사용 하는 Api 제공 하는 반면, **LOB**s (**CLOB** 및 **NCLOB**).</span><span class="sxs-lookup"><span data-stu-id="e0c43-130">In contrast, Oracle client software provides a number of APIs to work with character **LOB**s (**CLOB** and **NCLOB**).</span></span> <span data-ttu-id="e0c43-131">그러나 이러한 API는 전체 문자에 대해서만 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="e0c43-131">However, these APIs work on full characters only.</span></span> <span data-ttu-id="e0c43-132">이러한 차이로 인해 Data Provider for Oracle에 대 한 지원을 구현 **읽기** 및 **ReadByte** 바이트 단위 방식으로 u t F-16으로 데이터에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0c43-132">Because of this difference, the Data Provider for Oracle implements support for **Read** and **ReadByte** to work with UTF-16 data in a byte-wise manner.</span></span> <span data-ttu-id="e0c43-133">그러나의 다른 메서드는 **OracleLob** 개체는 전체 문자 작업만 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0c43-133">However, the other methods of the **OracleLob** object only allow full-character operations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0c43-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e0c43-134">See Also</span></span>  
 [<span data-ttu-id="e0c43-135">Oracle 및 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="e0c43-135">Oracle and ADO.NET</span></span>](../../../../docs/framework/data/adonet/oracle-and-adonet.md)  
 [<span data-ttu-id="e0c43-136">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="e0c43-136">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
