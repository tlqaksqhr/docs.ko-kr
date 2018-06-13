---
title: '방법: Visual Basic에서 XML 문서 만들기'
ms.date: 07/20/2015
helpviewer_keywords:
- XML comments
- XML documentation [Visual Basic], creating
ms.assetid: 27b5b06c-09b9-496a-8245-f9542d846230
ms.openlocfilehash: 7fb56da8a28367a6dcd5e28f208b4519510d7d95
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33650883"
---
# <a name="how-to-create-xml-documentation-in-visual-basic"></a>방법: Visual Basic에서 XML 문서 만들기
이 예에서는 XML 문서 주석 코드를 추가 하는 방법을 보여 줍니다.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-xml-documentation-for-a-type-or-member"></a>형식 또는 멤버에 대 한 XML 문서를 만들려면  
  
1.  에 **코드 편집기**, 설명서 만들려는 형식 또는 멤버의 줄에 커서를 놓습니다.  
  
2.  형식 `'''` (세 단일 인용 부호 제외).  
  
     형식 또는 멤버에 대 한 XML 기초가에 추가 되는 **코드 편집기**합니다.  
  
3.  해당 태그 사이 설명 정보를 추가 합니다.  
  
    > [!NOTE]
    >  XML 문서 블록에 줄을 추가 하는 경우 각 줄으로 시작 해야 `'''`합니다.  
  
4.  새 XML 문서 주석이 있는 형식 또는 멤버를 사용 하는 추가 코드를 추가 합니다.  
  
     텍스트를 표시 하는 IntelliSense는 \<요약 > 형식 또는 멤버에 대 한 태그입니다.  
  
5.  문서 주석을 포함 하는 XML 파일을 생성 하는 코드를 컴파일하십시오. 자세한 내용은 [/doc](../../../visual-basic/reference/command-line-compiler/doc.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [코드를 XML로 문서화](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)  
 [XML 주석 태그](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)  
 [/doc](../../../visual-basic/reference/command-line-compiler/doc.md)
