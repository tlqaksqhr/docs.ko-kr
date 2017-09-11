---
title: "방법: 항목 목록 만들기 | Microsoft 문서"
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
helpviewer_keywords:
- list [LINQ in Visual Basic]
- objects [Visual Basic], list of items
ms.assetid: fe941aba-6340-455c-8b1f-ffd9c3eb1ac5
caps.latest.revision: 29
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: ad0d2dfd38e30ddff1a5b030ec1ace884539d134
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-create-a-list-of-items"></a><span data-ttu-id="5ce12-102">방법: 항목 목록 만들기</span><span class="sxs-lookup"><span data-stu-id="5ce12-102">How to: Create a List of Items</span></span>
<span data-ttu-id="5ce12-103">이 항목의 코드는 `Student` 클래스를 정의하고 클래스의 인스턴스 목록을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5ce12-103">The code in this topic defines a `Student` class and creates a list of instances of the class.</span></span> <span data-ttu-id="5ce12-104">목록 항목을 지원 하도록 설계 된 [연습: Visual Basic에서 쿼리 작성](../../../../visual-basic/programming-guide/concepts/linq/walkthrough-writing-queries.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5ce12-104">The list is designed to support the topic [Walkthrough: Writing Queries in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/walkthrough-writing-queries.md).</span></span> <span data-ttu-id="5ce12-105">또한 개체 목록이 필요한 모든 응용 프로그램에도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ce12-105">It also can be used for any application that requires a list of objects.</span></span> <span data-ttu-id="5ce12-106">코드는 개체 이니셜라이저를 사용하여 학생 목록에 항목을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="5ce12-106">The code defines the items in the list of students by using object initializers.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5ce12-107">예제</span><span class="sxs-lookup"><span data-stu-id="5ce12-107">Example</span></span>  
 <span data-ttu-id="5ce12-108">연습에서 작업하는 경우 연습에서 만든 프로젝트의 Module1.vb 파일에 이 코드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ce12-108">If you are working on the walkthrough, you can use this code for the Module1.vb file of the project that is created there.</span></span> <span data-ttu-id="5ce12-109">`Main` 메서드에서 * * *로 표시된 줄을 연습에서 제공되는 쿼리 및 쿼리 실행으로 바꾸면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ce12-109">Just replace the lines marked with **** in the `Main` method with the queries and query executions that are provided in the walkthrough.</span></span>  
  
 <span data-ttu-id="5ce12-110">[!code-vb[VbLINQHowToCreateList #&1;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/how-to-create-a-list-of-items_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="5ce12-110">[!code-vb[VbLINQHowToCreateList#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/how-to-create-a-list-of-items_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ce12-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5ce12-111">See Also</span></span>  
 <span data-ttu-id="5ce12-112">[연습: Visual Basic에서 쿼리 작성](../../../../visual-basic/programming-guide/concepts/linq/walkthrough-writing-queries.md) </span><span class="sxs-lookup"><span data-stu-id="5ce12-112">[Walkthrough: Writing Queries in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/walkthrough-writing-queries.md) </span></span>  
<span data-ttu-id="5ce12-113"> [Visual Basic에서 LINQ 시작](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md) </span><span class="sxs-lookup"><span data-stu-id="5ce12-113"> [Getting Started with LINQ in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md) </span></span>  
<span data-ttu-id="5ce12-114"> [개체 이니셜라이저: 명명 된 형식과 익명 형식](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md) </span><span class="sxs-lookup"><span data-stu-id="5ce12-114"> [Object Initializers: Named and Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md) </span></span>  
<span data-ttu-id="5ce12-115"> [Visual Basic의 LINQ 소개](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) </span><span class="sxs-lookup"><span data-stu-id="5ce12-115"> [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) </span></span>  
<span data-ttu-id="5ce12-116"> [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md) </span><span class="sxs-lookup"><span data-stu-id="5ce12-116"> [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md) </span></span>  
<span data-ttu-id="5ce12-117"> [쿼리](../../../../visual-basic/language-reference/queries/queries.md)</span><span class="sxs-lookup"><span data-stu-id="5ce12-117"> [Queries](../../../../visual-basic/language-reference/queries/queries.md)</span></span>
