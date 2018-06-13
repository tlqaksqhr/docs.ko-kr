---
title: 기타 데이터 형식(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Object data type [Visual Basic], data types
- data types [Visual Basic], choosing
ms.assetid: 64c71a12-9057-4dbf-baca-7379c4aada69
ms.openlocfilehash: 9261a02f3dc286dc37b3073158ccc0c151030fe0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33647338"
---
# <a name="miscellaneous-data-types-visual-basic"></a>기타 데이터 형식(Visual Basic)
Visual Basic에서 숫자 또는 문자 분류 되지 않는 몇 가지 데이터 형식을 제공 합니다. 를 처리 특수 데이터와 같은 예/아니요 값, 날짜/시간 값 및 개체 주소입니다.  
  
 Visual Basic 데이터 형식-나란히 비교를 보여 주는 테이블을 참조 하십시오. [데이터 형식](../../../../visual-basic/language-reference/data-types/data-type-summary.md)합니다.  
  
## <a name="boolean-type"></a>부울 유형  
 [Boolean 데이터 형식](../../../../visual-basic/language-reference/data-types/boolean-data-type.md) 로 해석 되는 부호 없는 값은 `True` 또는 `False`합니다. 데이터 너비 구현 하는 플랫폼에 따라 달라 집니다. 변수를 포함할 수 있으면 true/false 같은 두 가지 상태 값만 예/아니요 또는 켜기/끄기로 선언 `Boolean`합니다.  
  
## <a name="date-type"></a>날짜 형식  
 [Date 데이터 형식](../../../../visual-basic/language-reference/data-types/date-data-type.md) 는 날짜와 시간 정보를 보유 하는 64 비트 값입니다. 각 증분은 일반 달력에서 1 년 1 월 1의 시작 부분 (오전 12시) 이후 경과 된 시간의 100 나노초를 나타냅니다. 변수 값을 날짜, 시간 값 또는 둘 다를 포함할 수 있으면로 선언 `Date`합니다.  
  
## <a name="object-type"></a>개체 형식  
 [Object 데이터 형식](../../../../visual-basic/language-reference/data-types/object-data-type.md) 응용 프로그램 내에서 또는 다른 응용 프로그램의 개체 인스턴스를 가리키는 32 비트 주소입니다. `Object` 변수 데이터 형식의 모든 데이터를 응용 프로그램에서 인식 하는 모든 개체를 참조할 수 있습니다. 여기에 둘 다 *값 형식이*와 같은 `Integer`, `Boolean`, 및 구조 인스턴스 및 *참조 형식*, 와같은클래스에서생성된개체의인스턴스는`String`및 <xref:System.Windows.Forms.Form>, 배열 인스턴스.  
  
 변수는 컴파일 타임에 알지 못하는 하는 클래스의 인스턴스에 대 한 포인터를 저장 하거나 다양 한 데이터 형식의 데이터를 가리킬 수로 선언 `Object`합니다.  
  
 이점은 `Object` 데이터 형식을 사용 하면 모든 데이터 형식의 데이터를 저장 한다는 것입니다. 단점은 실행 시간이 오래을 느리게 수행 하는 응용 프로그램을 확인 하는 추가 작업을 인해 발생 하는 것입니다. 사용 하는 경우는 `Object` 유발 값 형식에 대 한 변수를 *boxing* 및 *unboxing*합니다. 참조 형식에 대해 사용 하는 경우 발생할 *런타임에 바인딩*합니다.  
  
## <a name="see-also"></a>참고 항목  
 [형식 문자](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)  
 [기본 데이터 형식](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)  
 [숫자 데이터 형식](../../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)  
 [문자 데이터 형식](../../../../visual-basic/programming-guide/language-features/data-types/character-data-types.md)  
 [데이터 형식 문제 해결](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [초기 바인딩 및 런타임에 바인딩](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)
