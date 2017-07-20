---
title: "TextFieldParser 개체를 사용하여 텍스트 파일 구문 분석(Visual Basic) | Microsoft 문서"
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
- TextFieldParser object, using
- I/O [Visual Basic], parsing files
- files, parsing
ms.assetid: fc31d6e6-af0c-403f-8a00-d556b2c57567
caps.latest.revision: 20
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
ms.translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: a686058d97d499b3baf32b20b56834162200f346
ms.contentlocale: ko-kr
ms.lasthandoff: 05/22/2017

---
# <a name="parsing-text-files-with-the-textfieldparser-object-visual-basic"></a>TextFieldParser 개체를 사용하여 텍스트 파일 구문 분석(Visual Basic)
`TextFieldParser` 개체를 사용하면 로그 파일 또는 레거시 데이터베이스 정보와 같은 구분된 너비 열로 구성된 매우 큰 파일을 구문 분석하고 처리할 수 있습니다. `TextFieldParser`를 사용한 텍스트 파일 구문 분석은 텍스트 파일 반복과 비슷하고, 텍스트의 필드를 추출하는 구문 분석 메서드는 구분된 문자열을 토큰화하는 데 사용되는 문자열 조작 메서드와 비슷합니다.  
  
## <a name="parsing-different-types-of-text-files"></a>다양한 형식의 텍스트 파일 구문 분석  
 텍스트 파일에는 쉼표 또는 탭 공백과 같은 문자로 구분된 다양한 너비의 필드가 있을 수 있습니다. `SetDelimiters` 메서드를 사용하여 탭으로 구분된 텍스트 파일을 정의하는 다음 예제와 같이 `TextFieldType` 및 구분 기호를 정의합니다.  
  
 [!code-vb[VbVbalrTextFieldParser#21](../../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/parsing-text-files-with-the-textfieldparser-object_1.vb)]  
  
 기타 텍스트 파일에는 고정된 필드 너비가 있을 수 있습니다. 이러한 경우에는 `TextFieldType`을 `FixedWidth`로 정의하고 다음 예제와 같이 각 필드의 너비를 정의해야 합니다. 이 예제에서는 `SetFieldWidths` 메서드를 사용하여 텍스트 열을 정의합니다. 첫 번째 열은 너비가 5자이고, 두 번째 열은 10자, 세 번째 열은 11자, 네 번째 열은 가변 너비입니다.  
  
 [!code-vb[VbVbalrTextFieldParser#22](../../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/parsing-text-files-with-the-textfieldparser-object_2.vb)]  
  
 형식이 정의되고 나면 `ReadFields` 메서드로 각 줄을 차례로 처리하여 파일을 반복할 수 있습니다.  
  
 필드가 지정된 형식과 일치하지 않으면 <xref:Microsoft.VisualBasic.FileIO.MalformedLineException> 예외가 throw됩니다. 이러한 예외가 throw되는 경우 `ErrorLine` 및 `ErrorLineNumber` 속성에 예외를 발생시키는 텍스트와 해당 텍스트의 줄 번호가 포함됩니다.  
  
## <a name="parsing-files-with-multiple-formats"></a>여러 형식의 파일 구문 분석  
 `TextFieldParser` 개체의 `PeekChars` 메서드를 사용하면 각 필드를 읽기 전에 확인하여 필드에 대한 여러 형식을 정의하고 그에 따라 반응할 수 있습니다. 자세한 내용은 [방법: 여러 형식의 텍스트 파일에서 읽기](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files-with-multiple-formats.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
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
