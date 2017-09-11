---
title: "문자 데이터 형식 (Visual Basic) | Microsoft 문서"
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
- data types [Visual Basic], character
- String data type, character data types
- character data types [Visual Basic]
- Char data type, character data types
- data types [Visual Basic], choosing
ms.assetid: 902479ef-1679-47fc-9911-0c1c5008226c
caps.latest.revision: 23
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 3407f614d5898f4fccf04e0363ec31669661b60a
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="character-data-types-visual-basic"></a><span data-ttu-id="8725a-102">문자 데이터 형식(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8725a-102">Character Data Types (Visual Basic)</span></span>
[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="8725a-103">제공 *문자 데이터 형식* 인쇄 하거나 표시할 수 있는 문자를 처리 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8725a-103"> provides *character data types* to deal with printable and displayable characters.</span></span> <span data-ttu-id="8725a-104">유니코드 문자를 모두 처리 하는 동안 `Char` 반면은 단일 문자를 `String` 불특정 개수의 문자를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="8725a-104">While they both deal with Unicode characters, `Char` holds a single character whereas `String` contains an indefinite number of characters.</span></span>  
  
 <span data-ttu-id="8725a-105">나란히 비교를 표시 하는 테이블에 대 한는 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 데이터 형식 참조 [데이터 형식](../../../../visual-basic/language-reference/data-types/data-type-summary.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8725a-105">For a table that displays a side-by-side comparison of the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] data types, see [Data Types](../../../../visual-basic/language-reference/data-types/data-type-summary.md).</span></span>  
  
## <a name="char-type"></a><span data-ttu-id="8725a-106">Char 형식</span><span class="sxs-lookup"><span data-stu-id="8725a-106">Char Type</span></span>  
 <span data-ttu-id="8725a-107">`Char` 데이터 형식은 단일&2; 바이트 (16 비트) 유니코드 문자입니다.</span><span class="sxs-lookup"><span data-stu-id="8725a-107">The `Char` data type is a single two-byte (16-bit) Unicode character.</span></span> <span data-ttu-id="8725a-108">변수 항상 정확히 한 문자를 저장 하는 경우로 선언 `Char`합니다.</span><span class="sxs-lookup"><span data-stu-id="8725a-108">If a variable always stores exactly one character, declare it as `Char`.</span></span> <span data-ttu-id="8725a-109">예:</span><span class="sxs-lookup"><span data-stu-id="8725a-109">For example:</span></span>  
  
 <span data-ttu-id="8725a-110">[!code-vb[VbVbalrCharTypes #&1;](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/character-data-types_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="8725a-110">[!code-vb[VbVbalrCharTypes#1](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/character-data-types_1.vb)]</span></span>  
  
 <span data-ttu-id="8725a-111">가능한 각 값에는 `Char` 또는 `String` 변수가 *코드 포인트*, 또는 유니코드 문자 집합에서 문자 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="8725a-111">Each possible value in a `Char` or `String` variable is a *code point*, or character code, in the Unicode character set.</span></span> <span data-ttu-id="8725a-112">유니코드 문자는 기본 ASCII 문자 집합, 다양 한 다른 알파벳 문자, 악센트, 통화 기호, 분수, 분음 부호, 및 수학 및 공학 기호를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="8725a-112">Unicode characters include the basic ASCII character set, various other alphabet letters, accents, currency symbols, fractions, diacritics, and mathematical and technical symbols.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8725a-113">유니코드 문자 집합 코드 포인트 D800 ~ DFFF 55296 55551 10 진수에 대 한 *서로게이트 쌍*, 단일 코드 포인트를 나타내는 두 개의 16 비트 값 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="8725a-113">The Unicode character set reserves the code points D800 through DFFF (55296 through 55551 decimal) for *surrogate pairs*, which require two 16-bit values to represent a single code point.</span></span> <span data-ttu-id="8725a-114">A `Char` 변수는 서로게이트 쌍을 포함할 수 없습니다 및 `String` 이러한 쌍 유지 하기 위해 두 개의 위치를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8725a-114">A `Char` variable cannot hold a surrogate pair, and a `String` uses two positions to hold such a pair.</span></span>  
  
 <span data-ttu-id="8725a-115">자세한 내용은 참조 [Char 데이터 형식을](../../../../visual-basic/language-reference/data-types/char-data-type.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8725a-115">For more information, see [Char Data Type](../../../../visual-basic/language-reference/data-types/char-data-type.md).</span></span>  
  
## <a name="string-type"></a><span data-ttu-id="8725a-116">문자열 형식</span><span class="sxs-lookup"><span data-stu-id="8725a-116">String Type</span></span>  
 <span data-ttu-id="8725a-117">`String` 데이터 형식은&0; 개 이상의&2; 바이트 (16 비트) 유니코드 문자 시퀀스입니다.</span><span class="sxs-lookup"><span data-stu-id="8725a-117">The `String` data type is a sequence of zero or more two-byte (16-bit) Unicode characters.</span></span> <span data-ttu-id="8725a-118">변수를 무제한으로 문자를 포함할 수 있으면로 선언 `String`합니다.</span><span class="sxs-lookup"><span data-stu-id="8725a-118">If a variable can contain an indefinite number of characters, declare it as `String`.</span></span> <span data-ttu-id="8725a-119">예:</span><span class="sxs-lookup"><span data-stu-id="8725a-119">For example:</span></span>  
  
 <span data-ttu-id="8725a-120">[!code-vb[VbVbalrCharTypes #&2;](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/character-data-types_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="8725a-120">[!code-vb[VbVbalrCharTypes#2](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/character-data-types_2.vb)]</span></span>  
  
 <span data-ttu-id="8725a-121">자세한 내용은 참조 [문자열 데이터 형식](../../../../visual-basic/language-reference/data-types/string-data-type.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8725a-121">For more information, see [String Data Type](../../../../visual-basic/language-reference/data-types/string-data-type.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8725a-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8725a-122">See Also</span></span>  
 <span data-ttu-id="8725a-123">[기본 데이터 형식](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="8725a-123">[Elementary Data Types](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md) </span></span>  
<span data-ttu-id="8725a-124"> [복합 데이터 형식](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="8725a-124"> [Composite Data Types](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md) </span></span>  
<span data-ttu-id="8725a-125"> [Visual Basic의 제네릭 형식](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md) </span><span class="sxs-lookup"><span data-stu-id="8725a-125"> [Generic Types in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md) </span></span>  
<span data-ttu-id="8725a-126"> [값 형식과 참조 형식](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md) </span><span class="sxs-lookup"><span data-stu-id="8725a-126"> [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md) </span></span>  
<span data-ttu-id="8725a-127"> [Visual Basic의 형식 변환](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="8725a-127"> [Type Conversions in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md) </span></span>  
<span data-ttu-id="8725a-128"> [데이터 형식 문제 해결](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="8725a-128"> [Troubleshooting Data Types](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md) </span></span>  
<span data-ttu-id="8725a-129"> [형식 문자](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)</span><span class="sxs-lookup"><span data-stu-id="8725a-129"> [Type Characters](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)</span></span>
