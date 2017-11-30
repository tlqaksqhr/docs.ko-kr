---
title: "방법: 문자열 내에서 검색(Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- strings [Visual Basic], finding
- strings [Visual Basic], searching
- examples [Visual Basic], strings
ms.assetid: ae4c79e0-08ea-489f-bdb2-5eb6d355f284
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2c828d0b32fdf90e121e9d5da0bb60ab11c212f4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-search-within-a-string-visual-basic"></a><span data-ttu-id="c803f-102">방법: 문자열 내에서 검색(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c803f-102">How to: Search Within a String (Visual Basic)</span></span>
<span data-ttu-id="c803f-103">이 예제에서는 호출는 <xref:System.String.IndexOf%2A> 에서 메서드는 <xref:System.String> 개체 맨 처음 발견 되는 부분 문자열의 인덱스를 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="c803f-103">This example calls the <xref:System.String.IndexOf%2A> method on a <xref:System.String> object to report the index of the first occurrence of a substring.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c803f-104">예제</span><span class="sxs-lookup"><span data-stu-id="c803f-104">Example</span></span>  
 [!code-vb[VbVbalrStrings#71](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-search-within-a-string_1.vb)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c803f-105">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="c803f-105">Compiling the Code</span></span>  
 <span data-ttu-id="c803f-106">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="c803f-106">This example requires:</span></span>  
  
-   <span data-ttu-id="c803f-107">`Imports` 문을 지정 하는 <xref:System> 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="c803f-107">An `Imports` statement specifying the <xref:System> namespace.</span></span> <span data-ttu-id="c803f-108">자세한 내용은 [Imports 문(.NET 네임스페이스 및 형식)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c803f-108">For more information, see [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="c803f-109">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="c803f-109">Robust Programming</span></span>  
 <span data-ttu-id="c803f-110"><xref:System.String.IndexOf%2A> 메서드 맨 처음 발견 되는 부분 문자열의 첫 번째 문자의 위치를 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="c803f-110">The <xref:System.String.IndexOf%2A> method reports the location of the first character of the first occurrence of the substring.</span></span> <span data-ttu-id="c803f-111">인덱스는 0부터 즉 문자열의 첫 번째 문자에 인덱스 0.</span><span class="sxs-lookup"><span data-stu-id="c803f-111">The index is 0-based, which means the first character of a string has an index of 0.</span></span>  
  
 <span data-ttu-id="c803f-112">경우 <xref:System.String.IndexOf%2A> 는 부분 문자열을 찾지 못하면-1을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c803f-112">If <xref:System.String.IndexOf%2A> does not find the substring, it returns -1.</span></span>  
  
 <span data-ttu-id="c803f-113"><xref:System.String.IndexOf%2A> 메서드는 대/소문자 구분 하며 현재 문화권을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c803f-113">The <xref:System.String.IndexOf%2A> method is case-sensitive and uses the current culture.</span></span>  
  
 <span data-ttu-id="c803f-114">오류를 제어에 대 한 문자열 검색을 포함 하려는 `Try` 블록는 [시도 중... Catch 하는 중... Finally 문](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md) 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="c803f-114">For optimal error control, you might want to enclose the string search in the `Try` block of a [Try...Catch...Finally Statement](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md) construction.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c803f-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c803f-115">See Also</span></span>  
 <xref:System.String.IndexOf%2A>  
 [<span data-ttu-id="c803f-116">Try...Catch...Finally 문</span><span class="sxs-lookup"><span data-stu-id="c803f-116">Try...Catch...Finally Statement</span></span>](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)  
 [<span data-ttu-id="c803f-117">Visual Basic의 문자열 소개</span><span class="sxs-lookup"><span data-stu-id="c803f-117">Introduction to Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)  
 [<span data-ttu-id="c803f-118">문자열</span><span class="sxs-lookup"><span data-stu-id="c803f-118">Strings</span></span>](../../../../visual-basic/programming-guide/language-features/strings/index.md)
