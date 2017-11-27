---
title: "방법: 컬렉션 이니셜라이저에 사용되는 확장명 추가 메서드 만들기(Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords: collection initializers [Visual Basic]
ms.assetid: f64b52c7-8b11-4410-93a6-cb3aeebcc772
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d19ac8b03b992eb9b09b5cb45fdcceadad3a822a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-an-add-extension-method-used-by-a-collection-initializer-visual-basic"></a><span data-ttu-id="f2ea2-102">방법: 컬렉션 이니셜라이저에 사용되는 확장명 추가 메서드 만들기(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f2ea2-102">How to: Create an Add Extension Method Used by a Collection Initializer (Visual Basic)</span></span>
<span data-ttu-id="f2ea2-103">Visual Basic 컴파일러에 대 한 검색 컬렉션 이니셜라이저를 사용 하 여 컬렉션을 만들 수는 `Add` 컬렉션 형식의 메서드를 대 한 매개 변수는 `Add` 컬렉션 이니셜라이저에 있는 값의 형식과 일치 하는 메서드.</span><span class="sxs-lookup"><span data-stu-id="f2ea2-103">When you use a collection initializer to create a collection, the Visual Basic compiler searches for an `Add` method of the collection type for which the parameters for the `Add` method match the types of the values in the collection initializer.</span></span> <span data-ttu-id="f2ea2-104">이 `Add` 메서드 값을 해당 컬렉션 이니셜라이저를 사용 하 여 컬렉션을 채우는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f2ea2-104">This `Add` method is used to populate the collection with the values from the collection initializer.</span></span>  
  
 <span data-ttu-id="f2ea2-105">일치 하는 경우 `Add` 메서드 및 컬렉션에 대 한 코드를 수정할 수 없습니다, 확장 메서드를 추가할 수 있습니다 `Add` 컬렉션 이니셜라이저에 필요한 매개 변수를 사용 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2ea2-105">If no matching `Add` method exists and you cannot modify the code for the collection, you can add an extension method called `Add` that takes the parameters that are required by the collection initializer.</span></span> <span data-ttu-id="f2ea2-106">일반적으로 제네릭 컬렉션에 대 한 컬렉션 이니셜라이저를 사용 하는 경우 수행 해야 하는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="f2ea2-106">This is typically what you need to do when you use collection initializers for generic collections.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f2ea2-107">예제</span><span class="sxs-lookup"><span data-stu-id="f2ea2-107">Example</span></span>  
 <span data-ttu-id="f2ea2-108">다음 예제에서는 원본에는 확장 메서드를 추가 하는 방법을 보여 줍니다 <xref:System.Collections.Generic.List%601> 유형의 개체를 추가 하는 컬렉션 이니셜라이저를 사용할 수 있도록 입력 `Employee`합니다.</span><span class="sxs-lookup"><span data-stu-id="f2ea2-108">The following example shows how to add an extension method to the generic <xref:System.Collections.Generic.List%601> type so that a collection initializer can be used to add objects of type `Employee`.</span></span> <span data-ttu-id="f2ea2-109">확장 메서드를 사용 하면 약식된 컬렉션 이니셜라이저 구문을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2ea2-109">The extension method enables you to use the shortened collection initializer syntax.</span></span>  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#1](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-an-add-extension-method-used-by-a-collection-initializer_1.vb)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#2](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-an-add-extension-method-used-by-a-collection-initializer_2.vb)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#3](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-an-add-extension-method-used-by-a-collection-initializer_3.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="f2ea2-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f2ea2-110">See Also</span></span>  
 [<span data-ttu-id="f2ea2-111">컬렉션 이니셜라이저</span><span class="sxs-lookup"><span data-stu-id="f2ea2-111">Collection Initializers</span></span>](../../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)  
 [<span data-ttu-id="f2ea2-112">방법: 컬렉션 이니셜라이저에 사용되는 컬렉션 만들기</span><span class="sxs-lookup"><span data-stu-id="f2ea2-112">How to: Create a Collection Used by a Collection Initializer</span></span>](../../../../visual-basic/programming-guide/language-features/collection-initializers/how-to-create-a-collection-used-by-a-collection-initializer.md)
