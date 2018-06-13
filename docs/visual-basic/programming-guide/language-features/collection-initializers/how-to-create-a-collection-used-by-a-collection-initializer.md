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
# <a name="how-to-create-a-collection-used-by-a-collection-initializer-visual-basic"></a>방법: 컬렉션 이니셜라이저에 사용되는 컬렉션 만들기(Visual Basic)
Visual Basic 컴파일러에 대 한 검색 컬렉션 이니셜라이저를 사용 하 여 컬렉션을 만들 수는 `Add` 컬렉션 형식의 메서드를 대 한 매개 변수는 `Add` 컬렉션 이니셜라이저에 있는 값의 형식과 일치 하는 메서드. 이 `Add` 메서드 값을 해당 컬렉션 이니셜라이저를 사용 하 여 컬렉션을 채우는 데 사용 됩니다.  
  
## <a name="example"></a>예제  
 다음 예제와 `OrderCollection` 공용 포함 된 컬렉션 `Add` 유형의 개체를 추가 하는 컬렉션 이니셜라이저를 사용할 수 있는 메서드 `Order`합니다. `Add` 메서드를 사용 하면 약식된 컬렉션 이니셜라이저 구문을 사용 합니다.  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#4](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-a-collection-used-by-a-collection-initializer_1.vb)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#1](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-a-collection-used-by-a-collection-initializer_2.vb)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#2](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-a-collection-used-by-a-collection-initializer_3.vb)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#3](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-a-collection-used-by-a-collection-initializer_4.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [컬렉션 이니셜라이저](../../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)  
 [방법: 컬렉션 이니셜라이저에 사용되는 확장명 추가 메서드 만들기](../../../../visual-basic/programming-guide/language-features/collection-initializers/how-to-create-an-add-extension-method-used-by-a-collection-initializer.md)
