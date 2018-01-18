---
title: "방법: Visual Basic 또는 C#에서 개체 모델 생성"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a0c73b33-5650-420c-b9dc-f49310c201ee
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: ec28b175dddb98eb035061363dd6581e796280b3
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-generate-the-object-model-in-visual-basic-or-c"></a><span data-ttu-id="1b84d-102">방법: Visual Basic 또는 C#에서 개체 모델 생성</span><span class="sxs-lookup"><span data-stu-id="1b84d-102">How to: Generate the Object Model in Visual Basic or C#</span></span> #
<span data-ttu-id="1b84d-103">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서 사용자 프로그래밍 언어의 개체 모델은 관계형 데이터베이스에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="1b84d-103">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], an object model in your own programming language is mapped to a relational database.</span></span> <span data-ttu-id="1b84d-104">기존 데이터베이스의 메타데이터에서 [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] 또는 C# 모델을 자동으로 생성할 수 있는 두 개의 도구를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1b84d-104">Two tools are available for automatically generating a [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] or C# model from the metadata of an existing database.</span></span>  
  
-   <span data-ttu-id="1b84d-105">[!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)]를 사용하는 경우 [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)]를 통해 개체 모델을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b84d-105">If you are using [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)], you can use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to generate an object model.</span></span> <span data-ttu-id="1b84d-106">[!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)]에서는 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 개체 모델을 생성하는 데 도움이 되는 다양한 사용자 인터페이스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1b84d-106">The [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)] provides a rich user interface to help you generate a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] object model.</span></span> <span data-ttu-id="1b84d-107">자세한 내용은 참조 하십시오 [Linq to SQL 도구 Visual Studio에서](https://docs.microsoft.com/en-us/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2)합니다.</span><span class="sxs-lookup"><span data-stu-id="1b84d-107">For more information see, [Linq to SQL Tools in Visual Studio](https://docs.microsoft.com/en-us/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2).</span></span>
  
-   <span data-ttu-id="1b84d-108">SQLMetal 명령줄 도구.</span><span class="sxs-lookup"><span data-stu-id="1b84d-108">The SQLMetal command-line tool.</span></span> <span data-ttu-id="1b84d-109">자세한 내용은 [SqlMetal.exe(코드 생성 도구)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1b84d-109">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1b84d-110">기존 데이터베이스가 없는 경우 개체 모델에서 데이터베이스를 만들려면 코드 편집기와 <xref:System.Data.Linq.DataContext.CreateDatabase%2A>를 사용하여 개체 모델을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b84d-110">If you do not have an existing database and want to create one from an object model, you can create your object model by using your code editor and <xref:System.Data.Linq.DataContext.CreateDatabase%2A>.</span></span> <span data-ttu-id="1b84d-111">자세한 내용은 참조 [하는 방법: 동적으로 데이터베이스를 만들](../../../../../../docs/framework/data/adonet/sql/linq/how-to-dynamically-create-a-database.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1b84d-111">For more information, see [How to: Dynamically Create a Database](../../../../../../docs/framework/data/adonet/sql/linq/how-to-dynamically-create-a-database.md).</span></span>  
  
 <span data-ttu-id="1b84d-112">[!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)] 설명서에서는 [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]를 사용하여 [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)] 또는 C# 개체 모델을 생성하는 방법에 대한 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1b84d-112">Documentation for the [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)] provides examples of how to generate a [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] or C# object model by using the [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)].</span></span> <span data-ttu-id="1b84d-113">다음 정보에서는 SQLMetal 명령줄 도구를 사용하는 방법에 대한 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1b84d-113">The following information provide examples of how to use the SQLMetal command-line tool.</span></span> <span data-ttu-id="1b84d-114">자세한 내용은 [SqlMetal.exe(코드 생성 도구)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1b84d-114">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1b84d-115">예</span><span class="sxs-lookup"><span data-stu-id="1b84d-115">Example</span></span>  
 <span data-ttu-id="1b84d-116">다음 예제의 SQLMetal 명령줄에서는 Northwind 샘플 데이터베이스의 특성 기반 개체 모델과 같은 [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] 코드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="1b84d-116">The SQLMetal command line shown in the following example produces [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] code as the attribute-based object model of the Northwind sample database.</span></span> <span data-ttu-id="1b84d-117">또한 저장 프로시저와 함수가 렌더링됩니다.</span><span class="sxs-lookup"><span data-stu-id="1b84d-117">Stored procedures and functions are also rendered.</span></span>  
  
```  
sqlmetal /code:northwind.vb /language:vb "c:\northwnd.mdf" /sprocs /functions  
```  
  
## <a name="example"></a><span data-ttu-id="1b84d-118">예</span><span class="sxs-lookup"><span data-stu-id="1b84d-118">Example</span></span>  
 <span data-ttu-id="1b84d-119">다음 예제의 SQLMetal 명령줄에서는 Northwind 샘플 데이터베이스의 특성 기반 개체 모델과 같은 C# 코드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="1b84d-119">The SQLMetal command line shown in the following example produces C# code as the attribute-based object model of the Northwind sample database.</span></span> <span data-ttu-id="1b84d-120">또한 저장 프로시저와 함수가 렌더링되며 테이블 이름은 자동으로 복수화됩니다.</span><span class="sxs-lookup"><span data-stu-id="1b84d-120">Stored procedures and functions are also rendered, and table names are automatically pluralized.</span></span>  
  
```  
sqlmetal /code:northwind.cs /language:csharp "c:\northwnd.mdf" /sprocs /functions /pluralize  
```  
  
## <a name="see-also"></a><span data-ttu-id="1b84d-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1b84d-121">See Also</span></span>  
 [<span data-ttu-id="1b84d-122">프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="1b84d-122">Programming Guide</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/programming-guide.md)  
 [<span data-ttu-id="1b84d-123">LINQ to SQL 개체 모델</span><span class="sxs-lookup"><span data-stu-id="1b84d-123">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)  
 [<span data-ttu-id="1b84d-124">연습으로 학습</span><span class="sxs-lookup"><span data-stu-id="1b84d-124">Learning by Walkthroughs</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md)  
 [<span data-ttu-id="1b84d-125">방법: 코드 편집기를 사용하여 엔터티 클래스 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="1b84d-125">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)  
 [<span data-ttu-id="1b84d-126">특성 기반 매핑</span><span class="sxs-lookup"><span data-stu-id="1b84d-126">Attribute-Based Mapping</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md)  
 [<span data-ttu-id="1b84d-127">SqlMetal.exe(코드 생성 도구)</span><span class="sxs-lookup"><span data-stu-id="1b84d-127">SqlMetal.exe (Code Generation Tool)</span></span>](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md)  
 [<span data-ttu-id="1b84d-128">외부 매핑</span><span class="sxs-lookup"><span data-stu-id="1b84d-128">External Mapping</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md)  
 [<span data-ttu-id="1b84d-129">샘플 데이터베이스 다운로드</span><span class="sxs-lookup"><span data-stu-id="1b84d-129">Downloading Sample Databases</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)  
 [<span data-ttu-id="1b84d-130">개체 모델 만들기</span><span class="sxs-lookup"><span data-stu-id="1b84d-130">Creating the Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)
