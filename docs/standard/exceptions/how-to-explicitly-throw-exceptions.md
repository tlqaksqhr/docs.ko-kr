---
title: "방법: 명시적으로 예외 Throw"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- exceptions, try/catch blocks
- FileNotFoundException class
- try/catch blocks
- exceptions, throwing
- implicitly throwing exceptions
ms.assetid: 72bdd157-caa9-4478-9ee3-cb4500b84528
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c3fce332263dac3f9906d33fe3bd2590050b86f8
ms.sourcegitcommit: bbde43da655ae7bea1977f7af7345eb87bd7fd5f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/21/2017
---
# <a name="how-to-explicitly-throw-exceptions"></a><span data-ttu-id="6b3ed-102">명시적으로 예외를 throw하는 방법</span><span class="sxs-lookup"><span data-stu-id="6b3ed-102">How to explicitly throw exceptions</span></span>

<span data-ttu-id="6b3ed-103">`throw` 문을 사용하여 명시적으로 예외를 throw할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b3ed-103">You can explicitly throw an exception using the `throw` statement.</span></span> <span data-ttu-id="6b3ed-104">`throw` 문을 사용하여 catch된 예외를 다시 throw할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b3ed-104">You can also throw a caught exception again using the `throw` statement.</span></span> <span data-ttu-id="6b3ed-105">디버그 시 자세한 정보를 제공하기 위해 다시 throw되는 예외에 정보를 추가하는 것은 좋은 코딩 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="6b3ed-105">It is good coding practice to add information to an exception that is re-thrown to provide more information when debugging.</span></span>

<span data-ttu-id="6b3ed-106">다음 코드 예제에서는 `try`/`catch` 블록을 사용하여 가능한 <xref:System.IO.FileNotFoundException>을 catch합니다.</span><span class="sxs-lookup"><span data-stu-id="6b3ed-106">The following code example uses a `try`/`catch` block to catch a possible <xref:System.IO.FileNotFoundException>.</span></span> <span data-ttu-id="6b3ed-107">`try` 블록 뒤에는 <xref:System.IO.FileNotFoundException>을 catch하고 데이터 파일을 찾을 수 없는 경우 콘솔에 메시지를 쓰는 `catch` 블록이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b3ed-107">Following the `try` block is a `catch` block that catches the <xref:System.IO.FileNotFoundException> and writes a message to the console if the data file is not found.</span></span> <span data-ttu-id="6b3ed-108">다음 문은 새 <xref:System.IO.FileNotFoundException>을 throw하고 예외에 텍스트 정보를 추가하는 `throw` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="6b3ed-108">The next statement is the `throw` statement that throws a new <xref:System.IO.FileNotFoundException> and adds text information to the exception.</span></span>

[!code-csharp[Exception.Throwing#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Exception.Throwing/CS/throw.cs#1)]
[!code-vb[Exception.Throwing#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Exception.Throwing/VB/throw.vb#1)]  

## <a name="see-also"></a><span data-ttu-id="6b3ed-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6b3ed-109">See Also</span></span>  
[<span data-ttu-id="6b3ed-110">예외</span><span class="sxs-lookup"><span data-stu-id="6b3ed-110">Exceptions</span></span>](index.md)
