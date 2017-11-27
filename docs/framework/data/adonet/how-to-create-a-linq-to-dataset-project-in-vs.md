---
title: "방법: Visual Studio에서 LINQ to DataSet 프로젝트 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 49ba6cb0-cdd2-4571-aeaa-25bf0f40e9b3
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 192273c6d364cebe828965ed016eea81135602f9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-linq-to-dataset-project-in-visual-studio"></a><span data-ttu-id="f23d8-102">방법: Visual Studio에서 LINQ to DataSet 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="f23d8-102">How to: Create a LINQ to DataSet Project In Visual Studio</span></span>
<span data-ttu-id="f23d8-103">다양한 형식의 [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] 프로젝트에는 가져온 네임스페이스(Visual Basic) 또는 `using` 지시문(C#) 및 참조가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f23d8-103">The different types of [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] projects require certain imported namespaces (Visual Basic) or `using` directives (C#) and references.</span></span> <span data-ttu-id="f23d8-104">적어도 System.Core.dll에 대한 참조와 `using`에 대한 <xref:System.Linq> 지시문이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f23d8-104">The minimum requirement is a reference to System.Core.dll and a `using` directive for <xref:System.Linq>.</span></span> <span data-ttu-id="f23d8-105">기본적으로 이들은 새 [!INCLUDE[csharp_orcas_long](../../../../includes/csharp-orcas-long-md.md)] 프로젝트를 만들면 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="f23d8-105">By default, these are supplied if you create a new [!INCLUDE[csharp_orcas_long](../../../../includes/csharp-orcas-long-md.md)] project.</span></span> <span data-ttu-id="f23d8-106">또한 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]에는 System.Data.dll 및 System.Data.DataSetExtensions.dll에 대한 참조와 `Imports`(Visual Basic) 또는 `using`(C#) 지시문이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f23d8-106">[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] also requires a reference to System.Data.dll and System.Data.DataSetExtensions.dll and an `Imports` (Visual Basic) or `using` (C#) directive.</span></span>  
  
 <span data-ttu-id="f23d8-107">이전 버전의 Visual Studio에서 만든 프로젝트를 업그레이드하는 경우 이러한 LINQ 관련 참조를 직접 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f23d8-107">If you are upgrading a project from an earlier version of Visual Studio, you might have to supply these LINQ-related references manually.</span></span> <span data-ttu-id="f23d8-108">또한 .NET Framework 버전 3.5를 대상으로 프로젝트를 직접 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f23d8-108">You might also have to manually set the project to target the .NET Framework version 3.5.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f23d8-109">LINQ 관련 Dll을 직접 참조 해야 명령 프롬프트에서 작성 하는 경우 `drive` **:**\Program Files\Reference Assemblies\Microsoft\Framework\v3.5 합니다.</span><span class="sxs-lookup"><span data-stu-id="f23d8-109">If you are building from a command prompt, you must manually reference the LINQ-related DLLs in `drive`**:**\Program Files\Reference Assemblies\Microsoft\Framework\v3.5.</span></span>  
  
### <a name="to-target-the-net-framework-35"></a><span data-ttu-id="f23d8-110">.NET Framework 3.5를 대상으로 지정하려면</span><span class="sxs-lookup"><span data-stu-id="f23d8-110">To target the .NET Framework 3.5</span></span>  
  
1.  <span data-ttu-id="f23d8-111">[!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)]에서 새 Visual Basic 또는 C# 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f23d8-111">In [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)], create a new Visual Basic or C# project.</span></span> <span data-ttu-id="f23d8-112">또는 Visual Studio 2005에서 만든 Visual Basic 또는 C# 프로젝트를 열고 프롬프트에 따라 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 프로젝트로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f23d8-112">Alternatively, you can open a Visual Basic or C# project that was created in Visual Studio 2005 and follow the prompts to convert it to a [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] project.</span></span>  
  
2.  <span data-ttu-id="f23d8-113">C# 프로젝트에 대 한 클릭는 **프로젝트** 메뉴를 차례로 클릭 **속성**합니다.</span><span class="sxs-lookup"><span data-stu-id="f23d8-113">For a C# project, click the **Project** menu, and then click **Properties**.</span></span>  
  
    1.  <span data-ttu-id="f23d8-114">에 **응용 프로그램** 속성 페이지에서.NET Framework 3.5를 선택는 **대상 프레임 워크** 드롭 다운 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="f23d8-114">In the **Application** property page, select .NET Framework 3.5 in the **Target Framework** drop-down list.</span></span>  
  
3.  <span data-ttu-id="f23d8-115">Visual Basic 프로젝트를 클릭 하 고 **프로젝트** 메뉴를 차례로 클릭 **속성**합니다.</span><span class="sxs-lookup"><span data-stu-id="f23d8-115">For a Visual Basic project, click the **Project** menu, and then click **Properties**.</span></span>  
  
    1.  <span data-ttu-id="f23d8-116">에 **컴파일** 속성 페이지에서 클릭 **고급 컴파일 옵션** 다음에서.NET Framework 3.5를 선택 하 고는 **대상 프레임 워크 (모든 구성)** 드롭 다운 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="f23d8-116">In the **Compile** property page, click **Advanced Compile Options** and then select .NET Framework 3.5 in the **Target Framework (all configurations)** drop-down list.</span></span>  
  
4.  <span data-ttu-id="f23d8-117">에 **프로젝트** 메뉴를 클릭 **참조 추가**, 클릭는 **.NET** 탭에서 아래쪽으로 스크롤하여 **System.Core**,를 클릭 한 다음 를클릭 **정상**합니다.</span><span class="sxs-lookup"><span data-stu-id="f23d8-117">On the **Project** menu, click **Add Reference**, click the **.NET** tab, scroll down to **System.Core**, click it, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="f23d8-118">`using`에 대한 <xref:System.Linq> 지시문 또는 가져온 네임스페이스를 소스 코드 파일이나 프로젝트에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f23d8-118">Add a `using` directive or imported namespace for <xref:System.Linq> to your source code file or project.</span></span>  
  
     <span data-ttu-id="f23d8-119">자세한 내용은 참조 [지시문을 사용 하 여](~/docs/csharp/language-reference/keywords/using-directive.md) 또는 [하는 방법: 추가 또는 제거 (Visual Basic) 가져온 네임 스페이스](/visualstudio/ide/how-to-add-or-remove-imported-namespaces-visual-basic)합니다.</span><span class="sxs-lookup"><span data-stu-id="f23d8-119">For more information, see [using Directive](~/docs/csharp/language-reference/keywords/using-directive.md) or [How to: Add or Remove Imported Namespaces (Visual Basic)](/visualstudio/ide/how-to-add-or-remove-imported-namespaces-visual-basic).</span></span>  
  
### <a name="to-enable-linq-to-dataset-functionality"></a><span data-ttu-id="f23d8-120">LINQ to DataSet 기능을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="f23d8-120">To enable LINQ to DataSet functionality</span></span>  
  
1.  <span data-ttu-id="f23d8-121">필요한 경우 이 항목의 앞에서 설명한 단계에 따라 System.Core.dll에 대한 참조와 System.Linq에 대한 `using` 지시문 또는 가져온 네임스페이스를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f23d8-121">If necessary, follow the steps earlier in this topic to add a reference to System.Core.dll and a `using` directive or imported namespace for System.Linq.</span></span>  
  
2.  <span data-ttu-id="f23d8-122">C# 또는 Visual Basic:는 **프로젝트** 메뉴를 차례로 클릭 **참조 추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="f23d8-122">In C# or Visual Basic, click the **Project** menu, and then click **Add Reference**.</span></span>  
  
3.  <span data-ttu-id="f23d8-123">에 **참조 추가** 대화 상자를 클릭는 **.NET** 탭 위에 표시 되지 않은 경우.</span><span class="sxs-lookup"><span data-stu-id="f23d8-123">In the **Add Reference** dialog box, click the **.NET** tab if it is not on top.</span></span> <span data-ttu-id="f23d8-124">으로 아래로 스크롤하여 **System.Data** 및 **System.Data.DataSetExtensions** 찾아서 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f23d8-124">Scroll down to **System.Data** and **System.Data.DataSetExtensions** and click on them.</span></span> <span data-ttu-id="f23d8-125">클릭는 **확인** 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="f23d8-125">Click the **OK** button.</span></span>  
  
4.  <span data-ttu-id="f23d8-126">`using`에 대한 <xref:System.Data> 지시문 또는 가져온 네임스페이스를 소스 코드 파일이나 프로젝트에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f23d8-126">Add a `using` directive or imported namespace for <xref:System.Data> to your source code file or project.</span></span> <span data-ttu-id="f23d8-127">자세한 내용은 참조 [지시문을 사용 하 여](~/docs/csharp/language-reference/keywords/using-directive.md) 또는 [하는 방법: 추가 또는 제거 (Visual Basic) 가져온 네임 스페이스](/visualstudio/ide/how-to-add-or-remove-imported-namespaces-visual-basic)합니다.</span><span class="sxs-lookup"><span data-stu-id="f23d8-127">For more information, see [using Directive](~/docs/csharp/language-reference/keywords/using-directive.md) or [How to: Add or Remove Imported Namespaces (Visual Basic)](/visualstudio/ide/how-to-add-or-remove-imported-namespaces-visual-basic).</span></span>  
  
5.  <span data-ttu-id="f23d8-128">LINQ to Dataset 기능을 위해 System.Data.DataSetExtensions.dll에 대한 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f23d8-128">Add a reference to System.Data.DataSetExtensions.dll for LINQ to Dataset functionality.</span></span> <span data-ttu-id="f23d8-129">System.Data.dll에 대한 참조가 아직 없으면 해당 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f23d8-129">Add a reference to System.Data.dll if it does not already exist.</span></span>  
  
6.  <span data-ttu-id="f23d8-130">데이터베이스에 연결하는 방법에 따라 선택적으로 `using` 또는 `System.Data.Common`에 대한 `System.Data.SqlClient` 지시문 또는 가져온 네임스페이스를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f23d8-130">Optionally, add a `using` directive or imported namespace for `System.Data.Common` or `System.Data.SqlClient`, depending on how you connect to the database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f23d8-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f23d8-131">See Also</span></span>  
 [<span data-ttu-id="f23d8-132">시작</span><span class="sxs-lookup"><span data-stu-id="f23d8-132">Getting Started</span></span>](../../../../docs/framework/data/adonet/getting-started-linq-to-dataset.md)  
 [<span data-ttu-id="f23d8-133">LINQ 시작</span><span class="sxs-lookup"><span data-stu-id="f23d8-133">Getting Started with LINQ</span></span>](http://msdn.microsoft.com/en-us/6cc9af04-950a-4cc3-83d4-2aeb4abe4de9)
