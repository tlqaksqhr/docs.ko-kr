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
author: stevehoag
ms.author: shoag
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
ms.openlocfilehash: 84af19189fa3fc510c8d4f8e408cbb2a393d8b8f
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-enable-xml-intellisense-in-visual-basic"></a>방법: Visual Basic에서 XML IntelliSense 사용
Visual Basic의 XML IntelliSense는 XML 스키마에 정의 된 요소에 대 한 단어 완성을 제공 합니다. Visual Basic의 XML IntelliSense를 사용 하려면 다음을 수행 해야 합니다.  
  
1.  XML 스키마 (XSD) 파일 또는 응용 프로그램은 읽거나 쓰려고 하는 XML 파일에 대 한 파일을 가져옵니다.  
  
2.  프로젝트에 XML 스키마 파일을 포함 합니다.  
  
3.  코드 파일이 나 프로젝트에 대상 네임 스페이스 또는 네임 스페이스를 가져옵니다. 대상 네임 스페이스도 식별 되는 `targetNamespace` 또는 `tns` XSD 스키마의 특성입니다.  
  
     사용 하 여 대상 네임 스페이스를 가져오려면는 `Imports` 문을 사용 하 여 프로젝트의 모든 코드 파일에 대 한 네임 스페이스를 추가 하거나는 **참조** 프로젝트 디자이너의 페이지입니다.  
  
 Visual Basic의 XML IntelliSense의 기능에 자세한 내용은 참조 [Visual Basic의 XML IntelliSense](../../../../visual-basic/programming-guide/language-features/xml/xml-intellisense.md)합니다. XML 네임 스페이스 가져오기에 대 한 자세한 내용은 참조 하십시오. [Imports 문 (XML Namespace)](../../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md) 또는 [프로젝트 디자이너 (Visual Basic), 참조 페이지](https://docs.microsoft.com/visualstudio/ide/reference/references-page-project-designer-visual-basic)합니다.  
  
[!INCLUDE[note_settings_general](../../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
 ![비디오에 링크](../../../../visual-basic/programming-guide/language-features/xml/media/playvideo.gif "PlayVideo") 이 항목의 비디오 버전을 참조 하십시오. [Video How to: Visual Basic의 XML IntelliSense 사용](http://go.microsoft.com/fwlink/?LinkId=102466)합니다. 관련된 비디오 데모를 참조 하십시오. [어떻게 XML IntelliSense 활성화 및 사용 하 여 XML 네임 스페이스 할까요?](http://go.microsoft.com/fwlink/?LinkId=143035)합니다.  
  
## <a name="enable-xml-intellisense-in-visual-basic"></a>Visual Basic에서 XML IntelliSense 사용  
 XML 파일로 있지만 그에 대 한 XSD 스키마 파일 수 없는 경우 s p&1;에서 만들면 XSD 스키마 파일 XML to Schema 마법사를 사용 하 여 됩니다. 또한 Visual Studio XML 편집기에서 스키마 유추를 사용할 수 있습니다.  
  
#### <a name="to-create-an-xsd-schema-file-for-an-xml-file-by-using-the-xml-to-schema-wizard-requires-sp1"></a>XML to Schema 마법사를 사용 하 여 XML 파일에 대 한 XSD 스키마 파일을 만들려면 (하려면 SP1 필요)  
  
1.  프로젝트에서 클릭 **새 항목 추가** 에 **프로젝트** 메뉴.  
  
2.  선택 된 **Xml 스키마를** 중 하나에서 항목 템플릿을 **데이터** 또는 **공통 항목** 템플릿 범주입니다.  
  
3.  XSD 파일 또는 유추 된 스키마 집합에 저장 되 고 다음을 클릭 하는 파일에 대 한 파일 이름을 제공 **추가**합니다.  
  
4.  에 **XML 문서에서 XML 스키마를 유추 집합** 창에서 하나 이상의 XML 문서에서 설정 된 XML 스키마를 추가 합니다.  
  
    -   파일 탐색기를 사용 하 여 XML 문서를 포함 하는 텍스트 파일을 추가 하려면 클릭 **파일에서 추가**합니다.  
  
    -   XML 문서에서 HTTP 주소를 추가 하려면 클릭 **웹에서 추가**합니다.  
  
    -   를 복사 하거나 마법사에는 XML 문서의 내용을 입력 하려면 클릭 **XML 입력 또는 붙여넣기**합니다.  
  
5.  XML 스키마 집합을 유추를 클릭 합니다. 원하는 모든 XML 문서 소스를 지정 했으면 하는 경우 **확인** 설정 XML 스키마를 유추 합니다. 스키마 집합에는 하나 이상의 XSD 파일의 프로젝트 폴더에 저장 됩니다. (스키마에서 각 XML 네임 스페이스에 대 한 파일이 생성 됩니다.)  
  
#### <a name="to-create-an-xsd-schema-file-for-an-xml-file-by-using-schema-inference-in-the-visual-studio-xml-editor"></a>Visual Studio XML 편집기에서 스키마 유추를 사용 하 여 XML 파일에 대 한 XSD 스키마 파일을 만들려면  
  
1.  Visual Studio XML 디자이너에서 XML 파일을 편집 합니다.  
  
2.  XML 파일 안에 있으면 커서는 **XML** 메뉴가 나타납니다. 클릭 **Create Schema** 에 **XML** 메뉴. XSD 파일은 XML 파일에서 유추 된 XSD 스키마에서 만들어집니다.  
  
3.  XSD 스키마 파일을 저장 합니다.  
  
    > [!NOTE]
    >  서로 다른 XSD 스키마가 동일한 스키마를 유추 하는 여러 XML 문서에서 유추 될 수 있습니다. 이 XML 파일 한 개 안 되며, 발견 된 특정 요소 및 특성 또는 요소 예를 들어 다른 순서에 포함 된 경우 발생할 수 있습니다. XSD 스키마 유추를 사용 하는 경우에 완결성 및 정확도 대해 유추 된 XSD 스키마를 검토 해야 합니다.  
  
#### <a name="to-include-an-xsd-schema-file"></a>XSD 스키마 파일을 포함 하려면  
  
-   기본적으로 Visual Basic 프로젝트의 XSD 파일을 볼 수 없습니다. XSD 파일에는 프로젝트에 대 한 폴더에 이미 포함 되어 있는 경우 클릭 하 고 **모든 파일 표시** 단추 **솔루션 탐색기**합니다. XSD 파일을 찾고 **솔루션 탐색기**파일을 마우스 오른쪽 단추로 클릭 하 고 클릭 **프로젝트에 파일 포함**합니다.  
  
-   경우 XSD 파일에 아직 없는 프로젝트의 일부 **솔루션 탐색기**, 가리킨, XSD 파일을 저장 하려는 폴더를 마우스 오른쪽 단추로 클릭 **추가**를 클릭 하 고 **기존 항목**합니다. XSD 파일을 찾은 다음 클릭 **추가**합니다.  
  
#### <a name="to-import-an-xml-namespace-in-a-code-file"></a>코드 파일에서 XML 네임 스페이스를 가져오려면  
  
1.  XSD 스키마에서 대상 네임 스페이스를 식별 합니다.  
  
2.  코드 파일의 시작 부분에 추가 하는 `Imports` 대상 XML 네임 스페이스, 다음 예제와 같이 대 한 정보입니다.  
  
     [!code-vb[VbXMLSamples #&1;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-enable-xml-intellisense_1.vb)]  
  
     기본 네임 스페이스와 XML 네임 스페이스를 가져오려면 즉, XML 요소 및 네임 스페이스 접두사를 갖지 않는 특성에 적용 되는 네임 스페이스 추가 `Imports` 대상 기본 XML 네임 스페이스에 대 한 정보입니다. 네임 스페이스 접두사를 지정 하지 마십시오. 다음은의 예는 `Imports` 문입니다.  
  
     [!code-vb[VbXmlSamples #&50;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-enable-xml-intellisense_2.vb)]  
  
#### <a name="to-import-an-xml-namespace-for-all-files-in-a-project"></a>프로젝트의 모든 파일에 대 한 XML 네임 스페이스를 가져오려면  
  
1.  코드 파일에서 가져온 XML 네임 스페이스만 해당 코드 파일에 적용 됩니다. 프로젝트의 모든 코드 파일에 적용 되는 XML 네임 스페이스를 가져오려면 두 번 클릭 하 여 프로젝트 디자이너를 열고 **My Project** 에서 **솔루션 탐색기**합니다.  
  
2.  에 **참조** 탭에 **가져온 네임 스페이스** 상자는 전체 XML 네임 스페이스 선언 형식의 대상 XML 네임 스페이스를 입력 합니다 (예를 들어 `<xmlns: ns="http://sampleNamespace">`). 대상 XML 네임 스페이스에서 네임 스페이스 접두사를 지정 하지 않으면, 네임 스페이스는 프로젝트에 대 한 기본 XML 네임 스페이스가 됩니다.  
  
3.  클릭 **사용자 가져오기 추가**합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Imports 문 (XML Namespace)](../../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)   
 [프로젝트 디자이너, 참조 페이지(Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/references-page-project-designer-visual-basic)   
 [Visual Basic의 XML IntelliSense](../../../../visual-basic/programming-guide/language-features/xml/xml-intellisense.md)

