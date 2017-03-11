---
title: "Visual Basic Coding Conventions | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "coding conventions, Visual Basic"
  - "examples [Visual Basic], coding conventions"
  - "Visual Basic code, conventions"
ms.assetid: c1df130b-fec6-49a5-becf-0a7e494a1d0f
caps.latest.revision: 48
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 48
---
# Visual Basic Coding Conventions
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Microsoft는 이 항목의 지침을 따르는 샘플과 설명서를 개발합니다.  동일한 코딩 규칙을 따를 경우 다음과 같은 이점이 있습니다.  
  
-   사용자 코드는 레이아웃이 아닌 내용에 집중할 수 있도록 일관성 있는 모양이 됩니다.  
  
-   사용자가 이전 경험을 기반으로 예상할 수 있기 때문에 코드를 더 신속하게 이해할 수 있습니다.  
  
-   코드를 더 쉽게 복사, 변경, 유지 관리할 수 있습니다.  
  
-   코드가 Visual Basic에 대한 "최선의 구현 방법"을 보여주도록 돕습니다.  
  
## 명명 규칙  
  
-   명명 지침에 대한 자세한 내용은 [명명 지침](../Topic/Naming%20Guidelines.md) 항목을 참조하십시오.  
  
-   변수 이름의 일부로 "My"나 "my"를 사용하지 마십시오.  이 연습은 `My` 개체와 혼동될 수 있습니다.  
  
-   자동 생성된 코드의 개체 이름을 지침에 맞게 변경할 필요는 없습니다.  
  
## 레이아웃 규칙  
  
-   탭을 공백으로 삽입하고 스마트 들여쓰기를 4개의 공백 들여쓰기와 함께 사용합니다.  
  
-   **코드 서식 다시 적용\(다시 설정\)**을 사용하면 코드 편집기의 코드 서식을 다시 지정합니다.  자세한 내용은 [옵션, 텍스트 편집기, 기본\(Visual Basic\)](/visual-studio/ide/reference/options-text-editor-basic-visual-basic)을 참조하십시오.  
  
-   한 줄에 하나의 문만 사용합니다.  Visual Basic 줄 구분선 문자\(:\)를 사용하지 마십시오.  
  
-   명시적 줄 연속 문자 "\_"를 사용하지 말고 대신 언어가 허용하는 암시적 줄 연속 문자를 사용합니다.  
  
-   한 줄에 하나의 선언만 사용합니다.  
  
-   **코드 서식 다시 적용\(재설정\)**이 연속 줄을 자동으로 설정하지 않는 경우 연속 줄을 수동으로 탭 정지 하나만큼 들여 써야 합니다.  그러나 목록의 항목은 항상 왼쪽으로 정렬합니다.  
  
    ```  
    a As Integer,  
    b As Integer  
    ```  
  
-   메서드 및 속성 정의 사이에 적어도 하나 이상의 빈 줄을 추가합니다.  
  
## 주석 규칙  
  
-   코드 줄의 끝이 아닌 새 줄에 주석을 배치합니다.  
  
-   대문자로 주석 텍스트를 시작하고 주석 텍스트 끝에는 마침표를 찍습니다.  
  
-   주석 구분 기호\('\)와 주석 텍스트 사이에 공백 하나를 삽입합니다.  
  
     [!code-vb[VbVbalrGuidelines#2](../../../visual-basic/programming-guide/program-structure/codesnippet/visualbasic/VBProject/Class1.vb#2)]  
  
-   주석을 서식이 지정된 별표 블록으로 둘러싸지 마십시오.  
  
## 프로그램 구조  
  
-   `Main` 메서드를 사용할 때는 새 콘솔 응용 프로그램에 대해 기본 구조를 사용하고 명령줄 인수에 대해 `My`를 사용합니다.  
  
     [!code-vb[VbVbalrGuidelines#3](../../../visual-basic/programming-guide/program-structure/codesnippet/visualbasic/VBProject/Class1.vb#3)]  
  
## 언어 지침  
  
### String 데이터 형식  
  
-   문자열을 연결하려면, 앰퍼샌드\(&\)를 사용합니다.  
  
     [!code-vb[VbVbalrGuidelines#4](../../../visual-basic/programming-guide/program-structure/codesnippet/visualbasic/VBProject/Class1.vb#4)]  
  
-   루프에 문자열을 추가하려면 <xref:System.Text.StringBuilder> 개체를 사용합니다.  
  
     [!code-vb[VbVbalrGuidelines#5](../../../visual-basic/programming-guide/program-structure/codesnippet/visualbasic/VBProject/Class1.vb#5)]  
  
### 이벤트 처리기의 완화된 대리자  
 인수\(개체 및 EventArg\)를 이벤트 처리기로 명시적으로 한정하지 마십시오.  이벤트에 전달된 이벤트 인수를 사용하지 않는 경우\(예: Object, EventArgs와 같은 전달자\) 완화된 대리자를 사용하여 코드에서 이벤트 인수를 생략합니다.  
  
 [!code-vb[VbVbalrGuidelines#7](../../../visual-basic/programming-guide/program-structure/codesnippet/visualbasic/VBProject/Class1.vb#7)]  
  
### 부호 없는 데이터 형식  
  
-   필요한 경우를 제외하고는 부호 없는 형식 대신 `Integer`를 사용합니다.  
  
### 배열  
  
-   선언 줄에서 배열을 초기화할 때는 간단한 구문을 사용합니다.  예를 들어 다음 구문을 사용합니다.  
  
     [!code-vb[VbVbalrGuidelines#8](../../../visual-basic/programming-guide/program-structure/codesnippet/visualbasic/VBProject/Class1.vb#8)]  
  
     다음 구문을 사용하지 마십시오.  
  
     [!code-vb[VbVbalrGuidelines#9](../../../visual-basic/programming-guide/program-structure/codesnippet/visualbasic/VBProject/Class1.vb#9)]  
  
-   변수 대신 형식에 배열 지정자를 삽입합니다.  예를 들어 다음 구문을 사용합니다.  
  
     [!code-vb[VbVbalrGuidelines#11](../../../visual-basic/programming-guide/program-structure/codesnippet/visualbasic/VBProject/Class1.vb#11)]  
  
     다음 구문을 사용하지 마십시오.  
  
     [!code-vb[VbVbalrGuidelines#10](../../../visual-basic/programming-guide/program-structure/codesnippet/visualbasic/VBProject/Class1.vb#10)]  
  
-   기본 데이터 형식의 배열을 선언하고 초기화할 때 {} 구문을 사용합니다.  예를 들어 다음 구문을 사용합니다.  
  
     [!code-vb[VbVbalrGuidelines#12](../../../visual-basic/programming-guide/program-structure/codesnippet/visualbasic/VBProject/Class1.vb#12)]  
  
     다음 구문을 사용하지 마십시오.  
  
     [!code-vb[VbVbalrGuidelines#13](../../../visual-basic/programming-guide/program-structure/codesnippet/visualbasic/VBProject/Class1.vb#13)]  
  
### With 키워드 사용  
 한 개체에 대해 여러 호출을 하는 경우에는 `With` 키워드를 사용합니다.  
  
 [!code-vb[VbVbalrGuidelines#15](../../../visual-basic/programming-guide/program-structure/codesnippet/visualbasic/VBProject/Class1.vb#15)]  
  
### 예외 처리를 사용할 때 Try...Catch 및 Using 문 사용  
 `On Error Goto`를 사용하지 마십시오.  
  
### IsNot 키워드 사용  
 `Not...Is Nothing` 대신 `IsNot` 키워드를 사용하십시오.  
  
### New 키워드  
  
-   간단한 인스턴스를 사용합니다.  예를 들어 다음 구문을 사용합니다.  
  
     [!code-vb[VbVbalrGuidelines#21](../../../visual-basic/programming-guide/program-structure/codesnippet/visualbasic/VBProject/Class1.vb#21)]  
  
     앞의 줄은 다음과 동일합니다.  
  
     [!code-vb[VbVbalrGuidelines#22](../../../visual-basic/programming-guide/program-structure/codesnippet/visualbasic/VBProject/Class1.vb#22)]  
  
-   매개 변수 없는 생성자 대신 새 개체에 대해 개체 이니셜라이저를 사용합니다.  
  
     [!code-vb[VbVbalrGuidelines#23](../../../visual-basic/programming-guide/program-structure/codesnippet/visualbasic/VBProject/Class1.vb#23)]  
  
### 이벤트 처리  
  
-   `AddHandler` 대신 `Handles`를 사용합니다.  
  
     [!code-vb[VbVbalrGuidelines#24](../../../visual-basic/programming-guide/program-structure/codesnippet/visualbasic/VBProject/Class1.vb#24)]  
  
-   `AddressOf`를 사용하고 대리자를 명시적으로 인스턴스화하지 않습니다.  
  
     [!code-vb[VbVbalrGuidelines#25](../../../visual-basic/programming-guide/program-structure/codesnippet/visualbasic/VBProject/Class1.vb#25)]  
  
-   이벤트를 정의할 때는 간단한 구문을 사용하고 컴파일러에서 대리자를 정의하도록 합니다.  
  
     [!code-vb[VbVbalrGuidelines#26](../../../visual-basic/programming-guide/program-structure/codesnippet/visualbasic/VBProject/Class1.vb#26)]  
  
-   `RaiseEvent` 메서드를 호출하기 전에 이벤트가 `Nothing`\(null\)인지 확인하지 마십시오.  `RaiseEvent`는 이벤트를 발생시키기 전에 `Nothing`을 확인합니다.  
  
### 공유 멤버 사용  
 인스턴스 변수에서 호출하지 않고 클래스 이름을 사용하여 `Shared` 멤버를 호출합니다.  
  
### XML 리터럴 사용  
 XML 리터럴을 사용하면 XML을 사용할 할 때 가장 일반적으로 수행하는 로드, 쿼리, 변환과 같은 작업을 간단하게 만들 수 있습니다.  XML을 개발할 때 다음 지침을 따릅니다.  
  
-   XML API를 직접 호출하는 대신 XML 리터럴을 사용하여 XML 문서 및 조각을 만듭니다.  
  
-   파일 또는 프로젝트 수준에서 XML 네임스페이스를 가져와서 XML 리터럴의 성능 최적화를 활용합니다.  
  
-   XML 축 속성을 사용하여 XML 문서의 요소 및 특성에 액세스합니다.  
  
-   `Add` 메서드와 같은 API 호출을 사용하는 대신 포함 식을 사용하여 값을 포함하고 기존 값에서 XML을 만듭니다.  
  
     [!code-vb[VbVbalrGuidelines#27](../../../visual-basic/programming-guide/program-structure/codesnippet/visualbasic/VBProject/Class1.vb#27)]  
  
### LINQ 쿼리  
  
-   쿼리 변수에 의미 있는 이름을 사용합니다.  
  
     [!code-vb[VbVbalrGuidelines#28](../../../visual-basic/programming-guide/program-structure/codesnippet/visualbasic/VBProject/Class1.vb#28)]  
  
-   쿼리의 요소에 이름을 제공하여 익명 형식의 속성 이름이 파스칼식 대\/소문자에 따라 올바로 대문자로 표시되도록 합니다.  
  
     [!code-vb[VbVbalrGuidelines#29](../../../visual-basic/programming-guide/program-structure/codesnippet/visualbasic/VBProject/Class1.vb#29)]  
  
-   결과의 속성 이름이 모호한 경우 속성 이름을 바꿉니다.  예를 들어 쿼리에서 고객 이름과 주문 ID를 반환하는 경우 결과에서 `Name` 및 `ID`로 남겨두지 않고 다음과 같이 이름을 바꿉니다.  
  
     [!code-vb[VbVbalrGuidelines#30](../../../visual-basic/programming-guide/program-structure/codesnippet/visualbasic/VBProject/Class1.vb#30)]  
  
-   쿼리 변수 및 범위 변수의 선언에서 형식 유추를 사용합니다.  
  
     [!code-vb[VbVbalrGuidelines#31](../../../visual-basic/programming-guide/program-structure/codesnippet/visualbasic/VBProject/Class1.vb#31)]  
  
-   쿼리 절을 `From` 문 아래에 정렬합니다.  
  
     [!code-vb[VbVbalrGuidelines#32](../../../visual-basic/programming-guide/program-structure/codesnippet/visualbasic/VBProject/Class1.vb#32)]  
  
-   다른 쿼리 절 앞에 `Where` 절을 사용하여 나중 쿼리 절이 필터링된 데이터 집합에 대해 실행되게 합니다.  
  
     [!code-vb[VbVbalrGuidelines#33](../../../visual-basic/programming-guide/program-structure/codesnippet/visualbasic/VBProject/Class1.vb#33)]  
  
-   `Join` 절을 사용하여 조인 작업을 암시적으로 정의하는 대신 `Where` 절을 사용하여 조인 작업을 명시적으로 정의합니다.  
  
     [!code-vb[VbVbalrGuidelines#34](../../../visual-basic/programming-guide/program-structure/codesnippet/visualbasic/VBProject/Class1.vb#34)]  
  
## 참고 항목  
 [보안 코딩 지침](../Topic/Secure%20Coding%20Guidelines.md)