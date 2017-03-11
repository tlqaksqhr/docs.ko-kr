---
title: "XML to Schema Wizard (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.XmlToSchemaWizard"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "XML IntelliSense [Visual Basic]"
  - "XML [Visual Basic], IntelliSense"
  - "IntelliSense [Visual Basic], XML"
  - "XML schemas, creating"
ms.assetid: 98c495ba-8f37-4517-a0db-aa738611ab76
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# XML to Schema Wizard (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

XML to Schema 마법사를 사용하면 하나 이상의 XML 문서에서 유추한 XML 스키마 집합을 만들고 이 집합을 프로젝트에 포함할 수 있습니다.  텍스트 파일 형식의 XML 문서, HTTP 인터넷 주소의 XML 또는 XML to Schema 마법사에 입력하거나 붙여넣은 XML을 임의로 조합하여 사용할 수 있습니다.  
  
 Visual Basic에서 XML 스키마는 XML 속성에 대한 IntelliSense를 제공하기 위해 사용됩니다.  자세한 내용은 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md) 및 [XML IntelliSense in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/xml-intellisense.md)을 참조하십시오.  
  
> [!NOTE]
>  XML to Schema 마법사를 실행하기 전에 마법사에서 이전에 생성한 기존 XSD 파일을 프로젝트에서 제거하는 것이 좋습니다.  기존 스키마 집합과 일치하는 XML 스키마 집합을 유추하는 경우 충돌이 발생할 수 있으며 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서 XML 속성에 대한 IntelliSense를 제공할 수 없습니다.  
  
 XML to Schema 마법사에서는 <xref:System.Xml.Schema.XmlSchemaInference> 클래스를 사용하여 제공된 XML에 대한 스키마를 만듭니다.  따라서 스키마 집합에 대해 여러 스키마 파일이 만들어질 수 있습니다.  제공된 XML의 각 네임스페이스에 대해 XSD\(Extensible Schema Definition\) 파일이 만들어집니다.  자세한 내용은 <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A> 메서드를 참조하십시오.  
  
 XML to Schema 마법사에 액세스하려면 **프로젝트** 메뉴에서 **새 항목 추가**를 클릭하고 **데이터** 또는 **공통 항목** 템플릿 그룹에서 **Xml to Schema** 템플릿을 추가합니다.  XML 스키마 집합을 유추할 XML 문서 소스를 모두 포함했으면 **확인**을 클릭하여 유추한 XML 스키마 집합을 만듭니다.  
  
 **소스 형식**  
 이 열에는 XML 문서 소스의 형식 즉, **파일**, **URL** 또는 **XML**이 표시됩니다.  
  
 **XML 문서 위치**  
 이 열에는 XML 문서의 경로가 표시됩니다.  입력하거나 붙여넣은 XML 문서의 경우 XML 문서의 내용이 표시됩니다.  
  
 **파일에서 추가**  
 파일 탐색기를 사용 하 여 XML 문서 파일을 추가 하려면이 단추를 클릭 합니다.  
  
 **웹에서 추가**  
 XML 문서의 HTTP 주소를 제공하려면 이 단추를 클릭합니다.  
  
 **XML 입력 또는 붙여넣기**  
 대화 상자에 XML 문서를 입력하거나 붙여넣으려면 이 단추를 클릭합니다.  
  
## 참고 항목  
 <xref:System.Xml.Schema.XmlSchemaInference>   
 [XML IntelliSense in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/xml-intellisense.md)