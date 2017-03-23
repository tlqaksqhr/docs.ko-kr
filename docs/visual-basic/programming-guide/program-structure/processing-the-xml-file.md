---
title: "XML 파일 (Visual Basic) 처리 | Microsoft 문서"
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
- XML comments, parsing [Visual Basic]
ms.assetid: 78a15cd0-7708-4e79-85d1-c154b7a14a8c
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
ms.openlocfilehash: 72b2832d0131adf39a37ebd9297b43fb34ea49ba
ms.lasthandoff: 03/13/2017

---
# <a name="processing-the-xml-file-visual-basic"></a>XML 파일 처리(Visual Basic)
컴파일러는 문서를 생성 하는 태그가 지정 되는 코드의 각 구문에는 ID 문자열을 생성 합니다. (코드를 태그 하는 방법에 대 한 자세한 내용은 참조 [XML 주석 태그](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md).) ID 문자열 구문을 고유 하 게 식별합니다. 해당 식별 하는 XML 파일을 처리 하는 프로그램 ID 문자열을 사용 하 여 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] 메타 데이터/리플렉션 항목입니다.  
  
 XML 파일의 코드, 계층적 나타내지는 않습니다. 각 요소에 대해 생성된 된 ID로 플랫 목록입니다.  
  
 ID 문자열을 생성 하는 경우 컴파일러는 다음 규칙을 준수 합니다.  
  
-   공백이 없습니다 문자열에 배치 됩니다.  
  
-   ID 문자열의 첫 번째 부분 뒤에 콜론을 단일 문자로 식별 되 고 멤버의 종류를 식별 합니다. 다음과 같은 멤버 형식은 사용 합니다.  
  
|문자|설명|  
|---|---|  
|N|namespace<br /><br /> 네임 스페이스 문서 주석을 추가할 수 없지만, 스토리에 대 한 CREF 참조를 만들 수 있습니다 지원 되는 경우.|  
|T|type: `Class`, `Module`, `Interface`, `Structure`, `Enum`,`Delegate`|  
|F|필드:`Dim`|  
|P|속성: `Property` (기본 속성 포함)|  
|M|method: `Sub`, `Function`, `Declare`,`Operator`|  
|E|이벤트:`Event`|  
|!|오류 문자열<br /><br /> 문자열의 나머지 오류에 대 한 정보를 제공합니다. [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 컴파일러 링크를 확인할 수 없는 대 한 오류 정보를 생성 합니다.|  
  
-   두 번째 부분에서 `String` 네임 스페이스의 루트에서 시작 하는 항목의 정규화 된 이름입니다. 항목, 해당 바깥쪽 형식 및 네임 스페이스의 이름은 마침표로 구분 됩니다. 항목 자체의 이름에 마침표가 있는 경우에 숫자 기호 대체 (#). 항목이 없는 직접 해당 이름에에서 숫자 기호 간주 됩니다. 정규화 된 이름에 예를 들어는 `String` 생성자 것 `System.String.#ctor`합니다.  
  
-   속성 및 메서드를 메서드에 인수가 있을 경우 괄호 안에 인수 목록을 따릅니다. 인수가 있을 경우 없습니다 괄호가 존재 합니다. 인수는 쉼표로 구분 됩니다. 각 인수의 인코딩은 그대로 따릅니다에서 인코딩하는 방법을 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] 서명 합니다.  
  
## <a name="example"></a>예제  
 다음 코드에서는 클래스에 대 한 ID 문자열 방식 하 고 해당 멤버 생성 됩니다.  
  
 [!code-vb[VbVbcnXmlDocComments #&10;](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/processing-the-xml-file_1.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [/doc](../../../visual-basic/reference/command-line-compiler/doc.md)   
 [방법: XML 문서 만들기](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)
