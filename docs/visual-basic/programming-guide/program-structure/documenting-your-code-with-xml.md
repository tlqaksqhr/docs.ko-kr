---
title: "Documenting Your Code with XML (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "XML, documenting code"
  - "XML comments, Visual Basic"
  - "Visual Basic code, documenting with XML"
ms.assetid: a0d35dc7-c5f9-4d74-92ff-a1c6f28d5235
caps.latest.revision: 17
caps.handback.revision: 17
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Documenting Your Code with XML (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]에서는 XML을 사용하여 코드를 문서화할 수 있습니다.  
  
## XML 문서 주석  
 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]에서는 프로젝트에 대한 XML 문서를 자동으로 만들 수 있는 간편한 방법을 제공합니다.  형식과 멤버에 대한 XML 기초를 자동으로 생성한 다음 요약, 각 매개 변수에 대한 설명문 및 기타 설명을 제공할 수 있습니다.  적절한 설치 프로그램을 사용하면 XML 문서가 XML 파일에 자동으로 생성됩니다. 이때 문서의 이름은 사용자의 프로젝트와 동일하게 되고 확장명은 .xml이 사용됩니다.  자세한 내용은 [\/doc](../../../visual-basic/reference/command-line-compiler/doc.md)를 참조하십시오.  
  
 XML 파일은 그대로 사용하거나 XML로 조작할 수 있습니다.  이 파일은 프로젝트의 출력 .exe 파일이나 .dll 파일과 동일한 디렉터리에 있습니다.  
  
 XML 문서는 `'''`로 시작합니다.  이러한 주석 처리에는 몇 가지 제한이 있습니다.  
  
-   이 문서는 반드시 제대로 구성된 XML이어야 합니다.  XML을 제대로 구성하지 않으면 경고가 생성되고 문서 파일에 오류가 발생하였음을 표시하는 주석이 포함됩니다.  
  
-   개발자는 자유롭게 자체 태그 집합을 만들 수 있습니다.  권장 태그 집합을 보려면 이 항목에서 "관련 단원"을 참조하십시오.  권장 태그 중에는 특별한 의미가 있는 것도 있습니다.  
  
    -   \<param\> 태그는 매개 변수를 설명하는 데 사용됩니다.  이 태그를 사용하면 컴파일러가 매개 변수의 존재를 확인하며 모든 매개 변수가 문서에서 설명됩니다.  확인이 실패하면 컴파일러에 경고가 발생합니다.  
  
    -   `cref` 특성은 모든 태그에 연결되어 코드 요소에 대한 참조를 제공할 수 있습니다.  컴파일러에서는 이 코드 요소가 존재하는지 확인합니다.  확인이 실패하면 컴파일러에 경고가 발생합니다.  또한 컴파일러에서는 `cref` 특성에 설명된 형식을 찾을 때 모든 `Imports` 문을 고려합니다.  
  
    -   \<summary\> 태그는 [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)]의 IntelliSense에 의해 사용되어 형식이나 멤버에 대한 추가 정보를 표시합니다.  
  
## 관련 단원  
 문서 주석으로 XML 파일을 만드는 방법에 대한 자세한 내용은 아래 항목을 참조하십시오.  
  
-   [\/doc](../../../visual-basic/reference/command-line-compiler/doc.md)  
  
-   [XML Comment Tags](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)  
  
-   [Processing the XML File](../../../visual-basic/programming-guide/program-structure/processing-the-xml-file.md)  
  
-   [How to: Create XML Documentation](../Topic/How%20to:%20Create%20XML%20Documentation%20in%20Visual%20Basic.md)  
  
-   [Visual Studio의 XML 도구](/visual-studio/xml-tools/xml-tools-in-visual-studio)  
  
## 참고 항목  
 [Visual Basic을 사용한 응용 프로그램 개발](../../../visual-basic/developing-apps/index.md)   
 [Visual Basic Programming Guide](../../../visual-basic/programming-guide/index.md)