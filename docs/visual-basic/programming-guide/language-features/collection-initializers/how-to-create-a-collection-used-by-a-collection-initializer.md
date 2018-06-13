---
title: '방법: 컬렉션 이니셜라이저에 사용되는 컬렉션 만들기(Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- collection initializers [Visual Basic]
ms.assetid: c858db10-424d-47e0-92cd-e08087cc5ebc
ms.openlocfilehash: 6158b6f02d95260e2955e77d732fae8b8d9d5e04
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33654163"
---
# <a name="how-to-create-a-collection-used-by-a-collection-initializer-visual-basic"></a><span data-ttu-id="da201-102">방법: 컬렉션 이니셜라이저에 사용되는 컬렉션 만들기(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="da201-102">How to: Create a Collection Used by a Collection Initializer (Visual Basic)</span></span>
<span data-ttu-id="da201-103">Visual Basic 컴파일러에 대 한 검색 컬렉션 이니셜라이저를 사용 하 여 컬렉션을 만들 수는 `Add` 컬렉션 형식의 메서드를 대 한 매개 변수는 `Add` 컬렉션 이니셜라이저에 있는 값의 형식과 일치 하는 메서드.</span><span class="sxs-lookup"><span data-stu-id="da201-103">When you use a collection initializer to create a collection, the Visual Basic compiler searches for an `Add` method of the collection type for which the parameters for the `Add` method match the types of the values in the collection initializer.</span></span> <span data-ttu-id="da201-104">이 `Add` 메서드 값을 해당 컬렉션 이니셜라이저를 사용 하 여 컬렉션을 채우는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="da201-104">This `Add` method is used to populate the collection with the values from the collection initializer.</span></span>  
  
## <a name="example"></a><span data-ttu-id="da201-105">예제</span><span class="sxs-lookup"><span data-stu-id="da201-105">Example</span></span>  
 <span data-ttu-id="da201-106">다음 예제와 `OrderCollection` 공용 포함 된 컬렉션 `Add` 유형의 개체를 추가 하는 컬렉션 이니셜라이저를 사용할 수 있는 메서드 `Order`합니다.</span><span class="sxs-lookup"><span data-stu-id="da201-106">The following example shows an `OrderCollection` collection that contains a public `Add` method that a collection initializer can use to add objects of type `Order`.</span></span> <span data-ttu-id="da201-107">`Add` 메서드를 사용 하면 약식된 컬렉션 이니셜라이저 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="da201-107">The `Add` method enables you to use the shortened collection initializer syntax.</span></span>  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#4](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-a-collection-used-by-a-collection-initializer_1.vb)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#1](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-a-collection-used-by-a-collection-initializer_2.vb)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#2](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-a-collection-used-by-a-collection-initializer_3.vb)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#3](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-a-collection-used-by-a-collection-initializer_4.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="da201-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="da201-108">See Also</span></span>  
 [<span data-ttu-id="da201-109">컬렉션 이니셜라이저</span><span class="sxs-lookup"><span data-stu-id="da201-109">Collection Initializers</span></span>](../../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)  
 [<span data-ttu-id="da201-110">방법: 컬렉션 이니셜라이저에 사용되는 확장명 추가 메서드 만들기</span><span class="sxs-lookup"><span data-stu-id="da201-110">How to: Create an Add Extension Method Used by a Collection Initializer</span></span>](../../../../visual-basic/programming-guide/language-features/collection-initializers/how-to-create-an-add-extension-method-used-by-a-collection-initializer.md)
