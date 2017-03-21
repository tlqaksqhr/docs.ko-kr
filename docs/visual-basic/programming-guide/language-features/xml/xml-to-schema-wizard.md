---
title: "XML to Schema 마법사 (Visual Basic) | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vb.XmlToSchemaWizard
dev_langs:
- VB
helpviewer_keywords:
- XML IntelliSense [Visual Basic]
- XML [Visual Basic], IntelliSense
- IntelliSense [Visual Basic], XML
- XML schemas, creating
ms.assetid: 98c495ba-8f37-4517-a0db-aa738611ab76
caps.latest.revision: 16
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
ms.openlocfilehash: d0c9c0247f3d9934ef973c7322cb098f9b445a5a
ms.lasthandoff: 03/13/2017

---
# <a name="xml-to-schema-wizard-visual-basic"></a>XML to Schema 마법사(Visual Basic)
XML to Schema 마법사를 사용 하 여 하나 이상의 XML 문서에서 유추 하는 XML 스키마 집합을 만들고 프로젝트를 포함 합니다. HTTP 인터넷 주소에서 XML 또는 형식화 하거나 XML to Schema 마법사에 붙여 넣은 XML 텍스트 파일의 형태로 XML 문서의 모든 조합을 사용할 수 있습니다.  
  
 XML 스키마는 Visual Basic의 XML 속성에 대 한 IntelliSense를 제공 하는 데 사용 됩니다. 자세한 내용은 참조 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md) 및 [Visual Basic의 XML IntelliSense](../../../../visual-basic/programming-guide/language-features/xml/xml-intellisense.md)합니다.  
  
> [!NOTE]
>  XML to Schema 마법사를 실행 하기 전에 마법사에서 이전에 생성 된 프로젝트에서 기존 XSD 파일을 제거 하는 것이 좋습니다. 기존 스키마 집합에 일치 하는 XML 스키마 집합을 유추 하려고 하면 충돌이 발생 하 고 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] XML 속성에 대 한 IntelliSense를 제공할 수 없습니다.  
  
 XML to Schema 마법사를 사용 하 여는 <xref:System.Xml.Schema.XmlSchemaInference>클래스를 지정 된 XML에 대 한 스키마를 만듭니다.</xref:System.Xml.Schema.XmlSchemaInference> 결과적으로, 스키마 집합에 대 한 여러 스키마 파일을 만들 수 있습니다. 지정 된 XML의 각 XML 네임 스페이스에 대 한 확장 가능한 스키마 정의 (XSD) 파일 생성 됩니다. 자세한 내용은 참조는 <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A>메서드.</xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A>  
  
 XML to Schema 마법사에 액세스 하려면 **새 항목 추가** 에 **프로젝트** 메뉴 추가 **XML 스키마를** 템플릿 중 하나에서 **데이터** 또는 **공통 항목** 템플릿 그룹입니다. 모든 XML 문서 소스에서 XML 스키마 집합을 유추를 포함 한 후 클릭 **확인** 유추 된 스키마를 만들려면 다음을 설정 합니다.  
  
 **원본 유형**  
 이 열에 XML 문서 소스의 유형을 표시: **파일**, **URL**, 또는 **XML**합니다.  
  
 **XML 문서 위치**  
 이 열은 XML 문서 경로 표시 합니다. 입력 하거나 붙여넣은 XML 문서에 대 한 XML 문서의 내용을 표시합니다.  
  
 **파일에서 추가**  
 파일 탐색기를 사용 하 여 XML 문서 파일을 추가 하려면이 단추를 클릭 합니다.  
  
 **웹에서 추가**  
 XML 문서의 HTTP 주소를 제공 하려면이 단추를 클릭 합니다.  
  
 **입력 하거나 XML을 붙여 넣습니다**  
 입력 하거나 대화 상자에는 XML 문서를 붙여 넣습니다.이 단추를 클릭 합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Xml.Schema.XmlSchemaInference></xref:System.Xml.Schema.XmlSchemaInference>   
 [Visual Basic의 XML IntelliSense](../../../../visual-basic/programming-guide/language-features/xml/xml-intellisense.md)
