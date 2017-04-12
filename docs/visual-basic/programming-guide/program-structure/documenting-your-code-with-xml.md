---
title: "XML (Visual Basic)를 사용 하 여 코드 문서화 | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- XML, documenting code
- XML comments, Visual Basic
- Visual Basic code, documenting with XML
ms.assetid: a0d35dc7-c5f9-4d74-92ff-a1c6f28d5235
caps.latest.revision: 17
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
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 2ec4907ff96a0861f97de21bdf45662c558d0a95
ms.lasthandoff: 03/13/2017

---
# <a name="documenting-your-code-with-xml-visual-basic"></a>코드를 XML로 문서화(Visual Basic)
[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], XML을 사용 하 여 코드를 문서화할 수 있습니다  
  
## <a name="xml-documentation-comments"></a>XML 문서 주석  
 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]프로젝트에 대 한 XML 문서를 자동으로 만들 하는 간편한 방법을 제공 합니다. 형식 및 멤버에 대 한 XML 기초가 자동으로 생성할 수 있으며 각 매개 변수 및 기타 설명에 대 한 요약, 설명이 포함 된 설명서를 제공 합니다. 적절 한 설치 프로그램을 XML 문서는.xml 확장명 프로젝트와 동일한 이름 가진 XML 파일에 자동으로 내보내집니다. 자세한 내용은 참조 [/doc](../../../visual-basic/reference/command-line-compiler/doc.md)합니다.  
  
 XML 파일을 사용 또는 XML로 조작할 수 있습니다. 이 파일은 프로젝트의 출력.exe 또는.dll 파일과 동일한 디렉터리에 있습니다.  
  
 XML 문서 시작 `'''`합니다. 이러한 주석 처리에 몇 가지 제한이 있습니다.  
  
-   설명서는 제대로 구성 되어야 합니다. XML입니다. XML이 제대로 구성 되지 경우는 경고가 생성 되 고 문서 파일에 오류가 발생 했습니다 표시 하는 주석이 포함 되어 있습니다.  
  
-   개발자는 각자의 태그를 만들 수 있습니다. 권장된 태그 (이 항목의 "관련 된 섹션" 참조) 집합이 있습니다. 권장된 태그 중 일부는 특별 한 의미를 갖습니다.  
  
    -   \<param > 태그는 매개 변수를 설명 하는 데 사용 됩니다. 사용 하는 경우 컴파일러는 매개 변수 있고 모든 매개 변수는 설명서에 설명 되어 있는지 확인 하십시오. 확인에 실패 하는 경우 컴파일러 경고를 생성 합니다.  
  
    -   `cref` 코드 요소에 대 한 참조를 제공 하기 위해 모든 태그에 특성을 연결할 수 있습니다. 컴파일러는이 코드 요소가 존재 하는지 확인 합니다. 확인에 실패 하는 경우 컴파일러 경고를 생성 합니다. 또한 컴파일러는 모든 고객 존중 `Imports` 에 설명 된 형식의 찾을 때 문은 `cref` 특성입니다.  
  
    -   \<요약 > 태그의 intellisense에서 사용 [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] 형식 또는 멤버에 대 한 추가 정보를 표시 합니다.  
  
## <a name="related-sections"></a>관련 단원  
 자세한 내용은 설명서 주석을 사용 하 여 XML 파일을 만드는 방법에 다음 항목을 참조 합니다.  
  
-   [/doc](../../../visual-basic/reference/command-line-compiler/doc.md)  
  
-   [XML 주석 태그](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)  
  
-   [XML 파일 처리](../../../visual-basic/programming-guide/program-structure/processing-the-xml-file.md)  
  
-   [방법: XML 문서 만들기](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)  
  
-   [Visual Studio의 XML 도구](https://docs.microsoft.com/visualstudio/xml-tools/xml-tools-in-visual-studio)  
  
## <a name="see-also"></a>참고 항목  
 [Visual Basic로 응용 프로그램 개발](../../../visual-basic/developing-apps/index.md)   
 [Visual Basic 프로그래밍 가이드](../../../visual-basic/programming-guide/index.md)
