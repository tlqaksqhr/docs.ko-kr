---
title: "Parsing Text Files with the TextFieldParser Object (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
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
  - "TextFieldParser object, using"
  - "I/O [Visual Basic], parsing files"
  - "files, parsing"
ms.assetid: fc31d6e6-af0c-403f-8a00-d556b2c57567
caps.latest.revision: 20
caps.handback.revision: 20
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Parsing Text Files with the TextFieldParser Object (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

`TextFieldParser` 개체를 사용하면 긴 파일 또는 레거시 데이터베이스 정보 등과 같이 구분된 너비의 텍스트 열로 구성된 매우 큰 파일을 구문 분석하고 처리할 수 있습니다.  `TextFieldParser`를 사용한 텍스트 파일 구문 분석은 텍스트 파일을 반복하는 것과 비슷한 반면, 구분 분석 메서드를 사용하여 텍스트의 필드를 추출하는 것은 구분된 문자열의 토큰화에 사용되는 문자열 조작 메서드와 비슷합니다.  
  
## 서로 다른 형식의 텍스트 파일 구문 분석  
 텍스트 파일에는 쉼표 또는 탭 공백 등과 같은 문자로 구분된 다양한 너비의 필드가 있을 수 있습니다.  이 경우에는 `SetDelimiters` 메서드를 사용하여 탭으로 구분된 텍스트 파일을 정의하는 다음 예제에서처럼 `TextFieldType`과 구분 기호를 정의합니다.  
  
 [!CODE [VbVbalrTextFieldParser#21](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrTextFieldParser#21)]  
  
 필드 너비가 고정된 텍스트 파일도 있을 수 있습니다.  이러한 경우에는 다음 예제처럼 `TextFieldType`을 `FixedWidth`로 정의하고 각 필드의 너비를 정의해야 합니다.  이 예제에서는 `SetFieldWidths` 메서드를 사용하여 텍스트의 열을 정의합니다. 즉, 첫 번째 열의 너비는 5자, 두 번째 열은 10자, 세 번째 열은 11자 그리고 네 번째 열은 가변 너비로 정의합니다.  
  
 [!CODE [VbVbalrTextFieldParser#22](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrTextFieldParser#22)]  
  
 형식이 정의되면 파일을 순환하며 `ReadFields` 메서드를 사용하여 각 줄을 차례로 처리할 수 있습니다.  
  
 필드가 지정된 형식과 일치하지 않으면 <xref:Microsoft.VisualBasic.FileIO.MalformedLineException> 예외가 throw됩니다.  이러한 예외가 throw되면 예외를 발생시킨 텍스트와 해당 텍스트의 줄 번호가 `ErrorLine` 및 `ErrorLineNumber` 속성에 저장됩니다.  
  
## 여러 형식이 포함된 파일 구문 분석  
 `TextFieldParser` 개체의 `PeekChars` 메서드를 사용하면 각 필드를 읽기 전에 해당 필드를 확인할 수 있기 때문에 필드에 대해 여러 형식을 정의하고 그에 맞게 처리할 수 있습니다.  자세한 내용은 [How to: Read From Text Files with Multiple Formats](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files-with-multiple-formats.md)를 참조하십시오.  
  
## 참고 항목  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFieldParser%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.PeekChars%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ReadFields%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.CommentTokens%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.Delimiters%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ErrorLine%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ErrorLineNumber%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.FieldWidths%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.HasFieldsEnclosedInQuotes%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.LineNumber%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.TextFieldType%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.TrimWhiteSpace%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.SetDelimiters%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.SetFieldWidths%2A>   
 [예외 문제 해결: Microsoft.VisualBasic.FileIO.TextFieldParser.MalformedLineException](../Topic/Troubleshooting%20Exceptions:%20Microsoft.VisualBasic.FileIO.TextFieldParser.MalformedLineException.md)