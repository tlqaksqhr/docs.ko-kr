---
title: "방법: Visual Basic에서 XML 문서 만들기 | Microsoft 문서"
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
- XML comments
- XML documentation, creating
ms.assetid: 27b5b06c-09b9-496a-8245-f9542d846230
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
ms.openlocfilehash: 363a20c0fce05566b61e764d05932a9dfb779f90
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-create-xml-documentation-in-visual-basic"></a>방법: Visual Basic에서 XML 문서 만들기
이 예제에서는 XML 문서 주석 코드를 추가 하는 방법을 보여 줍니다.  
  
[!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
### <a name="to-create-xml-documentation-for-a-type-or-member"></a>형식 또는 멤버에 대 한 XML 문서를 만들려면  
  
1.  에 **코드 편집기**, 설명서를 만들려는 형식 또는 멤버 위의 줄에 커서를 놓습니다.  
  
2.  형식 `'''` (세 단일 인용 부호 제외).  
  
     형식 또는 멤버에 대 한 XML 기초가에 추가 되는 **코드 편집기**합니다.  
  
3.  적절 한 태그 사이 설명 정보를 추가 합니다.  
  
    > [!NOTE]
    >  XML 문서 블록 내에서 줄을 추가 하는 경우에 각 줄으로 시작 해야 `'''`합니다.  
  
4.  새 XML 문서 주석이 있는 형식 또는 멤버를 사용 하는 추가 코드를 추가 합니다.  
  
     텍스트를 표시 하는 IntelliSense는 \<요약 > 형식 또는 멤버에 대 한 태그입니다.  
  
5.  문서 주석을 포함 하는 XML 파일을 생성 하는 코드를 컴파일하십시오. 자세한 내용은 참조 [/doc](../../../visual-basic/reference/command-line-compiler/doc.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [XML 사용 하 여 코드 문서화](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)   
 [XML 주석 태그](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)   
 [/doc](../../../visual-basic/reference/command-line-compiler/doc.md)
