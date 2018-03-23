---
title: -doc
ms.date: 03/10/2018
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- doc compiler option [Visual Basic]
- -doc compiler option [Visual Basic]
- /doc compiler option [Visual Basic]
ms.assetid: 5fc32ec9-a149-4648-994c-a8d0cccd0a65
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0948b9ef0675541ca595bb297e01e62c9d79a181
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/22/2018
---
# <a name="-doc"></a><span data-ttu-id="2dd72-102">-doc</span><span class="sxs-lookup"><span data-stu-id="2dd72-102">-doc</span></span>
<span data-ttu-id="2dd72-103">XML 파일에 대해 문서 주석을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="2dd72-103">Processes documentation comments to an XML file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2dd72-104">구문</span><span class="sxs-lookup"><span data-stu-id="2dd72-104">Syntax</span></span>  
  
```  
-doc[+ | -]  
' -or-  
-doc:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="2dd72-105">인수</span><span class="sxs-lookup"><span data-stu-id="2dd72-105">Arguments</span></span>  
  
|<span data-ttu-id="2dd72-106">용어</span><span class="sxs-lookup"><span data-stu-id="2dd72-106">Term</span></span>|<span data-ttu-id="2dd72-107">정의</span><span class="sxs-lookup"><span data-stu-id="2dd72-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="2dd72-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="2dd72-108">`+` &#124; `-`</span></span>|<span data-ttu-id="2dd72-109">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="2dd72-109">Optional.</span></span> <span data-ttu-id="2dd72-110">지정 +, 또는 그냥 `-doc`, 컴파일러가 문서 정보를 생성 하는 XML 파일에 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="2dd72-110">Specifying +, or just `-doc`, causes the compiler to generate documentation information and place it in an XML file.</span></span> <span data-ttu-id="2dd72-111">지정 `-` 지정 하지 않는 것과 같습니다 `-doc`, 하므로 문서 정보가 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2dd72-111">Specifying `-` is the equivalent of not specifying `-doc`, causing no documentation information to be created.</span></span>|  
|`file`|<span data-ttu-id="2dd72-112">`-doc:`를 사용하는 경우 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="2dd72-112">Required if `-doc:` is used.</span></span> <span data-ttu-id="2dd72-113">컴파일의 소스 코드 파일에서 사용 되는 출력 XML 파일을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2dd72-113">Specifies the output XML file, which is populated with the comments from the source-code files of the compilation.</span></span> <span data-ttu-id="2dd72-114">파일 이름에 공백이 있으면 이름을 따옴표로 묶습니다 ("").</span><span class="sxs-lookup"><span data-stu-id="2dd72-114">If the file name contains a space, surround the name with quotation marks (" ").</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2dd72-115">설명</span><span class="sxs-lookup"><span data-stu-id="2dd72-115">Remarks</span></span>  
 <span data-ttu-id="2dd72-116">`-doc` 옵션 컴파일러 문서 주석을 포함 하는 XML 파일을 생성 하는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="2dd72-116">The `-doc` option controls whether the compiler generates an XML file containing the documentation comments.</span></span> <span data-ttu-id="2dd72-117">사용 하는 경우는 `-doc:file` 구문에서 `file` 매개 변수는 XML 파일의 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2dd72-117">If you use the `-doc:file` syntax, the `file` parameter specifies the name of the XML file.</span></span> <span data-ttu-id="2dd72-118">사용 하는 경우 `-doc` 또는 `-doc+`, 컴파일러에서는 실행 파일 또는 작성 하는 라이브러리에서 XML 파일 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2dd72-118">If you use `-doc` or `-doc+`, the compiler takes the XML file name from the executable file or library that the compiler is creating.</span></span> <span data-ttu-id="2dd72-119">사용 하는 경우 `-doc-` 지정 하지 않으면 또는 `-doc` 옵션을 컴파일러를 XML 파일로 만들지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2dd72-119">If you use `-doc-` or do not specify the `-doc` option, the compiler does not create an XML file.</span></span>  
  
 <span data-ttu-id="2dd72-120">소스 코드 파일 문서 주석을 다음 정의 앞 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2dd72-120">In source-code files, documentation comments can precede the following definitions:</span></span>  
  
-   <span data-ttu-id="2dd72-121">사용자 정의 형식는 [클래스](../../../visual-basic/language-reference/statements/class-statement.md) 또는 [인터페이스](../../../visual-basic/language-reference/statements/interface-statement.md)</span><span class="sxs-lookup"><span data-stu-id="2dd72-121">User-defined types, such as a [class](../../../visual-basic/language-reference/statements/class-statement.md) or [interface](../../../visual-basic/language-reference/statements/interface-statement.md)</span></span>  
  
-   <span data-ttu-id="2dd72-122">멤버는 필드와 같은 [이벤트](../../../visual-basic/language-reference/statements/event-statement.md), [속성](../../../visual-basic/language-reference/statements/property-statement.md), [함수](../../../visual-basic/language-reference/statements/function-statement.md), 또는 [서브루틴](../../../visual-basic/language-reference/statements/sub-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2dd72-122">Members, such as a field, [event](../../../visual-basic/language-reference/statements/event-statement.md), [property](../../../visual-basic/language-reference/statements/property-statement.md), [function](../../../visual-basic/language-reference/statements/function-statement.md), or [subroutine](../../../visual-basic/language-reference/statements/sub-statement.md).</span></span>  
  
 <span data-ttu-id="2dd72-123">생성 된 XML 파일을 사용 하는 [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] [IntelliSense](/visualstudio/ide/using-intellisense) 기능, XML 파일의 파일 이름을 지원 하려는 어셈블리와 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="2dd72-123">To use the generated XML file with the [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] [IntelliSense](/visualstudio/ide/using-intellisense) feature, let the file name of the XML file be the same as the assembly you want to support.</span></span> <span data-ttu-id="2dd72-124">어셈블리에서 참조 되는 경우 되도록 XML 파일을 어셈블리와 동일한 디렉터리에 있는지 확인은 [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] 프로젝트.xml 파일과 함께 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="2dd72-124">Make sure the XML file is in the same directory as the assembly so that when the assembly is referenced in the [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] project, the .xml file is found as well.</span></span> <span data-ttu-id="2dd72-125">XML 문서 파일 intellisense는 프로젝트 내 또는 프로젝트에서 참조 하는 프로젝트 내에서 코드에 대 한 작동 하려면 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2dd72-125">XML documentation files are not required for IntelliSense to work for code within a project or within projects referenced by a project.</span></span>  
  
 <span data-ttu-id="2dd72-126">사용 하 여 컴파일하지 않으면 `/target:module`, XML 파일에는 태그가 포함 된 `<assembly></assembly>`합니다.</span><span class="sxs-lookup"><span data-stu-id="2dd72-126">Unless you compile with `/target:module`, the XML file contains the tags `<assembly></assembly>`.</span></span> <span data-ttu-id="2dd72-127">이러한 태그는 컴파일의 출력 파일에 대 한 어셈블리 매니페스트를 포함 하는 파일의 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2dd72-127">These tags specify the name of the file containing the assembly manifest for the output file of the compilation.</span></span>  
  
 <span data-ttu-id="2dd72-128">참조 [XML 주석 태그](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md) 코드 주석에서 문서를 생성 하는 방법에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="2dd72-128">See [XML Comment Tags](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md) for ways to generate documentation from comments in your code.</span></span>  
  
|<span data-ttu-id="2dd72-129">Visual Studio에서 doc 통합 개발 환경 설정-</span><span class="sxs-lookup"><span data-stu-id="2dd72-129">To set -doc in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="2dd72-130">1.  **솔루션 탐색기**에서 프로젝트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2dd72-130">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="2dd72-131">**프로젝트** 메뉴에서 **속성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2dd72-131">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="2dd72-132">2.  **컴파일** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2dd72-132">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="2dd72-133">3.  값을 설정는 **XML 문서 파일 생성** 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="2dd72-133">3.  Set the value in the **Generate XML documentation file** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="2dd72-134">예제</span><span class="sxs-lookup"><span data-stu-id="2dd72-134">Example</span></span>  
 <span data-ttu-id="2dd72-135">참조 [Your 코드를 XML로 문서화](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md) 샘플입니다.</span><span class="sxs-lookup"><span data-stu-id="2dd72-135">See [Documenting Your Code with XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md) for a sample.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2dd72-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2dd72-136">See Also</span></span>  
 [<span data-ttu-id="2dd72-137">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="2dd72-137">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="2dd72-138">코드를 XML로 문서화</span><span class="sxs-lookup"><span data-stu-id="2dd72-138">Documenting Your Code with XML</span></span>](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)
