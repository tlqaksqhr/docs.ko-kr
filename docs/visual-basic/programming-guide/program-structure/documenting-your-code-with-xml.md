---
title: "코드를 XML로 문서화(Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- XML [Visual Basic], documenting code
- XML comments, Visual Basic
- Visual Basic code, documenting with XML
ms.assetid: a0d35dc7-c5f9-4d74-92ff-a1c6f28d5235
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ddb1f366002c4f0c675c591d83aab1b31ef8f602
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="documenting-your-code-with-xml-visual-basic"></a>코드를 XML로 문서화(Visual Basic)
[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)], XML을 사용 하 여 코드를 문서화할 수 있습니다  
  
## <a name="xml-documentation-comments"></a>XML 문서 주석  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]쉽게 자동으로 프로젝트에 대 한 XML 문서를 만들 수 있는 방법을 제공 합니다. 형식 및 멤버에 대 한 XML 구조는 자동으로 생성할 수 있으며 각 매개 변수 및 기타 설명을 대 한 요약, 설명이 포함 된 설명서를 제공 합니다. 적절 한 설치 프로그램을 XML 문서는.xml 확장명 프로젝트와 동일한 이름 가진 XML 파일에 자동으로 내보내집니다. 자세한 내용은 [/doc](../../../visual-basic/reference/command-line-compiler/doc.md)를 참조하세요.  
  
 XML 파일을 사용 또는 XML로 조작할 수 있습니다. 이 파일은 프로젝트의 출력.exe 또는.dll 파일과 동일한 디렉터리에 있습니다.  
  
 XML 문서 시작 `'''`합니다. 이러한 주석의 처리에는 몇 가지 제한이 있습니다.  
  
-   문서는 잘 구성된 XML이어야 합니다. XML 잘 구성 되지 않았습니다 경고가 생성 되 고 설명서 파일에 오류가 발생 했습니다 표시 하는 주석이 포함 되어 있습니다.  
  
-   개발자는 각자 고유한 태그 집합을 만들 수 있습니다. 권장된 태그 (이 항목의 "관련 섹션" 참조) 집합이 있습니다. 권장 태그 중 일부는 특별한 의미가 있습니다.  
  
    -   \<param> 태그는 매개 변수를 설명하는 데 사용됩니다. 사용되는 경우 컴파일러는 매개 변수가 있고 모든 매개 변수가 문서에서 설명되었는지 확인합니다. 확인에 실패 하는 경우 컴파일러에서 경고가 발생 합니다.  
  
    -   `cref` 특성을 태그에 연결하여 코드 요소에 대한 참조를 제공할 수 있습니다. 컴파일러는 코드 요소가이 존재 하는지 확인 합니다. 확인에 실패 하는 경우 컴파일러에서 경고가 발생 합니다. 또한 컴파일러는 하나는 존중 `Imports` 에 설명 된 형식의 찾을 때 문은 `cref` 특성입니다.  
  
    -   \<요약 > 태그의 IntelliSense에 의해 사용 [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] 형식이 나 멤버에 대 한 추가 정보를 표시 합니다.  
  
## <a name="related-sections"></a>관련 단원  
 문서 주석을 사용 하 여 XML 파일을 만드는 방법에 자세한 다음 항목을 참조 합니다.  
  
-   [/doc](../../../visual-basic/reference/command-line-compiler/doc.md)  
  
-   [XML 주석 태그](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)  
  
-   [XML 파일 처리](../../../visual-basic/programming-guide/program-structure/processing-the-xml-file.md)  
  
-   [방법: XML 문서 만들기](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)  
  
-   [Visual Studio의 XML 도구](/visualstudio/xml-tools/xml-tools-in-visual-studio)  
  
## <a name="see-also"></a>참고 항목  
 [Visual Basic을 사용한 응용 프로그램 개발](../../../visual-basic/developing-apps/index.md)  
 [Visual Basic 프로그래밍 가이드](../../../visual-basic/programming-guide/index.md)
