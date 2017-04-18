---
title: "방법: 제네릭 클래스 (Visual Basic)를 사용 하 여 | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- type parameters, defining
- data type arguments, defining
- arguments [Visual Basic], data types
- Of keyword, using
- generic parameters
- data type parameters
- generics [Visual Basic], about generics
- data types [Visual Basic], as parameters
- data types [Visual Basic], as arguments
- parameters, type
- types [Visual Basic], generic
- parameters, generic
- generics [Visual Basic], creating generic types
- data type arguments
- parameters, data type
- data type parameters, defining
- type arguments, defining
- arguments [Visual Basic], type
ms.assetid: 242dd2a6-86c4-4ce7-83f2-f2661803f752
caps.latest.revision: 24
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
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: eeb55be1c368e9ca80ab94de814a5e2ba9bc9f1f
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-use-a-generic-class-visual-basic"></a>방법: 제네릭 클래스 사용(Visual Basic)
*형식 매개 변수* 를 사용하는 클래스를 *제네릭 클래스*라고 합니다. 제네릭 클래스를 사용 중인 경우 이러한 각 매개 변수에 대해 *형식 인수* 를 제공하여, 여기에서 *생성된 클래스* 를 만들 수 있습니다. 그런 다음 생성된 클래스 형식의 변수를 선언하고, 생성된 클래스의 인스턴스를 만들어 해당 변수에 할당할 수 있습니다.  
  
 클래스 이외에도 제네릭 구조체, 인터페이스, 프로시저 및 대리자도 정의할 수 있습니다.  
  
 다음 절차에서는 [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] 에서 정의한 제네릭 클래스를 가져오고 여기에서 인스턴스를 만듭니다.  
  
### <a name="to-use-a-class-that-takes-a-type-parameter"></a>형식 매개 변수를 가져오는 클래스를 사용하려면  
  
1.  소스 파일의 시작 부분에 포함 된 [Imports 문 (.NET Namespace 및 형식)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) 가져오려는 <xref:System.Collections.Generic?displayProperty=fullName>네임 스페이스.</xref:System.Collections.Generic?displayProperty=fullName> 이 <xref:System.Collections.Generic.Queue%601?displayProperty=fullName>정규화 <xref:System.Collections.Queue?displayProperty=fullName>.</xref:System.Collections.Queue?displayProperty=fullName> 과 같은 다른 큐 클래스에서이 구분 하지 않고 클래스</xref:System.Collections.Generic.Queue%601?displayProperty=fullName> 를 참조할 수 있습니다.  
  
2.  일반적인 방법으로 개체를 만들지만 클래스 이름 바로 뒤에 `(Of` `type``)` 을 추가합니다.  
  
     다음 예제에서는 동일한 클래스를 사용 하 여 (<xref:System.Collections.Generic.Queue%601?displayProperty=fullName>) 포함 된 항목의 데이터 형식이 서로 다른 두 큐 개체를 만듭니다.</xref:System.Collections.Generic.Queue%601?displayProperty=fullName> 각 큐의 끝에 항목을 추가한 다음 각 큐의 앞부분부터 항목을 제거하고 표시합니다.  
  
     [!code-vb[VbVbalrDataTypes #&9;](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/how-to-use-a-generic-class_1.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [데이터 형식](../../../../visual-basic/programming-guide/language-features/data-types/index.md)   
 [Visual Basic의 제네릭 형식](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)   
 [언어 독립성 및 언어 독립적 구성 요소](https://msdn.microsoft.com/library/12a7a7h3)   
 [Of](../../../../visual-basic/language-reference/statements/of-clause.md)   
 [Imports 문(.NET 네임스페이스 및 형식)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)   
 [방법: 다른 데이터 형식에 동일한 기능을 제공할 수 있는 클래스 정의](../../../../visual-basic/programming-guide/language-features/data-types/how-to-define-a-class-that-can-provide-identical-functionality.md)   
 [반복기](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7)
