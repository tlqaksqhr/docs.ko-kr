---
title: "방법: 상수 선언 (Visual Basic) | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.constant
dev_langs:
- VB
helpviewer_keywords:
- Integer data type, declaring constants
- Single data type, declaring constants
- Const statement [Visual Basic], declaring constants
- procedures, declaration
- data types [Visual Basic], constants
- Long data type, declaring constants
- Visual Basic code, declaring variables and constants
- Double data type, declaring constants
- Boolean data type, declaring constants
- modules, declaring constants
- Byte data type, declaring constants
- constants, declaring
- Date data type, declaring constants
- String data type, declaring constants
- declaring constants, const keyword
- Currency data type, declaring constants and variants
- module-level constants and variables
- Object data type, declaring constants
ms.assetid: f901b4fa-481f-4621-822e-427060577ad1
caps.latest.revision: 20
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
ms.openlocfilehash: 401d0feb85fccf94a25308d38c3c75198ef9294c
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-declare-a-constant-visual-basic"></a>방법: 상수 선언(Visual Basic)
사용 된 `Const` 상수를 선언 하 고 해당 값을 설정 하는 문입니다. 상수를 선언 하 여 값으로 의미 있는 이름을 할당 합니다. 상수 선언 되 면 수정 하거나 새 값을 지정할 수 없습니다.  
  
 프로시저 내에서 또는 모듈, 클래스 또는 구조체의 선언 섹션에는 상수를 선언합니다. 클래스 또는 구조체 수준의 상수는 `Private` 기본적으로,도로 선언할 수 있지만 `Public`, `Friend`, `Protected`, 또는 `Protected Friend` 적절 한 수준의 코드 액세스 합니다.  
  
 상수 (규칙은 변수 이름 만들기와 동일) 하는 기호화 된 올바른 이름 및 숫자 또는 문자열 상수 및 연산자 (없습니다 함수 호출)의 구성 된 식 이어야 합니다.  
  
[!INCLUDE[note_settings_general](../../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
### <a name="to-declare-a-constant"></a>상수 선언 하려면  
  
-   액세스 지정자를 포함 하는 선언을 작성 된 `Const` 키워드 및 다음 예와 같이 식:  
  
     [!code-vb[VbEnumsTask #&8;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-a-constant_1.vb)]  
  
     때 [Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md) 는 `Off` 및 [Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) 는 `On`, 데이터 형식을 지정 하 여 상수를 명시적으로 선언 해야 합니다 (`Boolean`, `Byte`, `Char`, `DateTime`, `Decimal`, `Double`, `Integer`, `Long`, `Short`, `Single`, 또는 `String`).  
  
     때 `Option Infer` 는 `On` 또는 `Option Strict` 는 `Off`, 데이터 형식으로 지정 하지 않고 상수를 선언할 수는 `As` 절. 컴파일러에는 상수 식의 형식에서 형식을 결정 합니다. 자세한 내용은 참조 [상수 및 리터럴 데이터 형식](constant-and-literal-data-types.md)합니다.  
  
### <a name="to-declare-a-constant-that-has-an-explicitly-stated-data-type"></a>으로 명시적으로 지정된 하는 데이터 형식이 지정 된 상수를 선언 하려면  
  
-   포함 하는 선언을 쓰기는 `As` 키워드 및는 명시적 데이터 형식, 다음 예제와 같이 합니다.  
  
     [!code-vb[VbEnumsTask #&9;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-a-constant_2.vb)]  
  
     코드 줄에 하나씩만 하는 단일 상수를 선언 하는 경우 보다 읽기 쉬운 되어도 한 줄에 여러 개의 상수를 선언할 수 있습니다. 한 줄에 여러 개의 상수를 선언 하는 경우 이들은 모두 가져야 동일한 액세스 레벨 (`Public`, `Private`, `Friend`, `Protected`, 또는 `Protected Friend`).  
  
### <a name="to-declare-multiple-constants-on-a-single-line"></a>한 줄에 여러 상수를 선언 하려면  
  
-   다음 예제와 같이 공백, 쉼표와 선언을 구분 합니다.  
  
    ```  
    Public Const Four As Integer = 4, Five As Integer = 5, Six As Integer = 44  
    ```  
  
## <a name="see-also"></a>참고 항목  
 [Const 문](../../../../visual-basic/language-reference/statements/const-statement.md)   
 [상수 및 리터럴 데이터 형식](constant-and-literal-data-types.md)   
 [상수 개요](constants-overview.md)
 [하는 방법: 상수 선언](how-to-declare-a-constant.md)
 [사용자 정의 상수](user-defined-constants.md)
 [상수 및 리터럴 데이터 형식](constant-and-literal-data-types.md)
 [하는 방법: 관련 상수 값 그룹화](how-to-group-related-constant-values-together.md)
 [열거형 개요](enumerations-overview.md)
 [하는 방법: 열거형 선언](how-to-declare-enumerations.md)
 [하는 방법: 열거형 멤버 참조](how-to-refer-to-an-enumeration-member.md)
 [열거형 및 이름 한정](enumerations-and-name-qualification.md)
 [하는 방법: 열거형 반복](how-to-iterate-through-an-enumeration.md)
 [하는 방법: 문자열 확인 열거형 값과 연결 된](how-to-determine-the-string-associated-with-an-enumeration-value.md)
 [열거형을 사용 하는 경우](when-to-use-an-enumeration.md)

 [열거형 개요](enumerations-overview.md)   
 [상수 개요](constants-overview.md)   
 [방법: 열거형 선언](how-to-declare-enumerations.md)   
 [열거형 및 이름 한정](enumerations-and-name-qualification.md)   
 [Option Strict 문](../../../../visual-basic/language-reference/statements/option-strict-statement.md)   
 [상수 및 열거형](../../../../visual-basic/language-reference/constants-and-enumerations.md)

