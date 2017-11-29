---
title: "방법: Visual Basic에서 문자열 안의 문자에 액세스"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- strings [Visual Basic], accessing characters
- characters [Visual Basic], accessing in strings
ms.assetid: 02c5206c-ffab-494d-b648-3b2ea358dc34
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 54d604fc08dd97e0e31f9bcec148431374e8ef8f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-access-characters-in-strings-in-visual-basic"></a><span data-ttu-id="fe7b4-102">방법: Visual Basic에서 문자열 안의 문자에 액세스</span><span class="sxs-lookup"><span data-stu-id="fe7b4-102">How to: Access Characters in Strings in Visual Basic</span></span>
<span data-ttu-id="fe7b4-103">사용 하는 방법을 보여 주는이 예제는 <xref:System.String.Chars%2A> 문자는 문자열에 지정된 된 위치에 액세스 하려면 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="fe7b4-103">This example demonstrates how to use the <xref:System.String.Chars%2A> property to access the character at the specified location in a string.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fe7b4-104">예제</span><span class="sxs-lookup"><span data-stu-id="fe7b4-104">Example</span></span>  
 <span data-ttu-id="fe7b4-105">경우에 따라 문자 및 문자열에서 문자열 내에서 해당 문자의 위치에 대 한 데이터가 있어야 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe7b4-105">Sometimes it is useful to have data about the characters in your string and the positions of those characters within your string.</span></span> <span data-ttu-id="fe7b4-106">문자의 배열 문자열 생각할 수 있습니다 (`Char` 인스턴스);를 통해 해당 문자의 인덱스를 참조 하 여 특정 문자를 검색할 수 있습니다는 <xref:System.String.Chars%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="fe7b4-106">You can think of a string as an array of characters (`Char` instances); you can retrieve a particular character by referencing the index of that character through the <xref:System.String.Chars%2A> property.</span></span>  
  
 [!code-vb[VbVbalrStrings#49](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-access-characters-in-strings_1.vb)]  
  
 <span data-ttu-id="fe7b4-107">`index` 의 매개 변수는 <xref:System.String.Chars%2A> 속성은 0부터 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe7b4-107">The `index` parameter of the <xref:System.String.Chars%2A> property is zero-based.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="fe7b4-108">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="fe7b4-108">Robust Programming</span></span>  
 <span data-ttu-id="fe7b4-109"><xref:System.String.Chars%2A> 속성이 지정된 된 위치에 문자를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe7b4-109">The <xref:System.String.Chars%2A> property returns the character at the specified position.</span></span> <span data-ttu-id="fe7b4-110">그러나 일부 유니코드 문자 1 자로 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe7b4-110">However, some Unicode characters can be represented by more than one character.</span></span> <span data-ttu-id="fe7b4-111">유니코드 문자를 사용 하는 방법에 대 한 자세한 내용은 참조 하십시오. [하는 방법: 배열의 문자를 문자열로 변환](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-a-string-to-an-array-of-characters.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fe7b4-111">For more information on how to work with Unicode characters, see [How to: Convert a String to an Array of Characters](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-a-string-to-an-array-of-characters.md).</span></span>  
  
 <span data-ttu-id="fe7b4-112"><xref:System.String.Chars%2A> 속성은 <xref:System.IndexOutOfRangeException> 예외 경우는 `index` 매개 변수는 문자열의 길이 보다 크거나 그가 0 보다 작은 경우</span><span class="sxs-lookup"><span data-stu-id="fe7b4-112">The <xref:System.String.Chars%2A> property throws an <xref:System.IndexOutOfRangeException> exception if the `index` parameter is greater than or equal to the length of the string, or if it is less than zero</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe7b4-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fe7b4-113">See Also</span></span>  
 <xref:System.String.Chars%2A>  
 [<span data-ttu-id="fe7b4-114">방법: 문자열을 문자 배열로 변환</span><span class="sxs-lookup"><span data-stu-id="fe7b4-114">How to: Convert a String to an Array of Characters</span></span>](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-a-string-to-an-array-of-characters.md)  
 [<span data-ttu-id="fe7b4-115">Visual Basic에서 문자열 및 기타 데이터 형식 사이에 변환</span><span class="sxs-lookup"><span data-stu-id="fe7b4-115">Converting Between Strings and Other Data Types in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/converting-between-strings-and-other-data-types.md)  
 [<span data-ttu-id="fe7b4-116">문자열</span><span class="sxs-lookup"><span data-stu-id="fe7b4-116">Strings</span></span>](../../../../visual-basic/programming-guide/language-features/strings/index.md)
