---
title: "방법: DBML 파일을 수정하여 사용자 지정된 코드 생성"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 50ad597a-8598-42d3-82dd-fc7d702ebc37
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: c9a2b382c84548d3226fe68531961e0f53033e7d
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-generate-customized-code-by-modifying-a-dbml-file"></a><span data-ttu-id="ca2d0-102">방법: DBML 파일을 수정하여 사용자 지정된 코드 생성</span><span class="sxs-lookup"><span data-stu-id="ca2d0-102">How to: Generate Customized Code by Modifying a DBML File</span></span>
<span data-ttu-id="ca2d0-103">생성할 수 있습니다 [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] 또는 데이터베이스 태그 언어 (.dbml) 메타 데이터 파일에서 C# 소스 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="ca2d0-103">You can generate [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] or C# source code from a database markup language (.dbml) metadata file.</span></span> <span data-ttu-id="ca2d0-104">이 방법을 사용하면 응용 프로그램 매핑 코드를 생성하기 전에 기본 .dbml 파일을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca2d0-104">This approach provides an opportunity to customize the default .dbml file before you generate the application mapping code.</span></span> <span data-ttu-id="ca2d0-105">이는 고급 기능에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="ca2d0-105">This is an advanced feature.</span></span>  
  
 <span data-ttu-id="ca2d0-106">이 프로세스의 단계는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ca2d0-106">The steps in this process are as follows:</span></span>  
  
1.  <span data-ttu-id="ca2d0-107">.dbml 파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="ca2d0-107">Generate a .dbml file.</span></span>  
  
2.  <span data-ttu-id="ca2d0-108">편집기를 사용하여 .dbml 파일을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="ca2d0-108">Use an editor to modify the .dbml file.</span></span> <span data-ttu-id="ca2d0-109">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] .dbml 파일용 스키마 정의 파일(.xsd)에 대해 .dbml 파일의 유효성을 검사해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca2d0-109">Note that the .dbml file must validate against the schema definition (.xsd) file for [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] .dbml files.</span></span> <span data-ttu-id="ca2d0-110">자세한 내용은 참조 [LINQ to SQL에서에서 코드 생성](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ca2d0-110">For more information, see [Code Generation in LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md).</span></span>  
  
3.  <span data-ttu-id="ca2d0-111">[!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] 또는 C# 소스 코드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="ca2d0-111">Generate the [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] or C# source code.</span></span>  
  
 <span data-ttu-id="ca2d0-112">다음 예제에서는 SQLMetal 명령줄 도구를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ca2d0-112">The following examples use the SQLMetal command-line tool.</span></span> <span data-ttu-id="ca2d0-113">자세한 내용은 [SqlMetal.exe(코드 생성 도구)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ca2d0-113">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ca2d0-114">예</span><span class="sxs-lookup"><span data-stu-id="ca2d0-114">Example</span></span>  
 <span data-ttu-id="ca2d0-115">다음 코드에서는 Northwind 샘플 데이터베이스에서 .dbml 파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="ca2d0-115">The following code generates a .dbml file from the Northwind sample database.</span></span> <span data-ttu-id="ca2d0-116">데이터베이스 메타데이터의 소스로 데이터베이스의 이름이나 .mdf 파일의 이름을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca2d0-116">As source for the database metadata, you can use either the name of the database or the name of the .mdf file.</span></span>  
  
```  
sqlmetal /server:myserver /database:northwind /dbml:mymeta.dbml  
sqlmetal /dbml:mymeta.dbml mydbfile.mdf  
```  
  
## <a name="example"></a><span data-ttu-id="ca2d0-117">예</span><span class="sxs-lookup"><span data-stu-id="ca2d0-117">Example</span></span>  
 <span data-ttu-id="ca2d0-118">다음 코드에서는 .dbml 파일에서 [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] 또는 C# 소스 코드 파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="ca2d0-118">The following code generates [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] or C# source code file from a .dbml file.</span></span>  
  
```  
sqlmetal /namespace:nwind /code:nwind.vb /language:vb DBMLFile.dbml  
sqlmetal /namespace:nwind /code:nwind.cs /language:csharp DBMLFile.dbml  
```  
  
## <a name="see-also"></a><span data-ttu-id="ca2d0-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ca2d0-119">See Also</span></span>  
 [<span data-ttu-id="ca2d0-120">LINQ to SQL에서 코드 생성</span><span class="sxs-lookup"><span data-stu-id="ca2d0-120">Code Generation in LINQ to SQL</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md)  
 [<span data-ttu-id="ca2d0-121">SqlMetal.exe(코드 생성 도구)</span><span class="sxs-lookup"><span data-stu-id="ca2d0-121">SqlMetal.exe (Code Generation Tool)</span></span>](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md)  
 [<span data-ttu-id="ca2d0-122">개체 모델 만들기</span><span class="sxs-lookup"><span data-stu-id="ca2d0-122">Creating the Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)
