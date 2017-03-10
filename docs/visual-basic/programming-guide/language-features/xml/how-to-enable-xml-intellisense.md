---
title: "How to: Enable XML IntelliSense in Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "XML IntelliSense [Visual Basic]"
  - "XML [Visual Basic], IntelliSense"
  - "IntelliSense [Visual Basic], XML"
ms.assetid: af67d0ee-a4a6-4abf-9c07-5a8cfe80d111
caps.latest.revision: 25
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 25
---
# How to: Enable XML IntelliSense in Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Visual Basic의 XML IntelliSense는 XML 스키마에 정의된 요소에 대한 단어 완성 기능을 제공합니다.  Visual Basic에서 XML IntelliSense를 사용하려면 다음을 수행해야 합니다.  
  
1.  응용 프로그램이 읽거나 쓸 XML 파일에 대해 XML 스키마\(XSD\) 파일을 가져옵니다.  
  
2.  XML 스키마 파일을 프로젝트에 포함시킵니다.  
  
3.  대상 네임스페이스를 코드 파일 또는 프로젝트로 가져옵니다.  대상 네임스페이스는 XSD 스키마의 `targetNamespace` 또는 `tns` 특성에 의해 식별됩니다.  
  
     대상 네임스페이스를 가져오려면 `Imports` 문을 사용하거나, 프로젝트 디자이너의 **참조** 페이지를 사용하여 프로젝트의 모든 코드 파일에 대해 네임스페이스를 추가합니다.  
  
 Visual Basic의 XML IntelliSense 기능에 대한 자세한 내용은 [XML IntelliSense in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/xml-intellisense.md)를 참조하십시오.  XML 네임스페이스를 가져오는 방법에 대한 자세한 내용은 [Imports Statement \(XML Namespace\)](../../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md) 또는 [참조 페이지, 프로젝트 디자이너\(Visual Basic\)](/visual-studio/ide/reference/references-page-project-designer-visual-basic)를 참조하십시오.  
  
 [!INCLUDE[note_settings_general](../../../../csharp/language-reference/compiler-messages/includes/note-settings-general-md.md)]  
  
 ![비디오에 링크](../../../../csharp/programming-guide/concepts/linq/media/playvideo.png "PlayVideo") 이 항목의 비디오 버전을 보려면 [Video How to: Enable XML IntelliSense in Visual Basic](http://go.microsoft.com/fwlink/?LinkId=102466)을 참조하십시오.  관련 비디오 데모를 보려면 [How Do I: Enable XML IntelliSense and Use XML Namespaces?](http://go.microsoft.com/fwlink/?LinkId=143035)를 참조하십시오.  
  
## Visual Basic에서 XML IntelliSense 사용  
 XML 파일이 있지만 이에 대한 XSD 스키마 파일이 없는 경우 SP1에서는 XML to Schema 마법사를 사용하여 XSD 스키마 파일을 만들 수 있습니다.  또한 Visual Studio XML 편집기에서 스키마 유추를 사용할 수도 있습니다.  
  
#### XML to Schema 마법사를 사용하여 XML 파일에 대한 XSD 스키마 파일을 만들려면\(SP1 필요\)  
  
1.  프로젝트의 **프로젝트** 메뉴에서 **새 항목 추가**를 클릭합니다.  
  
2.  **데이터** 또는 **공통 항목** 템플릿 범주에서 **Xml to Schema** 항목 템플릿을 선택합니다.  
  
3.  XSD 파일의 파일 이름 또는 유추된 스키마 집합이 저장되는 파일을 지정한 다음 **추가**를 클릭합니다.  
  
4.  **XML 문서에서 XML 스키마 집합 유추** 창에서 XML 스키마 집합을 유추할 하나 이상의 XML 문서를 추가합니다.  
  
    -   파일 탐색기를 사용 하 여 XML 문서를 포함 하는 텍스트 파일을 추가 하려면  **파일에서 추가**.  
  
    -   HTTP 주소에서 XML 문서를 추가하려면 **웹에서 추가**를 클릭합니다.  
  
    -   XML 문서의 내용을 마법사에 복사하거나 입력하려면 **XML 입력 또는 붙여넣기**를 클릭합니다.  
  
5.  XML 스키마 집합을 유추할 XML 문서 소스를 모두 지정했으면 **확인**을 클릭하여 XML 스키마 집합을 유추합니다.  스키마 집합은 프로젝트 폴더에 하나 이상의 XSD 파일로 저장됩니다.  스키마의 각 XML 네임스페이스에 대해 파일이 만들어집니다.  
  
#### Visual Studio XML 편집기에서 스키마 유추를 사용하여 XML 파일에 대한 XSD 스키마 파일을 만들려면  
  
1.  Visual Studio XML 디자이너에서 XML 파일을 편집합니다.  
  
2.  커서가 XML 파일 안에 있으면 **XML** 메뉴가 나타납니다.  **XML** 메뉴에서 **스키마 만들기**를 클릭합니다.  XML 파일에서 유추된 XSD 스키마로부터 XSD 파일이 만들어집니다.  
  
3.  XSD 스키마 파일을 저장합니다.  
  
    > [!NOTE]
    >  동일한 스키마가 유추되어야 하는 여러 XML 문서에서 서로 다른 XSD 스키마가 유추될 수 있습니다.  특정 요소 및 특성이 한 XML 파일에서는 발견되고 다른 파일에서는 발견되지 않거나 요소가 서로 다른 순서로 포함되어 있는 경우 등에 이러한 현상이 발생할 수 있습니다.  XSD 스키마 유추를 사용할 때는 유추된 XSD 스키마가 완전하고 정확한지 검토해야 합니다.  
  
#### XSD 스키마 파일을 포함하려면  
  
-   기본적으로 Visual Basic 프로젝트에서 XSD 파일은 볼 수 없습니다.  XSD 파일이 프로젝트의 폴더에 이미 포함되어 있으면 **솔루션 탐색기**에서 **모든 파일 표시** 단추를 클릭하십시오.  **솔루션 탐색기**에서 XSD 파일을 찾아서 마우스 오른쪽 단추로 클릭하고 **프로젝트에 파일 포함**을 클릭합니다.  
  
-   XSD 파일이 아직 프로젝트에 포함되어 있지 않은 경우에는 **솔루션 탐색기**에서 XSD 파일을 저장할 폴더를 마우스 오른쪽 단추로 클릭하고 **추가**를 가리킨 다음 **기존 항목**을 클릭합니다.  XSD 파일을 찾은 다음 **추가**를 클릭합니다.  
  
#### XML 네임스페이스를 코드 파일로 가져오려면  
  
1.  XSD 스키마에서 대상 네임스페이스를 식별합니다.  
  
2.  다음 예제와 같이 코드 파일의 시작 부분에 대상 XML 네임스페이스에 대한 `Imports` 문을 추가합니다.  
  
     [!code-vb[VbXMLSamples#1](../../../../visual-basic/language-reference/operators/codesnippet/visualbasic/how-to-enable-xml-intell_1.vb)]  
  
     XML 네임스페이스를 기본 네임스페이스, 즉 네임스페이스 접두사가 없는 XML 요소 및 특성에 적용되는 네임스페이스로 가져오려면 대상 기본 XML 네임스페이스에 대한 `Imports` 문을 추가합니다.  네임스페이스 접두사는 지정하지 마십시오.  다음은 `Imports` 문의 예입니다.  
  
     [!code-vb[VbXmlSamples#50](../../../../visual-basic/language-reference/operators/codesnippet/visualbasic/how-to-enable-xml-intell_2.vb)]  
  
#### 프로젝트의 모든 파일에 대해 XML 네임스페이스를 가져오려면  
  
1.  코드 파일로 가져온 XML 네임스페이스는 해당 코드 파일에만 적용됩니다.  프로젝트의 모든 코드 파일에 적용되는 XML 네임스페이스를 가져오려면 **솔루션 탐색기**에서 **My Project**를 두 번 클릭하여 프로젝트 디자이너를 엽니다.  
  
2.  **참조** 탭의 **가져온 네임스페이스** 상자에 대상 XML 네임스페이스를 전체 XML 네임스페이스 선언의 형식으로 입력합니다\(예: `<xmlns: ns="http://sampleNamespace">`\).  대상 XML 네임스페이스가 네임스페이스 접두사를 지정하지 않는 경우에는 이 네임스페이스가 프로젝트의 기본 XML 네임스페이스가 됩니다.  
  
3.  **사용자 가져오기 추가**를 클릭합니다.  
  
## 참고 항목  
 [Imports Statement \(XML Namespace\)](../../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)   
 [참조 페이지, 프로젝트 디자이너\(Visual Basic\)](/visual-studio/ide/reference/references-page-project-designer-visual-basic)   
 [XML IntelliSense in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/xml-intellisense.md)