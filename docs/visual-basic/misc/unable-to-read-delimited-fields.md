---
title: "EscapeQuotes가 True로 설정되어 있으면 큰따옴표가 올바른 구분 기호가 아니므로 구분된 필드를 읽을 수 없습니다."
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrTextFieldParser_IllegalDelimiter
ms.assetid: ab8a0c3a-b89c-4617-9e31-7e81f5dca433
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3644165d0c25189f29f3f878a17b0d9bf4e2623b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="unable-to-read-delimited-fields-because-a-double-quote-is-not-a-legal-delimiter-when-escapequotes-is-set-to-true"></a><span data-ttu-id="05f9a-102">EscapeQuotes가 True로 설정되어 있으면 큰따옴표가 올바른 구분 기호가 아니므로 구분된 필드를 읽을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="05f9a-102">Unable to read delimited fields because a double quote is not a legal delimiter when EscapeQuotes is set to True</span></span>
<span data-ttu-id="05f9a-103">`TextFieldParser` 는 따옴표(")가 구분 기호로 제공되고 `EscapeQuotes` 가 `True`로 설정되므로 파일에서 읽을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="05f9a-103">The `TextFieldParser` cannot read from the file because a quotation mark (") has been supplied as the delimiter and `EscapeQuotes` is set to `True`.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="05f9a-104">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="05f9a-104">To correct this error</span></span>  
  
-   <span data-ttu-id="05f9a-105">`EscapeQuotes` 를 `False`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="05f9a-105">Set `EscapeQuotes` to `False`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05f9a-106">참고 항목</span><span class="sxs-lookup"><span data-stu-id="05f9a-106">See Also</span></span>  
 [<span data-ttu-id="05f9a-107">TextFieldParser.SetDelimiters 메서드</span><span class="sxs-lookup"><span data-stu-id="05f9a-107">TextFieldParser.SetDelimiters Method</span></span>](http://msdn.microsoft.com/en-us/21fa40ec-5866-4d0e-9fd9-c708a190dcc9)  
 [<span data-ttu-id="05f9a-108">TextFieldParser.Delimiters 속성</span><span class="sxs-lookup"><span data-stu-id="05f9a-108">TextFieldParser.Delimiters Property</span></span>](http://msdn.microsoft.com/en-us/4eb18f4d-3011-40a9-b668-be93eed0444f)  
 [<span data-ttu-id="05f9a-109">방법: 쉼표로 구분된 텍스트 파일에서 읽기</span><span class="sxs-lookup"><span data-stu-id="05f9a-109">How to: Read From Comma-Delimited Text Files</span></span>](../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-comma-delimited-text-files.md)  
 [<span data-ttu-id="05f9a-110">TextFieldParser 개체</span><span class="sxs-lookup"><span data-stu-id="05f9a-110">TextFieldParser Object</span></span>](../../visual-basic/language-reference/objects/textfieldparser-object.md)
