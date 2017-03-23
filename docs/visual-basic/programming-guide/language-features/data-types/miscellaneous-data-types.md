---
title: "기타 데이터 형식 (Visual Basic) | Microsoft 문서"
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
- Object data type, data types
- data types [Visual Basic], choosing
ms.assetid: 64c71a12-9057-4dbf-baca-7379c4aada69
caps.latest.revision: 22
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 2de377fa9dfd7ec13cdbb9b700f8485b0c0e2106
ms.lasthandoff: 03/13/2017

---
# <a name="miscellaneous-data-types-visual-basic"></a>기타 데이터 형식(Visual Basic)
[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]숫자 또는 문자 분류 되지 않는 몇 가지 데이터 형식을 제공 합니다. 대신,은 특수 한 데이터 처리와 같은 예/아니요 값, 날짜/시간 값 및 개체 주소 합니다.  
  
 나란히 비교를 보여 주는 표는 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 데이터 형식 참조 [데이터 형식](../../../../visual-basic/language-reference/data-types/data-type-summary.md)합니다.  
  
## <a name="boolean-type"></a>부울 형식  
 [Boolean 데이터 형식](../../../../visual-basic/language-reference/data-types/boolean-data-type.md) 로 해석 되는 부호 없는 값은 `True` 또는 `False`합니다. 데이터 너비 구현 하는 플랫폼에 따라 달라 집니다. 변수를 포함할 수 있으면 true/false와 같은 두 가지 상태 값만 예/아니요 또는 켜기/끄기로 선언 `Boolean`합니다.  
  
## <a name="date-type"></a>날짜 형식  
 [Date 데이터 형식](../../../../visual-basic/language-reference/data-types/date-data-type.md) 날짜와 시간 정보를 보유 하는 64 비트 값입니다. 각 증분 일반 달력에서 1 년 1 월 1 (오전 12시)부터 경과 된 시간 (100 나노초)를 나타냅니다. 변수는 날짜 값, 시간 값 또는 둘 다를 포함할 수 있으면로 선언 `Date`합니다.  
  
## <a name="object-type"></a>개체 형식  
 [Object 데이터 형식](../../../../visual-basic/language-reference/data-types/object-data-type.md) 응용 프로그램 내에서 또는 일부 다른 응용 프로그램에서 개체 인스턴스를 가리키는 32 비트 주소입니다. `Object` 변수는 모든 데이터 형식의 데이터 또는 응용 프로그램에서 인식, 모든 개체를 참조할 수 있습니다. 모두 포함이 *값 형식*와 같은 `Integer`, `Boolean`, 및 구조 인스턴스 및 *참조 형식*이며와 같은 클래스에서 생성 된 개체의 인스턴스인 `String` 및 <xref:System.Windows.Forms.Form>, 배열 인스턴스.</xref:System.Windows.Forms.Form>  
  
 컴파일 타임에 모르는 하는 클래스의 인스턴스에 대 한 포인터를 저장 하는 변수 또는 다양 한 데이터 형식의 데이터를 가리키는 수로 선언 `Object`합니다.  
  
 장점은 `Object` 데이터 형식을 사용 하면 모든 데이터 형식의 데이터를 저장 한다는 것입니다. 단점은 실행 시간이 더 오래 걸리는 느리게 수행 하는 응용 프로그램을 확인 하는 추가 작업을 인해 발생 하는 것입니다. 사용 하는 경우는 `Object` 유발 값 형식에 대 한 변수를 *boxing* 및 *unboxing*합니다. 참조 형식에 대해 사용 하는 경우 발생할 *런타임에 바인딩*합니다.  
  
## <a name="see-also"></a>참고 항목  
 [형식 문자](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)   
 [기본 데이터 형식](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)   
 [숫자 데이터 형식](../../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)   
 [문자 데이터 형식](../../../../visual-basic/programming-guide/language-features/data-types/character-data-types.md)   
 [데이터 형식 문제 해결](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)   
 [초기 바인딩 및 런타임에 바인딩](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)
