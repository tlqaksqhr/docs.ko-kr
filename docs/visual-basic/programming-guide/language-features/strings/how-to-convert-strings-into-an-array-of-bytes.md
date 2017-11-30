---
title: "방법: Visual Basic에서 문자열을 바이트 배열로 변환"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- string conversion [Visual Basic], arrays
- arrays [Visual Basic], converting strings to
- byte arrays
- examples [Visual Basic], string conversion
- arrays [Visual Basic], byte arrays
ms.assetid: f477d35c-a3fc-4a30-b1d4-cd0d353aae1d
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 6d527434dc0a61c9c771b42d05c1ee316094e7fd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-convert-strings-into-an-array-of-bytes-in-visual-basic"></a><span data-ttu-id="81e00-102">방법: Visual Basic에서 문자열을 바이트 배열로 변환</span><span class="sxs-lookup"><span data-stu-id="81e00-102">How to: Convert Strings into an Array of Bytes in Visual Basic</span></span>
<span data-ttu-id="81e00-103">이 항목에서는 바이트 배열을 문자열로 변환 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="81e00-103">This topic shows how to convert a string into an array of bytes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="81e00-104">예제</span><span class="sxs-lookup"><span data-stu-id="81e00-104">Example</span></span>  
 <span data-ttu-id="81e00-105">사용 하 여이 예제는 <xref:System.Text.Encoding.GetBytes%2A> 의 메서드는 <xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType> 인코딩 바이트 배열에 문자열을 변환 하는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="81e00-105">This example uses the <xref:System.Text.Encoding.GetBytes%2A> method of the <xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType> encoding class to convert a string into an array of bytes.</span></span>  
  
 [!code-vb[VbVbalrStrings#74](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-convert-strings-into-an-array-of-bytes_1.vb)]  
  
 <span data-ttu-id="81e00-106">문자열을 바이트 배열로 변환 하는 여러 인코딩 옵션 중에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81e00-106">You can choose from several encoding options to convert a string into a byte array:</span></span>  
  
-   <span data-ttu-id="81e00-107"><xref:System.Text.Encoding.ASCII%2A?displayProperty=nameWithType>: 집합은 ASCII (7 비트) 문자에 대 한 인코딩을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="81e00-107"><xref:System.Text.Encoding.ASCII%2A?displayProperty=nameWithType>: Gets an encoding for the ASCII (7-bit) character set.</span></span>  
  
-   <span data-ttu-id="81e00-108"><xref:System.Text.Encoding.BigEndianUnicode%2A?displayProperty=nameWithType>: Big endian 바이트 순서를 사용 하 여 utf-16 형식에 대 한 인코딩을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="81e00-108"><xref:System.Text.Encoding.BigEndianUnicode%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-16 format using the big-endian byte order.</span></span>  
  
-   <span data-ttu-id="81e00-109"><xref:System.Text.Encoding.Default%2A?displayProperty=nameWithType>: 시스템의 현재 ANSI 코드 페이지에 대 한 인코딩을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="81e00-109"><xref:System.Text.Encoding.Default%2A?displayProperty=nameWithType>: Gets an encoding for the system's current ANSI code page.</span></span>  
  
-   <span data-ttu-id="81e00-110"><xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType>: Little endian 바이트 순서를 사용 하 여 utf-16 형식에 대 한 인코딩을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="81e00-110"><xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-16 format using the little-endian byte order.</span></span>  
  
-   <span data-ttu-id="81e00-111"><xref:System.Text.Encoding.UTF32%2A?displayProperty=nameWithType>: Little endian 바이트 순서를 사용 하는 utf-32 형식에 대 한 인코딩을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="81e00-111"><xref:System.Text.Encoding.UTF32%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-32 format using the little-endian byte order.</span></span>  
  
-   <span data-ttu-id="81e00-112"><xref:System.Text.Encoding.UTF7%2A?displayProperty=nameWithType>: Utf-7 형식에 대 한 인코딩을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="81e00-112"><xref:System.Text.Encoding.UTF7%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-7 format.</span></span>  
  
-   <span data-ttu-id="81e00-113"><xref:System.Text.Encoding.UTF8%2A?displayProperty=nameWithType>: Utf-8 형식에 대 한 인코딩을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="81e00-113"><xref:System.Text.Encoding.UTF8%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-8 format.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81e00-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="81e00-114">See Also</span></span>  
 <xref:System.Text.Encoding?displayProperty=nameWithType>  
 <xref:System.Text.Encoding.GetBytes%2A>  
 [<span data-ttu-id="81e00-115">방법: Visual Basic의 문자열로 바이트 배열로 변환</span><span class="sxs-lookup"><span data-stu-id="81e00-115">How to: Convert an Array of Bytes into a String in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-an-array-of-bytes-into-a-string.md)
