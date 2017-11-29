---
title: "Visual Basic의 LINQ to XML 개요"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- LINQ to XML [Visual Basic], about LINQ to XML
- LINQ [Visual Basic], LINQ to XML
ms.assetid: 01c62a79-6d58-468e-84fb-039c05947701
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: baa60939654857f40d323b6412978ed4ff918177
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="overview-of-linq-to-xml-in-visual-basic"></a>Visual Basic의 LINQ to XML 개요
[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]에 대 한 지원을 제공 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] XML 리터럴과 XML 축 속성을 통해. 이렇게 하면 XML에서 사용 하기 위한 친숙 하 고 편리한 구문을 사용 하 여 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 코드입니다. *XML 리터럴* 코드에서 직접 XML을 포함할 수 있습니다. *XML 축 속성* XML 리터럴의 특성, 하위 노드 및 자식 노드의 액세스를 사용 하면 됩니다. 자세한 내용은 참조 [XML 리터럴 개요](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-overview.md) 및 [Visual Basic의 XML에 액세스](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)합니다.  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]메모리 내 XML 프로그래밍 API를 활용 하도록 특별히 설계 [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)]합니다. 호출할 수 있지만 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] Api를 직접만 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] XML 리터럴 선언 및 XML 축 속성에 직접 액세스할 수 있습니다.  
  
> [!NOTE]
>  ASP.NET 페이지의 선언적 코드에서 XML 리터럴과 XML 축 속성이 지원 되지 않습니다. Visual Basic XML 기능을 사용 하려면 ASP.NET 응용 프로그램에서 코드 숨김 페이지에 코드를 입력 합니다.  
  
 ![비디오에 링크](../../../../visual-basic/programming-guide/language-features/xml/media/playvideo.gif "PlayVideo") 관련된 비디오 데모를 참조 하십시오. [하는 LINQ to XML 시작 하는 방법?](http://go.microsoft.com/fwlink/?LinkId=143034) 및 [어떻게 할까요? LINQ to XML 사용 하 여 Excel 스프레드시트 만들?](http://go.microsoft.com/fwlink/?LinkId=143536)합니다.  
  
## <a name="creating-xml"></a>XML 만들기  
 XML 트리를 만드는 두 가지 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]합니다. XML를 코드에 직접 리터럴 선언할 수 있습니다 또는 사용할 수는 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] Api 트리를 만듭니다. XML 트리의 최종 구조를 반영 하도록 코드를 사용 하는 두 프로세스입니다. 예를 들어 다음 코드 예제에서는 XML 요소를 만듭니다.  
  
 [!code-vb[VbXmlSamples#5](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_1.vb)]  
  
 자세한 내용은 참조 [Visual Basic에서 XML 만들기](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)합니다.  
  
## <a name="accessing-and-navigating-xml"></a>액세스 하 고 XML 탐색  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]에 액세스 하 고 XML 구조를 탐색 하기 위한 XML 축 속성을 제공 합니다. 이러한 속성을 사용 하는 XML 자식 요소 이름을 지정 하 여 XML 요소 및 특성에 액세스할 수 있습니다. 명시적으로 호출할 수 또는 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 탐색 하 고 특성과 해당 요소를 찾는 방법입니다. 예를 들어 다음 코드 예제를 사용 하 여 XML 축 속성 특성 및 XML 요소의 자식 요소를 참조 하십시오. 사용 하 여 코드 예제는 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 자식 요소를 검색 하 고 변환을 수행 하 고 XML 요소로 출력 하 여를 쿼리 합니다.  
  
 [!code-vb[VbXmlSamples#8](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_2.vb)]  
  
 자세한 내용은 참조 [Visual Basic의 XML에 액세스](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)합니다.  
  
## <a name="xml-namespaces"></a>XML 네임스페이스  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]사용 하 여 전역 XML 네임 스페이스에 대 한 별칭을 지정할 수 있습니다는 `Imports` 문. 사용 하는 방법을 보여 주는 다음 예제는 `Imports` XML 네임 스페이스를 가져올 계정:  
  
 [!code-vb[VbXMLSamples#1](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_3.vb)]  
  
 XML 축 속성에 액세스 하 고 XML 문서 및 요소에 대 한 XML 리터럴을 선언할 XML 네임 스페이스 별칭을 사용할 수 있습니다.  
  
 검색할 수 있습니다는 <xref:System.Xml.Linq.XNamespace> 를 사용 하 여 특정 네임 스페이스 접두사에 대 한 개체는 [GetXmlNamespace 연산자](../../../../visual-basic/language-reference/operators/getxmlnamespace-operator.md)합니다.  
  
 자세한 내용은 참조 [Imports 문 (XML Namespace)](../../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)합니다.  
  
### <a name="using-xml-namespaces-in-xml-literals"></a>XML 리터럴의 XML 네임 스페이스를 사용 하 여  
 만드는 방법을 보여 주는 다음 예제는 <xref:System.Xml.Linq.XElement> 전역 네임 스페이스를 사용 하는 개체 `ns`:  
  
 [!code-vb[VbXMLSamples#2](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_4.vb)]  
  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 컴파일러가 변환 XML 표기법을 사용 하 여 XML 네임 스페이스에 사용 하기 위해 해당 코드에 XML 네임 스페이스 별칭을 포함 하는 XML 리터럴을 `xmlns` 특성입니다. 를 컴파일할 때 이전 섹션의 예제 코드에서는 다음 예제와 같이 동일한 실행 코드 기본적으로 생성 합니다.  
  
 [!code-vb[VbXMLSamples#3](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_5.vb)]  
  
### <a name="using-xml-namespaces-in-xml-axis-properties"></a>XML 축 속성에 XML 네임 스페이스 사용  
 XML 리터럴 선언 된 XML 네임 스페이스 XML 축 속성에서 사용 하기 위해 사용할 수 없는 경우 그러나 XML 축 속성을 가진 전역 네임 스페이스를 사용할 수 있습니다. 로컬 요소 이름에서 XML 네임 스페이스 접두사를 구분 하려면 콜론을 사용 합니다. 예를 들면 다음과 같습니다.  
  
 [!code-vb[VbXMLSamples#4](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_6.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)  
 [Visual Basic에서 XML 만들기](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [Visual Basic에서 XML에 액세스](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)  
 [Visual Basic에서 XML 조작](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)
