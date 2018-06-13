---
title: '방법: Try/Catch 블록을 사용하여 예외 catch'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- exceptions, try/catch blocks
- try blocks
- try/catch blocks
- catch blocks
ms.assetid: a3ce6dfd-1f64-471b-8ad8-8cfaf406275d
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b169353752f6e6483a056cdc9dd8c3227b9ebeb8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33571453"
---
# <a name="how-to-use-the-trycatch-block-to-catch-exceptions"></a><span data-ttu-id="4a373-102">try/catch 블록을 사용하여 예외를 catch하는 방법</span><span class="sxs-lookup"><span data-stu-id="4a373-102">How to use the try/catch block to catch exceptions</span></span>

<span data-ttu-id="4a373-103">예외를 throw할 수 있는 코드 섹션을 `try` 블록에 넣고 예외를 처리하는 코드를 `catch` 블록에 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="4a373-103">Place the sections of code that might throw exceptions in a `try` block and place code that handles exceptions in a `catch` block.</span></span> <span data-ttu-id="4a373-104">`catch` 블록은 `catch` 키워드로 시작하고 예외 유형 및 수행할 작업으로 이루어진 일련의 문입니다.</span><span class="sxs-lookup"><span data-stu-id="4a373-104">The `catch` block is a series of statements beginning with the keyword `catch`, followed by an exception type and an action to be taken.</span></span>

<span data-ttu-id="4a373-105">다음 코드 예제에서는 `try`/`catch` 블록을 사용하여 가능한 예외를 catch합니다.</span><span class="sxs-lookup"><span data-stu-id="4a373-105">The following code example uses a `try`/`catch` block to catch a possible exception.</span></span> <span data-ttu-id="4a373-106">`Main` 메서드에는 `data.txt`라는 데이터 파일을 열고 파일에서 문자열을 쓰는 <xref:System.IO.StreamReader> 문이 포함된 `try` 블록이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a373-106">The `Main` method contains a `try` block with a <xref:System.IO.StreamReader> statement that opens a data file called `data.txt` and writes a string from the file.</span></span> <span data-ttu-id="4a373-107">`try` 블록 뒤에는 `try` 블록에서 발생하는 예외를 catch하는 `catch` 블록이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a373-107">Following the `try` block is a `catch` block that catches any exception that results from the `try` block.</span></span>

 [!code-cpp[CatchException#3](../../../samples/snippets/cpp/VS_Snippets_CLR/CatchException/CPP/catchexception2.cpp#3)]
 [!code-csharp[CatchException#3](../../../samples/snippets/csharp/VS_Snippets_CLR/CatchException/CS/catchexception2.cs#3)]
 [!code-vb[CatchException#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CatchException/VB/catchexception2.vb#3)]  

<span data-ttu-id="4a373-108">공용 언어 런타임은 catch 블록에서 catch되지 않은 예외를 catch합니다.</span><span class="sxs-lookup"><span data-stu-id="4a373-108">The common language runtime catches exceptions that are not caught by a catch block.</span></span> <span data-ttu-id="4a373-109">런타임의 구성 방법에 따라 디버그 대화 상자가 나타나거나, 프로그램 실행이 중단되고 예외 정보가 포함된 대화 상자가 나타나거나, 오류가 STDERR에 출력됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a373-109">Depending on how the runtime is configured, a debug dialog box appears, or the program stops executing and a dialog box with exception information appears, or an error is printed out to STDERR.</span></span>

> [!NOTE] 
> <span data-ttu-id="4a373-110">거의 모든 코드 줄에서 예외, 특히 <xref:System.OutOfMemoryException>과 같은 공용 언어 런타임에서 throw된 예외가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a373-110">Almost any line of code can cause an exception, particularly exceptions that are thrown by the common language runtime itself, such as <xref:System.OutOfMemoryException>.</span></span> <span data-ttu-id="4a373-111">대부분의 응용 프로그램은 이러한 예외를 처리할 필요가 없지만 다른 사용자가 사용할 라이브러리를 작성하는 경우 이러한 가능성에 유의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a373-111">Most applications don't have to deal with these exceptions, but you should be aware of this possibility when writing libraries to be used by others.</span></span> <span data-ttu-id="4a373-112">Try 블록에서 코드를 설정하는 경우에 대한 제안 사항은 [예외에 대한 모범 사례](best-practices-for-exceptions.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4a373-112">For suggestions on when to set code in a Try block, see [Best Practices for Exceptions](best-practices-for-exceptions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="4a373-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4a373-113">See Also</span></span>  
[<span data-ttu-id="4a373-114">예외</span><span class="sxs-lookup"><span data-stu-id="4a373-114">Exceptions</span></span>](index.md)
