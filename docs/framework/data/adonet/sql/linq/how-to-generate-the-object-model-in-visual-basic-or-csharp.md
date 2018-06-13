---
title: '방법: Visual Basic 또는 C#에서 개체 모델 생성'
ms.date: 03/30/2017
ms.assetid: a0c73b33-5650-420c-b9dc-f49310c201ee
ms.openlocfilehash: ce7f1f30a606c0d0c81a1afbfc2552ece4fc1029
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33360395"
---
# <a name="how-to-generate-the-object-model-in-visual-basic-or-c"></a><span data-ttu-id="9e18f-102">방법: Visual Basic 또는 C#에서 개체 모델 생성</span><span class="sxs-lookup"><span data-stu-id="9e18f-102">How to: Generate the Object Model in Visual Basic or C#</span></span> #
<span data-ttu-id="9e18f-103">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서 사용자 프로그래밍 언어의 개체 모델은 관계형 데이터베이스에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e18f-103">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], an object model in your own programming language is mapped to a relational database.</span></span> <span data-ttu-id="9e18f-104">두 도구는 자동으로 기존 데이터베이스의 메타 데이터에서 Visual Basic 또는 C# 모델을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e18f-104">Two tools are available for automatically generating a Visual Basic or C# model from the metadata of an existing database.</span></span>  
  
-   <span data-ttu-id="9e18f-105">Visual Studio를 사용 하는 경우 사용할 수 있습니다는 [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] 를 개체 모델을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e18f-105">If you are using Visual Studio, you can use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to generate an object model.</span></span> <span data-ttu-id="9e18f-106">[!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)]에서는 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 개체 모델을 생성하는 데 도움이 되는 다양한 사용자 인터페이스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9e18f-106">The [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)] provides a rich user interface to help you generate a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] object model.</span></span> <span data-ttu-id="9e18f-107">자세한 내용은 참조 하십시오 [Linq to SQL 도구 Visual Studio에서](https://docs.microsoft.com/en-us/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2)합니다.</span><span class="sxs-lookup"><span data-stu-id="9e18f-107">For more information see, [Linq to SQL Tools in Visual Studio](https://docs.microsoft.com/en-us/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2).</span></span>
  
-   <span data-ttu-id="9e18f-108">SQLMetal 명령줄 도구.</span><span class="sxs-lookup"><span data-stu-id="9e18f-108">The SQLMetal command-line tool.</span></span> <span data-ttu-id="9e18f-109">자세한 내용은 [SqlMetal.exe(코드 생성 도구)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9e18f-109">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9e18f-110">기존 데이터베이스가 없는 경우 개체 모델에서 데이터베이스를 만들려면 코드 편집기와 <xref:System.Data.Linq.DataContext.CreateDatabase%2A>를 사용하여 개체 모델을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e18f-110">If you do not have an existing database and want to create one from an object model, you can create your object model by using your code editor and <xref:System.Data.Linq.DataContext.CreateDatabase%2A>.</span></span> <span data-ttu-id="9e18f-111">자세한 내용은 참조 [하는 방법: 동적으로 데이터베이스를 만들](../../../../../../docs/framework/data/adonet/sql/linq/how-to-dynamically-create-a-database.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9e18f-111">For more information, see [How to: Dynamically Create a Database](../../../../../../docs/framework/data/adonet/sql/linq/how-to-dynamically-create-a-database.md).</span></span>  
  
 <span data-ttu-id="9e18f-112">에 대 한 설명서는 [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)] 를 사용 하 여 Visual Basic 또는 C# 개체 모델을 생성 하는 방법의 예제를 제공는 [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="9e18f-112">Documentation for the [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)] provides examples of how to generate a Visual Basic or C# object model by using the [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)].</span></span> <span data-ttu-id="9e18f-113">다음 정보에서는 SQLMetal 명령줄 도구를 사용하는 방법에 대한 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9e18f-113">The following information provide examples of how to use the SQLMetal command-line tool.</span></span> <span data-ttu-id="9e18f-114">자세한 내용은 [SqlMetal.exe(코드 생성 도구)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9e18f-114">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9e18f-115">예제</span><span class="sxs-lookup"><span data-stu-id="9e18f-115">Example</span></span>  
 <span data-ttu-id="9e18f-116">다음 예제에서에 표시 된 SQLMetal 명령줄에서는 Northwind 샘플 데이터베이스의 특성 기반 개체 모델을 Visual Basic 코드를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e18f-116">The SQLMetal command line shown in the following example produces Visual Basic code as the attribute-based object model of the Northwind sample database.</span></span> <span data-ttu-id="9e18f-117">또한 저장 프로시저와 함수가 렌더링됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e18f-117">Stored procedures and functions are also rendered.</span></span>  
  
```  
sqlmetal /code:northwind.vb /language:vb "c:\northwnd.mdf" /sprocs /functions  
```  
  
## <a name="example"></a><span data-ttu-id="9e18f-118">예제</span><span class="sxs-lookup"><span data-stu-id="9e18f-118">Example</span></span>  
 <span data-ttu-id="9e18f-119">다음 예제의 SQLMetal 명령줄에서는 Northwind 샘플 데이터베이스의 특성 기반 개체 모델과 같은 C# 코드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="9e18f-119">The SQLMetal command line shown in the following example produces C# code as the attribute-based object model of the Northwind sample database.</span></span> <span data-ttu-id="9e18f-120">또한 저장 프로시저와 함수가 렌더링되며 테이블 이름은 자동으로 복수화됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e18f-120">Stored procedures and functions are also rendered, and table names are automatically pluralized.</span></span>  
  
```  
sqlmetal /code:northwind.cs /language:csharp "c:\northwnd.mdf" /sprocs /functions /pluralize  
```  
  
## <a name="see-also"></a><span data-ttu-id="9e18f-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9e18f-121">See Also</span></span>  
 [<span data-ttu-id="9e18f-122">프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="9e18f-122">Programming Guide</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/programming-guide.md)  
 [<span data-ttu-id="9e18f-123">LINQ to SQL 개체 모델</span><span class="sxs-lookup"><span data-stu-id="9e18f-123">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)  
 [<span data-ttu-id="9e18f-124">연습으로 학습</span><span class="sxs-lookup"><span data-stu-id="9e18f-124">Learning by Walkthroughs</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md)  
 [<span data-ttu-id="9e18f-125">방법: 코드 편집기를 사용하여 엔터티 클래스 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="9e18f-125">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)  
 [<span data-ttu-id="9e18f-126">특성 기반 매핑</span><span class="sxs-lookup"><span data-stu-id="9e18f-126">Attribute-Based Mapping</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md)  
 [<span data-ttu-id="9e18f-127">SqlMetal.exe(코드 생성 도구)</span><span class="sxs-lookup"><span data-stu-id="9e18f-127">SqlMetal.exe (Code Generation Tool)</span></span>](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md)  
 [<span data-ttu-id="9e18f-128">외부 매핑</span><span class="sxs-lookup"><span data-stu-id="9e18f-128">External Mapping</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md)  
 [<span data-ttu-id="9e18f-129">샘플 데이터베이스 다운로드</span><span class="sxs-lookup"><span data-stu-id="9e18f-129">Downloading Sample Databases</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)  
 [<span data-ttu-id="9e18f-130">개체 모델 만들기</span><span class="sxs-lookup"><span data-stu-id="9e18f-130">Creating the Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)
