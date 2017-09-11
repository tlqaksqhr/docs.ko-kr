---
title: "방법: 쿼리 (LINQ) (Visual Basic)는 문자열의 문자에 대 한 | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 499ebbe0-746c-4235-9dba-ce722c12b50e
caps.latest.revision: 4
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: dabd63e52707f3078c6cdc41db8c4f0e7dfbf70e
ms.contentlocale: ko-kr
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-query-for-characters-in-a-string-linq-visual-basic"></a><span data-ttu-id="bcc1c-102">방법: 문자열 (Visual Basic) (LINQ)의 문자에 대 한 쿼리</span><span class="sxs-lookup"><span data-stu-id="bcc1c-102">How to: Query for Characters in a String (LINQ) (Visual Basic)</span></span>
<span data-ttu-id="bcc1c-103">때문에 <xref:System.String>클래스는 제네릭 구현 <xref:System.Collections.Generic.IEnumerable%601>인터페이스를 문자 시퀀스로 모든 문자열을 쿼리할 수 있습니다.</xref:System.Collections.Generic.IEnumerable%601> </xref:System.String></span><span class="sxs-lookup"><span data-stu-id="bcc1c-103">Because the <xref:System.String> class implements the generic <xref:System.Collections.Generic.IEnumerable%601> interface, any string can be queried as a sequence of characters.</span></span> <span data-ttu-id="bcc1c-104">그러나 LINQ의 일반적인 용도 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="bcc1c-104">However, this is not a common use of LINQ.</span></span> <span data-ttu-id="bcc1c-105">복잡 한 패턴 일치 작업에 대 한 <xref:System.Text.RegularExpressions.Regex>클래스</xref:System.Text.RegularExpressions.Regex> 를 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="bcc1c-105">For complex pattern matching operations, use the <xref:System.Text.RegularExpressions.Regex> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bcc1c-106">예제</span><span class="sxs-lookup"><span data-stu-id="bcc1c-106">Example</span></span>  
 <span data-ttu-id="bcc1c-107">다음 예제에서는 포함 된 숫자의 수를 결정 하는 문자열을 쿼리 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcc1c-107">The following example queries a string to determine the number of numeric digits it contains.</span></span> <span data-ttu-id="bcc1c-108">Note는 쿼리는 "" 다음 다시 처음으로 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bcc1c-108">Note that the query is "reused" after it is executed the first time.</span></span> <span data-ttu-id="bcc1c-109">쿼리 자체 실제 결과 저장 하지 않기 때문에 이것이 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcc1c-109">This is possible because the query itself does not store any actual results.</span></span>  
  
<span data-ttu-id="bcc1c-110"><CodeContentPlaceHolder>0</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="bcc1c-110"><CodeContentPlaceHolder>0</CodeContentPlaceHolder></span></span>  
## <a name="compiling-the-code"></a><span data-ttu-id="bcc1c-111">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="bcc1c-111">Compiling the Code</span></span>  
 <span data-ttu-id="bcc1c-112">.NET Framework 버전 3.5 이상 System.Core.dll에 대 한 참조를 대상으로 하는 프로젝트 만들기 및 `Imports` System.Linq 네임 스페이스에 대 한 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="bcc1c-112">Create a project that targets the .NET Framework version 3.5 or higher with a reference to System.Core.dll and a `Imports` statement for the System.Linq namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bcc1c-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bcc1c-113">See Also</span></span>  
 <span data-ttu-id="bcc1c-114">[LINQ 및 문자열 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md) </span><span class="sxs-lookup"><span data-stu-id="bcc1c-114">[LINQ and Strings (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md) </span></span>  
<span data-ttu-id="bcc1c-115"> [방법: LINQ 쿼리와 정규식 (Visual Basic)를 결합 합니다.](../../../../visual-basic/programming-guide/concepts/linq/how-to-combine-linq-queries-with-regular-expressions.md)</span><span class="sxs-lookup"><span data-stu-id="bcc1c-115"> [How to: Combine LINQ Queries with Regular Expressions (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-combine-linq-queries-with-regular-expressions.md)</span></span>
