---
title: "방법: DBML 및 외부 매핑 파일 유효성 검사"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d9ea37f5-0a9e-4401-8fc3-1e6fd44c49f9
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 7724586c33c19654c3657a5a4604a3c74f2c8756
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-validate-dbml-and-external-mapping-files"></a><span data-ttu-id="1a239-102">방법: DBML 및 외부 매핑 파일 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="1a239-102">How to: Validate DBML and External Mapping Files</span></span>
<span data-ttu-id="1a239-103">수정한 외부 매핑 파일 및 .dbml 파일은 해당 스키마 정의에 대해 유효성이 검사되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a239-103">External mapping files and .dbml files that you modify must be validated against their respective schema definitions.</span></span> <span data-ttu-id="1a239-104">이 항목에서는 유효성 검사 프로세스를 구현하는 단계를 [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] 사용자에게 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1a239-104">This topic provides [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] users with the steps to implement the validation process.</span></span>  
  
 [!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]  
  
### <a name="to-validate-a-dbml-or-xml-file"></a><span data-ttu-id="1a239-105">.dbml 또는 XML 파일의 유효성을 검사하려면</span><span class="sxs-lookup"><span data-stu-id="1a239-105">To validate a .dbml or XML file</span></span>  
  
1.  <span data-ttu-id="1a239-106">Visual Studio에서 **파일** 메뉴에서 **열려**, 클릭 하 고 **파일**합니다.</span><span class="sxs-lookup"><span data-stu-id="1a239-106">On the Visual Studio **File** menu, point to **Open**, and then click **File**.</span></span>  
  
2.  <span data-ttu-id="1a239-107">에 **열려 있는 파일** 대화 상자에서.dbml 또는 XML 매핑 파일 유효성을 검사할을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a239-107">In the **Open File** dialog box, click the .dbml or XML mapping file that you want to validate.</span></span>  
  
     <span data-ttu-id="1a239-108">파일이 열립니다는 **XML 편집기**합니다.</span><span class="sxs-lookup"><span data-stu-id="1a239-108">The file opens in the **XML Editor**.</span></span>  
  
3.  <span data-ttu-id="1a239-109">창에서 마우스 오른쪽 단추로 누른 **속성**합니다.</span><span class="sxs-lookup"><span data-stu-id="1a239-109">Right-click the window, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="1a239-110">에 **속성** 창에 대 한 줄임표를 클릭 하는 **스키마** 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="1a239-110">In the **Properties** window, click the ellipsis for the **Schemas** property.</span></span>  
  
     <span data-ttu-id="1a239-111">**XML 스키마** 대화 상자가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="1a239-111">The **XML Schemas** dialog box opens.</span></span>  
  
5.  <span data-ttu-id="1a239-112">원하는 목적에 맞는 적절한 스키마 정의를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1a239-112">Note the appropriate schema definition for your purpose.</span></span>  
  
    -   <span data-ttu-id="1a239-113">DbmlSchema.xsd는 .dbml 파일의 유효성 검사를 위한 스키마 정의입니다.</span><span class="sxs-lookup"><span data-stu-id="1a239-113">DbmlSchema.xsd is the schema definition for validating a .dbml file.</span></span> <span data-ttu-id="1a239-114">자세한 내용은 참조 [LINQ to SQL에서에서 코드 생성](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1a239-114">For more information, see [Code Generation in LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md).</span></span>  
  
    -   <span data-ttu-id="1a239-115">LinqToSqlMapping.xsd는 외부 XML 매핑 파일의 유효성 검사를 위한 스키마 정의입니다.</span><span class="sxs-lookup"><span data-stu-id="1a239-115">LinqToSqlMapping.xsd is the schema definition for validating an external XML mapping file.</span></span> <span data-ttu-id="1a239-116">자세한 내용은 참조 [외부 매핑](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1a239-116">For more information, see [External Mapping](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md).</span></span>  
  
6.  <span data-ttu-id="1a239-117">에 **사용** 드롭다운 상자를 열려면 클릭 한 다음를 클릭 하 여 원하는 스키마 정의 행의 열 **이 스키마를 사용 하 여**합니다.</span><span class="sxs-lookup"><span data-stu-id="1a239-117">In the **Use** column of the desired schema definition row, click to open the drop-down box, and then click **Use this schema**.</span></span>  
  
     <span data-ttu-id="1a239-118">이제 스키마 정의 파일이 DBML 또는 XML 매핑 파일과 연관됩니다.</span><span class="sxs-lookup"><span data-stu-id="1a239-118">The schema definition file is now associated with your DBML or XML mapping file.</span></span>  
  
     <span data-ttu-id="1a239-119">다른 스키마 정의가 선택되지 않았는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1a239-119">Make sure no other schema definitions are selected.</span></span>  
  
7.  <span data-ttu-id="1a239-120">에 **보기** 메뉴를 클릭 하 여 **오류 목록**합니다.</span><span class="sxs-lookup"><span data-stu-id="1a239-120">On the **View** menu, click **Error List**.</span></span>  
  
     <span data-ttu-id="1a239-121">오류, 경고 또는 메시지가 생성되었는지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1a239-121">Determine whether errors, warnings, or messages have been generated.</span></span> <span data-ttu-id="1a239-122">생성된 것이 없는 경우 스키마 정의에 대해 XML 파일이 유효합니다.</span><span class="sxs-lookup"><span data-stu-id="1a239-122">If not, the XML file is valid against the schema definition.</span></span>  
  
## <a name="alternate-method-for-supplying-schema-definition"></a><span data-ttu-id="1a239-123">스키마 정의 제공을 위한 대체 방법</span><span class="sxs-lookup"><span data-stu-id="1a239-123">Alternate Method for Supplying Schema Definition</span></span>  
 <span data-ttu-id="1a239-124">어떤 이유로 적절 한.xsd 파일에 표시 되지 않으면는 **XML 스키마** 대화 상자에서 도움말 항목에서.xsd 파일을 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a239-124">If for some reason the appropriate .xsd file does not appear in the **XML Schemas** dialog box, you can download the .xsd file from a Help topic.</span></span> <span data-ttu-id="1a239-125">다음 단계에서는 다운로드한 파일을 [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] XML 편집기에 필요한 유니코드 형식으로 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="1a239-125">The following steps help you save the downloaded file in the Unicode format required by the [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] XML Editor.</span></span>  
  
#### <a name="to-copy-a-schema-definition-file-from-a-help-topic"></a><span data-ttu-id="1a239-126">도움말 항목에서 스키마 정의 파일을 복사하려면</span><span class="sxs-lookup"><span data-stu-id="1a239-126">To copy a schema definition file from a Help topic</span></span>  
  
1.  <span data-ttu-id="1a239-127">이 항목의 앞부분에서 설명한 대로 스키마 정의가 포함된 도움말 항목을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="1a239-127">Locate the Help topic that contains the schema definition as described earlier in this topic.</span></span>  
  
    -   <span data-ttu-id="1a239-128">.Dbml 파일에 대 한 참조 [LINQ to SQL에서에서 코드 생성](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1a239-128">For .dbml files, see [Code Generation in LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md).</span></span>  
  
    -   <span data-ttu-id="1a239-129">외부 매핑 파일에 대 한 참조 [외부 매핑](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1a239-129">For external mapping files, see [External Mapping](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md).</span></span>  
  
2.  <span data-ttu-id="1a239-130">클릭 **코드 복사** 를 코드 파일을 클립보드에 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a239-130">Click **Copy Code** to copy the code file to the Clipboard.</span></span>  
  
3.  <span data-ttu-id="1a239-131">메모장을 시작하여 새 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1a239-131">Start Notepad to create a new file.</span></span>  
  
4.  <span data-ttu-id="1a239-132">클립보드에서 메모장 파일로 코드를 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="1a239-132">Paste the code from the clipboard into Notepad file.</span></span>  
  
5.  <span data-ttu-id="1a239-133">메모장에서 **파일** 메뉴를 클릭 하 여 **다른 이름으로 저장**합니다.</span><span class="sxs-lookup"><span data-stu-id="1a239-133">On the Notepad **File** menu, click **Save As**.</span></span>  
  
6.  <span data-ttu-id="1a239-134">에 **인코딩** 상자 **유니코드**합니다.</span><span class="sxs-lookup"><span data-stu-id="1a239-134">In the **Encoding** box, select **Unicode**.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="1a239-135">이렇게 하면 유니코드 16바이트 순서 마커(`FFFE`)가 텍스트 파일 앞에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="1a239-135">This selection guarantees that the Unicode-16 byte-order marker (`FFFE`) is prepended to the text file.</span></span>  
  
7.  <span data-ttu-id="1a239-136">에 **파일 이름** 상자에서 확장명이.xsd 인 파일 이름을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1a239-136">In the **File name** box, create a file name with an .xsd extension.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a239-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1a239-137">See Also</span></span>  
 [<span data-ttu-id="1a239-138">참조</span><span class="sxs-lookup"><span data-stu-id="1a239-138">Reference</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/reference.md)
