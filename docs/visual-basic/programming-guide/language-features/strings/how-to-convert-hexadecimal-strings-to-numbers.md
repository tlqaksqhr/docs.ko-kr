---
title: '방법: 16진수 문자열을 숫자로 변환(Visual Basic)'
ms.date: 01/31/2018
helpviewer_keywords:
- numbers [Visual Basic], hexadecimals
- hexadecimals [Visual Basic], decimals
- examples [Visual Basic], string conversion
- decimals [Visual Basic], hexadecimals
- string conversion [Visual Basic], hexadecimal to numbers
ms.assetid: 76675807-eadb-4c08-bd50-e6c6ff4b8ced
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: af0e6c1e30c116709ed98240de7bf3471fa842d4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33648644"
---
# <a name="how-to-convert-hexadecimal-strings-to-numbers-visual-basic"></a><span data-ttu-id="1737d-102">방법: 16진수 문자열을 숫자로 변환(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1737d-102">How to: Convert Hexadecimal Strings to Numbers (Visual Basic)</span></span>
<span data-ttu-id="1737d-103">사용 하 여 정수를 16 진수 문자열로 변환 하는이 예제는 <xref:System.Convert.ToInt32%2A?displayProperty=nameWithType> 메서드.</span><span class="sxs-lookup"><span data-stu-id="1737d-103">This example converts a hexadecimal string to an integer using the <xref:System.Convert.ToInt32%2A?displayProperty=nameWithType> method.</span></span>  
  
## <a name="to-convert-a-hexadecimal-string-to-a-number"></a><span data-ttu-id="1737d-104">16 진수 문자열을 숫자로 변환 하려면</span><span class="sxs-lookup"><span data-stu-id="1737d-104">To convert a hexadecimal string to a number</span></span>  
  
-   <span data-ttu-id="1737d-105">사용 하 여는 <xref:System.Convert.ToInt32(System.String,System.Int32)> 정수로 16 진수로 표시 된 숫자를 변환 하는 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="1737d-105">Use the <xref:System.Convert.ToInt32(System.String,System.Int32)> method to convert the number expressed in base-16 to an integer.</span></span>  
  
     <span data-ttu-id="1737d-106">첫 번째 인수는 <xref:System.Convert.ToInt32(System.String,System.Int32)> 메서드는 변환할 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="1737d-106">The first argument of the <xref:System.Convert.ToInt32(System.String,System.Int32)> method is the string to convert.</span></span> <span data-ttu-id="1737d-107">두 번째 인수는 숫자; 기 수를 나타냅니다. 16 진수는 기본 16 개입니다.</span><span class="sxs-lookup"><span data-stu-id="1737d-107">The second argument describes what base the number is expressed in; hexadecimal is base 16.</span></span>  
  
     [!code-vb[HexConversion](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-convert-hexadecimal-strings-to-numbers_1.vb)]  

- <span data-ttu-id="1737d-108">16 진수 문자열에 다음과 같은 제한 사항이 있는지 note:</span><span class="sxs-lookup"><span data-stu-id="1737d-108">Note that the hexadecimal string has the following restrictions:</span></span>

   - <span data-ttu-id="1737d-109">포함할 수 없습니다는 `&h` 접두사입니다.</span><span class="sxs-lookup"><span data-stu-id="1737d-109">It cannot include the `&h` prefix.</span></span>
   - <span data-ttu-id="1737d-110">포함할 수 없습니다는 `_` 숫자 구분 기호입니다.</span><span class="sxs-lookup"><span data-stu-id="1737d-110">It cannot include the `_` digit separator.</span></span>

   <span data-ttu-id="1737d-111">접두사 또는 숫자 구분 기호는 있는 경우에 대 한 호출에서 <xref:System.Convert.ToInt32(System.String,System.Int32)> 메서드가 throw 한 <xref:System.FormatException>합니다.</span><span class="sxs-lookup"><span data-stu-id="1737d-111">If the prefix or a digit separator is present, the call to the <xref:System.Convert.ToInt32(System.String,System.Int32)> method throws a <xref:System.FormatException>.</span></span>

## <a name="see-also"></a><span data-ttu-id="1737d-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1737d-112">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Conversion.Hex%2A>  
 <xref:System.Convert.ToInt32%2A?displayProperty=nameWithType>
