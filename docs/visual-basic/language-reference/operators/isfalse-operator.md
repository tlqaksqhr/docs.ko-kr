---
title: IsFalse 연산자(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.isfalse
helpviewer_keywords:
- AndAlso operator [Visual Basic]
- IsFalse operator [Visual Basic]
ms.assetid: 37fc9dbf-e5cc-4570-b93f-7213447974df
ms.openlocfilehash: e84b2162eb0763725f05bc52d5c4223d7c430b81
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33600049"
---
# <a name="isfalse-operator-visual-basic"></a>IsFalse 연산자(Visual Basic)
식이 인지 결정 `False`합니다.  
  
 호출할 수 없습니다 `IsFalse` 명시적으로 코드 하지만 Visual Basic에서 컴파일러 있습니다 사용할에서 코드를 생성할 `AndAlso` 절. 클래스 또는 구조체 정의 다음에 해당 형식의 변수를 사용 하는 경우는 `AndAlso` 정의 해야 절 `IsFalse` 해당 클래스 또는 구조체에서 합니다.  
  
 컴파일러 있다고 간주는 `IsFalse` 및 `IsTrue` 으로 연산자는 *일치 하는 쌍*합니다. 이 둘 중 하나를 정의 하는 경우도 정의 해야 다른 것을 의미 합니다.  
  
> [!NOTE]
>  `IsFalse` 연산자 될 수 있습니다 *오버 로드 된*, 클래스 또는 구조체 수 할의 동작에 해당 클래스 또는 구조체의 형식입니다. 이 연산자를 사용 하 여 이러한 클래스나 구조체에는 코드를 다시 정의 된 동작을 이해 해야 합니다. 자세한 내용은 참조 [연산자 프로시저](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)합니다.  
  
## <a name="example"></a>예제  
 다음 코드 예제에 대 한 정의 포함 하는 구조체의 개요를 정의 고 `IsFalse` 및 `IsTrue` 연산자입니다.  
  
 [!code-vb[VbVbalrOperators#28](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/isfalse-operator_1.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [IsTrue 연산자](../../../visual-basic/language-reference/operators/istrue-operator.md)  
 [방법: 연산자 정의](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)  
 [AndAlso 연산자](../../../visual-basic/language-reference/operators/andalso-operator.md)
