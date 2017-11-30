---
title: "방법: Visual Basic에서 문자열을 문자 배열로 변환"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- character arrays [Visual Basic], converting strings
- arrays [Visual Basic], converting strings to
- examples [Visual Basic], string conversion
- strings [Visual Basic], converting to arrays
- string conversion [Visual Basic], arrays
ms.assetid: 1b54b686-ab29-413b-adce-6bd5422376eb
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 59d0da52c8f78b93c76325e6242156c106deeaf1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-convert-a-string-to-an-array-of-characters-in-visual-basic"></a><span data-ttu-id="e92e6-102">방법: Visual Basic에서 문자열을 문자 배열로 변환</span><span class="sxs-lookup"><span data-stu-id="e92e6-102">How to: Convert a String to an Array of Characters in Visual Basic</span></span>
<span data-ttu-id="e92e6-103">경우에 따라 문자열을 구문 분석 하는 경우 처럼 문자열 내에서 해당 문자의 위치 및 문자열에서 문자에 대 한 데이터가 있어야 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e92e6-103">Sometimes it is useful to have data about the characters in your string and the positions of those characters within your string, such as when you are parsing a string.</span></span> <span data-ttu-id="e92e6-104">문자열의 호출 하 여 문자열에는 문자 배열을 가져올 수는 방법을 보여 주는이 예제 <xref:System.String.ToCharArray%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="e92e6-104">This example shows how you can get an array of the characters in a string by calling the string's <xref:System.String.ToCharArray%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e92e6-105">예제</span><span class="sxs-lookup"><span data-stu-id="e92e6-105">Example</span></span>  
 <span data-ttu-id="e92e6-106">에 문자열을 분할 하는 방법을 보여 주는이 예제는 `Char` 배열 및 문자열로 문자열을 분할 하는 방법을 `String` 배열 유니코드 텍스트 문자입니다.</span><span class="sxs-lookup"><span data-stu-id="e92e6-106">This example demonstrates how to split a string into a `Char` array, and how to split a string into a `String` array of its Unicode text characters.</span></span> <span data-ttu-id="e92e6-107">이 차이 대 한 이유는 두 개 이상의 유니코드 텍스트 문자를 구성할 수는 `Char` 문자 (예: 서로게이트 쌍 또는 조합 문자 시퀀스).</span><span class="sxs-lookup"><span data-stu-id="e92e6-107">The reason for this distinction is that Unicode text characters can be composed of two or more `Char` characters (such as a surrogate pair or a combining character sequence).</span></span> <span data-ttu-id="e92e6-108">자세한 내용은 참조 <xref:System.Globalization.TextElementEnumerator> "에서 유니코드 표준을" http://www.unicode.org 및 합니다.</span><span class="sxs-lookup"><span data-stu-id="e92e6-108">For more information, see <xref:System.Globalization.TextElementEnumerator> and "The Unicode Standard" at http://www.unicode.org.</span></span>  
  
 [!code-vb[VbVbalrStrings#75](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-convert-a-string-to-an-array-of-characters_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="e92e6-109">예제</span><span class="sxs-lookup"><span data-stu-id="e92e6-109">Example</span></span>  
 <span data-ttu-id="e92e6-110">유니코드 텍스트 문자를 문자열로 분할 하는 것이 어려워집니다 하지만이 작업은 문자열의 시각적 표시에 대 한 정보가 필요한 경우에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="e92e6-110">It is more difficult to split a string into its Unicode text characters, but this is necessary if you need information about the visual representation of a string.</span></span> <span data-ttu-id="e92e6-111">사용 하 여이 예제는 <xref:System.Globalization.StringInfo.SubstringByTextElements%2A> 메서드 문자열을 구성 하는 유니코드 텍스트 문자에 대 한 정보를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e92e6-111">This example uses the <xref:System.Globalization.StringInfo.SubstringByTextElements%2A> method to get information about the Unicode text characters that make up a string.</span></span>  
  
 [!code-vb[VbVbalrStrings#76](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-convert-a-string-to-an-array-of-characters_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="e92e6-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e92e6-112">See Also</span></span>  
 <xref:System.String.Chars%2A>  
 <xref:System.Globalization.StringInfo?displayProperty=nameWithType>  
 [<span data-ttu-id="e92e6-113">방법: 문자열 안의 문자에 액세스</span><span class="sxs-lookup"><span data-stu-id="e92e6-113">How to: Access Characters in Strings</span></span>](../../../../visual-basic/programming-guide/language-features/strings/how-to-access-characters-in-strings.md)  
 [<span data-ttu-id="e92e6-114">Visual Basic에서 문자열 및 기타 데이터 형식 사이에 변환</span><span class="sxs-lookup"><span data-stu-id="e92e6-114">Converting Between Strings and Other Data Types in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/converting-between-strings-and-other-data-types.md)  
 [<span data-ttu-id="e92e6-115">문자열</span><span class="sxs-lookup"><span data-stu-id="e92e6-115">Strings</span></span>](../../../../visual-basic/programming-guide/language-features/strings/index.md)
