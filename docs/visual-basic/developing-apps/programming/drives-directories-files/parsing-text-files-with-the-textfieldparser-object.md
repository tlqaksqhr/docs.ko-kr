---
title: TextFieldParser 개체를 사용하여 텍스트 파일 구문 분석(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- TextFieldParser object, using
- I/O [Visual Basic], parsing files
- files [Visual Basic], parsing
ms.assetid: fc31d6e6-af0c-403f-8a00-d556b2c57567
ms.openlocfilehash: 520121ba549532c5ce73810347025949eee5a077
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33587308"
---
# <a name="parsing-text-files-with-the-textfieldparser-object-visual-basic"></a><span data-ttu-id="246ca-102">TextFieldParser 개체를 사용하여 텍스트 파일 구문 분석(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="246ca-102">Parsing text files with the TextFieldParser object (Visual Basic)</span></span>
<span data-ttu-id="246ca-103">`TextFieldParser` 개체를 사용하면 로그 파일 또는 레거시 데이터베이스 정보와 같은 구분된 너비 열로 구성된 매우 큰 파일을 구문 분석하고 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="246ca-103">The `TextFieldParser` object allows you to parse and process very large file that are structured as delimited-width columns of text, such as log files or legacy database information.</span></span> <span data-ttu-id="246ca-104">`TextFieldParser`를 사용한 텍스트 파일 구문 분석은 텍스트 파일 반복과 비슷하고, 텍스트의 필드를 추출하는 구문 분석 메서드는 구분된 문자열을 토큰화하는 데 사용되는 문자열 조작 메서드와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="246ca-104">Parsing a text file with `TextFieldParser` is similar to iterating over a text file, while the parse method to extract fields of text is similar to string manipulation methods used to tokenize delimited strings.</span></span>  
  
## <a name="parsing-different-types-of-text-files"></a><span data-ttu-id="246ca-105">다양한 형식의 텍스트 파일 구문 분석</span><span class="sxs-lookup"><span data-stu-id="246ca-105">Parsing different types of text files</span></span>  
 <span data-ttu-id="246ca-106">텍스트 파일에는 쉼표 또는 탭 공백과 같은 문자로 구분된 다양한 너비의 필드가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="246ca-106">Text files may have fields of various width, delimited by a character such as a comma or a tab space.</span></span> <span data-ttu-id="246ca-107">`SetDelimiters` 메서드를 사용하여 탭으로 구분된 텍스트 파일을 정의하는 다음 예제와 같이 `TextFieldType` 및 구분 기호를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="246ca-107">Define `TextFieldType` and the delimiter, as in the following example, which uses the `SetDelimiters` method to define a tab-delimited text file:</span></span>  
  
 [!code-vb[VbVbalrTextFieldParser#21](../../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/parsing-text-files-with-the-textfieldparser-object_1.vb)]  
  
 <span data-ttu-id="246ca-108">기타 텍스트 파일에는 고정된 필드 너비가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="246ca-108">Other text files may have field widths that are fixed.</span></span> <span data-ttu-id="246ca-109">이러한 경우에는 `TextFieldType`을 `FixedWidth`로 정의하고 다음 예제와 같이 각 필드의 너비를 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="246ca-109">In such cases, you need to define the `TextFieldType` as `FixedWidth` and define the widths of each field, as in the following example.</span></span> <span data-ttu-id="246ca-110">이 예제에서는 `SetFieldWidths` 메서드를 사용하여 텍스트 열을 정의합니다. 첫 번째 열은 너비가 5자이고, 두 번째 열은 10자, 세 번째 열은 11자, 네 번째 열은 가변 너비입니다.</span><span class="sxs-lookup"><span data-stu-id="246ca-110">This example uses the `SetFieldWidths` method to define the columns of text: the first column is 5 characters wide, the second is 10, the third is 11, and the fourth is of variable width.</span></span>  
  
 [!code-vb[VbVbalrTextFieldParser#22](../../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/parsing-text-files-with-the-textfieldparser-object_2.vb)]  
  
 <span data-ttu-id="246ca-111">형식이 정의되고 나면 `ReadFields` 메서드로 각 줄을 차례로 처리하여 파일을 반복할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="246ca-111">Once the format is defined, you can loop through the file, using the `ReadFields` method to process each line in turn.</span></span>  
  
 <span data-ttu-id="246ca-112">필드가 지정된 형식과 일치하지 않으면 <xref:Microsoft.VisualBasic.FileIO.MalformedLineException> 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="246ca-112">If a field does not match the specified format, a <xref:Microsoft.VisualBasic.FileIO.MalformedLineException> exception is thrown.</span></span> <span data-ttu-id="246ca-113">이러한 예외가 throw되는 경우 `ErrorLine` 및 `ErrorLineNumber` 속성에 예외를 발생시키는 텍스트와 해당 텍스트의 줄 번호가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="246ca-113">When such exceptions are thrown, the `ErrorLine` and `ErrorLineNumber` properties hold the text causing the exception and the line number of that text.</span></span>  
  
## <a name="parsing-files-with-multiple-formats"></a><span data-ttu-id="246ca-114">여러 형식의 파일 구문 분석</span><span class="sxs-lookup"><span data-stu-id="246ca-114">Parsing files with multiple formats</span></span>  
 <span data-ttu-id="246ca-115">`TextFieldParser` 개체의 `PeekChars` 메서드를 사용하면 각 필드를 읽기 전에 확인하여 필드에 대한 여러 형식을 정의하고 그에 따라 반응할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="246ca-115">The `PeekChars` method of the `TextFieldParser` object can be used to check each field before reading it, allowing you to define multiple formats for the fields and react accordingly.</span></span> <span data-ttu-id="246ca-116">자세한 내용은 [방법: 여러 형식의 텍스트 파일에서 읽기](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files-with-multiple-formats.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="246ca-116">For more information, see [How to: Read From Text Files with Multiple Formats](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files-with-multiple-formats.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="246ca-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="246ca-117">See also</span></span>  
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
