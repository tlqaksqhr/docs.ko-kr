---
title: "How to: Create XML Documentation in Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "XML comments"
  - "XML documentation, creating"
ms.assetid: 27b5b06c-09b9-496a-8245-f9542d846230
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# How to: Create XML Documentation in Visual Basic
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

이 예제에서는 코드에 XML 문서 주석을 추가하는 방법을 보여 줍니다.  
  
 [!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note-settings-general-md.md)]  
  
### 형식 또는 멤버에 대한 XML 문서를 만들려면  
  
1.  **코드 편집기**에서 문서를 만들 형식 또는 멤버에 해당하는 줄에 커서를 놓습니다.  
  
2.  `'''`\(세 개의 작은따옴표\)를 입력합니다.  
  
     형식 또는 멤버에 대한 XML 기초가 **코드 편집기**에 추가됩니다.  
  
3.  해당 태그 사이에 설명 정보를 추가합니다.  
  
    > [!NOTE]
    >  XML 문서 블록에 줄을 추가하는 경우 각 줄은 `'''`로 시작해야 합니다.  
  
4.  형식 또는 멤버를 사용하는 코드를 새 XML 문서 주석과 함께 추가합니다.  
  
     IntelliSense에서 형식 또는 멤버에 대한 \<summary\> 태그의 텍스트를 표시합니다.  
  
5.  코드를 컴파일하여 문서 주석을 포함하는 XML 파일을 생성합니다.  자세한 내용은 [\/doc](../../../visual-basic/reference/command-line-compiler/doc.md)를 참조하십시오.  
  
## 참고 항목  
 [Documenting Your Code with XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)   
 [XML Comment Tags](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)   
 [\/doc](../../../visual-basic/reference/command-line-compiler/doc.md)