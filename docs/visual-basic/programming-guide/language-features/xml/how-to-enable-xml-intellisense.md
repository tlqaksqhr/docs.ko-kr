---
title: "방법: Visual Basic에서 XML IntelliSense 사용 | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- XML IntelliSense [Visual Basic]
- XML [Visual Basic], IntelliSense
- IntelliSense [Visual Basic], XML
ms.assetid: af67d0ee-a4a6-4abf-9c07-5a8cfe80d111
caps.latest.revision: 25
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 31905a37f09db5f5192123f0118252fbe8b02eff
ms.openlocfilehash: e367016c93586ad34492628b6a4384a5ef1b6acd
ms.contentlocale: ko-kr
ms.lasthandoff: 05/26/2017

---
# <a name="how-to-enable-xml-intellisense-in-visual-basic"></a><span data-ttu-id="a2907-102">방법: Visual Basic에서 XML IntelliSense 사용</span><span class="sxs-lookup"><span data-stu-id="a2907-102">How to: Enable XML IntelliSense in Visual Basic</span></span>
<span data-ttu-id="a2907-103">Visual Basic의 XML IntelliSense는 XML 스키마에 정의 된 요소에 대 한 단어 완성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2907-103">XML IntelliSense in Visual Basic provides word completion for elements that are defined in an XML schema.</span></span> <span data-ttu-id="a2907-104">Visual Basic의 XML IntelliSense를 사용 하려면 다음을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2907-104">To enable XML IntelliSense in Visual Basic, you must do the following:</span></span>  
  
1.  <span data-ttu-id="a2907-105">XML 스키마 (XSD) 파일 또는 응용 프로그램은 읽거나 쓰려고 하는 XML 파일에 대 한 파일을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a2907-105">Obtain the XML schema (XSD) file or files for the XML files that your application will read from or write to.</span></span>  
  
2.  <span data-ttu-id="a2907-106">프로젝트에 XML 스키마 파일을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2907-106">Include the XML schema files in your project.</span></span>  
  
3.  <span data-ttu-id="a2907-107">코드 파일이 나 프로젝트에 대상 네임 스페이스 또는 네임 스페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a2907-107">Import the target namespace or namespaces into your code file or project.</span></span> <span data-ttu-id="a2907-108">대상 네임 스페이스도 식별 되는 `targetNamespace` 또는 `tns` XSD 스키마의 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="a2907-108">A target namespace is identified by the `targetNamespace` or `tns` attribute of your XSD schema.</span></span>  
  
     <span data-ttu-id="a2907-109">사용 하 여 대상 네임 스페이스를 가져오려면는 `Imports` 문을 사용 하 여 프로젝트의 모든 코드 파일에 대 한 네임 스페이스를 추가 하거나는 **참조** 프로젝트 디자이너의 페이지입니다.</span><span class="sxs-lookup"><span data-stu-id="a2907-109">To import a target namespace, use the `Imports` statement, or add a namespace for all code files in a project by using the **References** page of the Project Designer.</span></span>  
  
 <span data-ttu-id="a2907-110">Visual Basic의 XML IntelliSense의 기능에 자세한 내용은 참조 [Visual Basic의 XML IntelliSense](../../../../visual-basic/programming-guide/language-features/xml/xml-intellisense.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a2907-110">For more information on the capabilities of XML IntelliSense in Visual Basic, see [XML IntelliSense in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/xml-intellisense.md).</span></span> <span data-ttu-id="a2907-111">XML 네임 스페이스 가져오기에 대 한 자세한 내용은 참조 하십시오. [Imports 문 (XML Namespace)](../../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md) 또는 [프로젝트 디자이너 (Visual Basic), 참조 페이지](https://docs.microsoft.com/visualstudio/ide/reference/references-page-project-designer-visual-basic)합니다.</span><span class="sxs-lookup"><span data-stu-id="a2907-111">For more information on importing XML namespaces, see [Imports Statement (XML Namespace)](../../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md) or [References Page, Project Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/references-page-project-designer-visual-basic).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
 <span data-ttu-id="a2907-112">![비디오에 링크](../../../../visual-basic/programming-guide/language-features/xml/media/playvideo.gif "PlayVideo") 이 항목의 비디오 버전을 참조 하십시오. [Video How to: Visual Basic의 XML IntelliSense 사용](http://go.microsoft.com/fwlink/?LinkId=102466)합니다.</span><span class="sxs-lookup"><span data-stu-id="a2907-112">![link to video](../../../../visual-basic/programming-guide/language-features/xml/media/playvideo.gif "PlayVideo") For a video version of this topic, see [Video How to: Enable XML IntelliSense in Visual Basic](http://go.microsoft.com/fwlink/?LinkId=102466).</span></span> <span data-ttu-id="a2907-113">관련된 비디오 데모를 참조 하십시오. [어떻게 XML IntelliSense 활성화 및 사용 하 여 XML 네임 스페이스 할까요?](http://go.microsoft.com/fwlink/?LinkId=143035)합니다.</span><span class="sxs-lookup"><span data-stu-id="a2907-113">For a related video demonstration, see [How Do I Enable XML IntelliSense and Use XML Namespaces?](http://go.microsoft.com/fwlink/?LinkId=143035).</span></span>  
  
## <a name="enable-xml-intellisense-in-visual-basic"></a><span data-ttu-id="a2907-114">Visual Basic에서 XML IntelliSense 사용</span><span class="sxs-lookup"><span data-stu-id="a2907-114">Enable XML IntelliSense in Visual Basic</span></span>  
 <span data-ttu-id="a2907-115">XML 파일로 있지만 그에 대 한 XSD 스키마 파일 수 없는 경우 s p&1;에서 만들면 XSD 스키마 파일 XML to Schema 마법사를 사용 하 여 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2907-115">If you have an XML file but you do not have an XSD schema file for it, in SP1 you can create an XSD schema file by using the XML to Schema Wizard.</span></span> <span data-ttu-id="a2907-116">또한 Visual Studio XML 편집기에서 스키마 유추를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2907-116">You can also use schema inference in the Visual Studio XML Editor.</span></span>  
  
#### <a name="to-create-an-xsd-schema-file-for-an-xml-file-by-using-the-xml-to-schema-wizard-requires-sp1"></a><span data-ttu-id="a2907-117">XML to Schema 마법사를 사용 하 여 XML 파일에 대 한 XSD 스키마 파일을 만들려면 (하려면 SP1 필요)</span><span class="sxs-lookup"><span data-stu-id="a2907-117">To create an XSD schema file for an XML file by using the XML to Schema Wizard (requires SP1)</span></span>  
  
1.  <span data-ttu-id="a2907-118">프로젝트에서 클릭 **새 항목 추가** 에 **프로젝트** 메뉴.</span><span class="sxs-lookup"><span data-stu-id="a2907-118">In your project, click **Add New Item** on the **Project** menu.</span></span>  
  
2.  <span data-ttu-id="a2907-119">선택 된 **Xml 스키마를** 중 하나에서 항목 템플릿을 **데이터** 또는 **공통 항목** 템플릿 범주입니다.</span><span class="sxs-lookup"><span data-stu-id="a2907-119">Select the **Xml to Schema** item template from either the **Data** or **Common Items** template categories.</span></span>  
  
3.  <span data-ttu-id="a2907-120">XSD 파일 또는 유추 된 스키마 집합에 저장 되 고 다음을 클릭 하는 파일에 대 한 파일 이름을 제공 **추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="a2907-120">Provide a file name for the XSD file or files that the inferred schema set will be stored in, and then click **Add**.</span></span>  
  
4.  <span data-ttu-id="a2907-121">에 **XML 문서에서 XML 스키마를 유추 집합** 창에서 하나 이상의 XML 문서에서 설정 된 XML 스키마를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2907-121">In the **Infer XML Schema set from XML documents** window, add one or more XML documents to infer the XML schema set from.</span></span>  
  
    -   <span data-ttu-id="a2907-122">파일 탐색기를 사용 하 여 XML 문서를 포함 하는 텍스트 파일을 추가 하려면 클릭 **파일에서 추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="a2907-122">To add text files that contain XML documents by using File Explorer, click **Add from File**.</span></span>  
  
    -   <span data-ttu-id="a2907-123">XML 문서에서 HTTP 주소를 추가 하려면 클릭 **웹에서 추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="a2907-123">To add an XML document from an HTTP address, click **Add from Web**.</span></span>  
  
    -   <span data-ttu-id="a2907-124">를 복사 하거나 마법사에는 XML 문서의 내용을 입력 하려면 클릭 **XML 입력 또는 붙여넣기**합니다.</span><span class="sxs-lookup"><span data-stu-id="a2907-124">To copy or type the contents of an XML document into the wizard, click **Type or paste XML**.</span></span>  
  
5.  <span data-ttu-id="a2907-125">XML 스키마 집합을 유추를 클릭 합니다. 원하는 모든 XML 문서 소스를 지정 했으면 하는 경우 **확인** 설정 XML 스키마를 유추 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2907-125">When you have specified all the XML document sources from which you want to infer the XML schema set, click **OK** to infer the XML schema set.</span></span> <span data-ttu-id="a2907-126">스키마 집합에는 하나 이상의 XSD 파일의 프로젝트 폴더에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2907-126">The schema set is saved in your project folder in one or more XSD files.</span></span> <span data-ttu-id="a2907-127">(스키마에서 각 XML 네임 스페이스에 대 한 파일이 생성 됩니다.)</span><span class="sxs-lookup"><span data-stu-id="a2907-127">(For each XML namespace in the schema, a file is created.)</span></span>  
  
#### <a name="to-create-an-xsd-schema-file-for-an-xml-file-by-using-schema-inference-in-the-visual-studio-xml-editor"></a><span data-ttu-id="a2907-128">Visual Studio XML 편집기에서 스키마 유추를 사용 하 여 XML 파일에 대 한 XSD 스키마 파일을 만들려면</span><span class="sxs-lookup"><span data-stu-id="a2907-128">To create an XSD schema file for an XML file by using schema inference in the Visual Studio XML Editor</span></span>  
  
1.  <span data-ttu-id="a2907-129">Visual Studio XML 디자이너에서 XML 파일을 편집 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2907-129">Edit the XML file in the Visual Studio XML Designer.</span></span>  
  
2.  <span data-ttu-id="a2907-130">XML 파일 안에 있으면 커서는 **XML** 메뉴가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="a2907-130">When the cursor is somewhere in the XML file, the **XML** menu appears.</span></span> <span data-ttu-id="a2907-131">클릭 **Create Schema** 에 **XML** 메뉴.</span><span class="sxs-lookup"><span data-stu-id="a2907-131">Click **Create Schema** on the **XML** menu.</span></span> <span data-ttu-id="a2907-132">XSD 파일은 XML 파일에서 유추 된 XSD 스키마에서 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="a2907-132">An XSD file is created from XSD schema inferred from the XML file.</span></span>  
  
3.  <span data-ttu-id="a2907-133">XSD 스키마 파일을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2907-133">Save the XSD schema file.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a2907-134">서로 다른 XSD 스키마가 동일한 스키마를 유추 하는 여러 XML 문서에서 유추 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2907-134">Different XSD schemas might be inferred from multiple XML documents that are intended to have the same schema.</span></span> <span data-ttu-id="a2907-135">이 XML 파일 한 개 안 되며, 발견 된 특정 요소 및 특성 또는 요소 예를 들어 다른 순서에 포함 된 경우 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2907-135">This can occur when particular elements and attributes are found in one XML file and not in another, or when elements are included in different order, for example.</span></span> <span data-ttu-id="a2907-136">XSD 스키마 유추를 사용 하는 경우에 완결성 및 정확도 대해 유추 된 XSD 스키마를 검토 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2907-136">You should review inferred XSD schemas for completeness and accuracy when you use XSD schema inference.</span></span>  
  
#### <a name="to-include-an-xsd-schema-file"></a><span data-ttu-id="a2907-137">XSD 스키마 파일을 포함 하려면</span><span class="sxs-lookup"><span data-stu-id="a2907-137">To include an XSD schema file</span></span>  
  
-   <span data-ttu-id="a2907-138">기본적으로 Visual Basic 프로젝트의 XSD 파일을 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a2907-138">By default, you cannot see XSD files in Visual Basic projects.</span></span> <span data-ttu-id="a2907-139">XSD 파일에는 프로젝트에 대 한 폴더에 이미 포함 되어 있는 경우 클릭 하 고 **모든 파일 표시** 단추 **솔루션 탐색기**합니다.</span><span class="sxs-lookup"><span data-stu-id="a2907-139">If your XSD file is already included in the folders for your project, click the **Show All Files** button in **Solution Explorer**.</span></span> <span data-ttu-id="a2907-140">XSD 파일을 찾고 **솔루션 탐색기**파일을 마우스 오른쪽 단추로 클릭 하 고 클릭 **프로젝트에 파일 포함**합니다.</span><span class="sxs-lookup"><span data-stu-id="a2907-140">Locate the XSD file in **Solution Explorer**, right-click the file, and click **Include File in Project**.</span></span>  
  
-   <span data-ttu-id="a2907-141">경우 XSD 파일에 아직 없는 프로젝트의 일부 **솔루션 탐색기**, 가리킨, XSD 파일을 저장 하려는 폴더를 마우스 오른쪽 단추로 클릭 **추가**를 클릭 하 고 **기존 항목**합니다.</span><span class="sxs-lookup"><span data-stu-id="a2907-141">If your XSD file is not already part of your project, in **Solution Explorer**, right-click the folder in which you want to store the XSD file, point to **Add**, and then click **Existing Item**.</span></span> <span data-ttu-id="a2907-142">XSD 파일을 찾은 다음 클릭 **추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="a2907-142">Locate your XSD file and then click **Add**.</span></span>  
  
#### <a name="to-import-an-xml-namespace-in-a-code-file"></a><span data-ttu-id="a2907-143">코드 파일에서 XML 네임 스페이스를 가져오려면</span><span class="sxs-lookup"><span data-stu-id="a2907-143">To import an XML namespace in a code file</span></span>  
  
1.  <span data-ttu-id="a2907-144">XSD 스키마에서 대상 네임 스페이스를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2907-144">Identify the target namespace from your XSD schema.</span></span>  
  
2.  <span data-ttu-id="a2907-145">코드 파일의 시작 부분에 추가 하는 `Imports` 대상 XML 네임 스페이스, 다음 예제와 같이 대 한 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="a2907-145">At the beginning of the code file, add an `Imports` statement for the target XML namespace, as shown in the following example.</span></span>  
  
     <span data-ttu-id="a2907-146">[!code-vb[VbXMLSamples #&1;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-enable-xml-intellisense_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="a2907-146">[!code-vb[VbXMLSamples#1](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-enable-xml-intellisense_1.vb)]</span></span>  
  
     <span data-ttu-id="a2907-147">기본 네임 스페이스와 XML 네임 스페이스를 가져오려면 즉, XML 요소 및 네임 스페이스 접두사를 갖지 않는 특성에 적용 되는 네임 스페이스 추가 `Imports` 대상 기본 XML 네임 스페이스에 대 한 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="a2907-147">To import an XML namespace as the default namespace, that is, the namespace that is applied to XML elements and attributes that do not have a namespace prefix, add an `Imports` statement for the target default XML namespace.</span></span> <span data-ttu-id="a2907-148">네임 스페이스 접두사를 지정 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="a2907-148">Do not specify a namespace prefix.</span></span> <span data-ttu-id="a2907-149">다음은의 예는 `Imports` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="a2907-149">Following is an example of an `Imports` statement.</span></span>  
  
     <span data-ttu-id="a2907-150">[!code-vb[VbXmlSamples #&50;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-enable-xml-intellisense_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="a2907-150">[!code-vb[VbXmlSamples#50](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-enable-xml-intellisense_2.vb)]</span></span>  
  
#### <a name="to-import-an-xml-namespace-for-all-files-in-a-project"></a><span data-ttu-id="a2907-151">프로젝트의 모든 파일에 대 한 XML 네임 스페이스를 가져오려면</span><span class="sxs-lookup"><span data-stu-id="a2907-151">To import an XML namespace for all files in a project</span></span>  
  
1.  <span data-ttu-id="a2907-152">코드 파일에서 가져온 XML 네임 스페이스만 해당 코드 파일에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2907-152">An XML namespace imported in a code file applies to that code file only.</span></span> <span data-ttu-id="a2907-153">프로젝트의 모든 코드 파일에 적용 되는 XML 네임 스페이스를 가져오려면 두 번 클릭 하 여 프로젝트 디자이너를 열고 **My Project** 에서 **솔루션 탐색기**합니다.</span><span class="sxs-lookup"><span data-stu-id="a2907-153">To import an XML namespace that applies to all code files in a project, open the Project Designer by double-clicking **My Project** in **Solution Explorer**.</span></span>  
  
2.  <span data-ttu-id="a2907-154">에 **참조** 탭에 **가져온 네임 스페이스** 상자는 전체 XML 네임 스페이스 선언 형식의 대상 XML 네임 스페이스를 입력 합니다 (예를 들어 `<xmlns: ns="http://sampleNamespace">`).</span><span class="sxs-lookup"><span data-stu-id="a2907-154">On the **References** tab, in the **Imported namespaces** box, type the target XML namespace in the form of a full XML namespace declaration (for example, `<xmlns: ns="http://sampleNamespace">`).</span></span> <span data-ttu-id="a2907-155">대상 XML 네임 스페이스에서 네임 스페이스 접두사를 지정 하지 않으면, 네임 스페이스는 프로젝트에 대 한 기본 XML 네임 스페이스가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2907-155">If the target XML namespace does not specify a namespace prefix, the namespace will be the default XML namespace for the project.</span></span>  
  
3.  <span data-ttu-id="a2907-156">클릭 **사용자 가져오기 추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="a2907-156">Click **Add User Import**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2907-157">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a2907-157">See Also</span></span>  
 <span data-ttu-id="a2907-158">[Imports 문 (XML Namespace)](../../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md) </span><span class="sxs-lookup"><span data-stu-id="a2907-158">[Imports Statement (XML Namespace)](../../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md) </span></span>  
<span data-ttu-id="a2907-159"> [프로젝트 디자이너, 참조 페이지(Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/references-page-project-designer-visual-basic) </span><span class="sxs-lookup"><span data-stu-id="a2907-159"> [References Page, Project Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/references-page-project-designer-visual-basic) </span></span>  
<span data-ttu-id="a2907-160"> [Visual Basic의 XML IntelliSense](../../../../visual-basic/programming-guide/language-features/xml/xml-intellisense.md)</span><span class="sxs-lookup"><span data-stu-id="a2907-160"> [XML IntelliSense in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/xml-intellisense.md)</span></span>

