---
title: "Lifetime in Visual Basic | Microsoft Docs"
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
  - "static variables, lifetime"
  - "static variables, Visual Basic"
  - "declared elements, lifetime"
  - "Shared variable lifetime"
  - "lifetime, declared elements"
  - "lifetime, Visual Basic"
  - "lifetime"
ms.assetid: bd91e390-690a-469a-9946-8dca70bc14e7
caps.latest.revision: 14
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 14
---
# Lifetime in Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

선언 요소의 *수명*은 선언 요소를 사용할 수 있는 기간을 의미합니다.  변수는 수명이 있는 유일한 요소입니다.  이를 위해 컴파일러에서는 프로시저 매개 변수와 함수 반환 값을 특별한 경우의 변수로 간주합니다.  변수의 수명은 변수가 값을 가질 수 있는 기간을 나타냅니다.  이 기간 동안 변수의 값은 변할 수 있지만 항상 어떤 값을 가집니다.  
  
## 여러 가지 수명  
 프로시저 밖의 모듈 수준에서 선언된 *멤버 변수*는 일반적으로 해당 변수가 선언된 요소와 수명이 동일합니다.  클래스나 구조체에서 선언된 비공유 변수는 해당 변수가 선언된 클래스나 구조체의 각 인스턴스에 대한 개별적인 복사본으로 존재합니다.  따라서 각 변수와 인스턴스는 수명이 동일합니다.  그러나, `Shared` 변수는 응용 프로그램이 실행되는 전체 기간 동안 지속되는 하나의 수명만을 가집니다.  
  
 프로시저 내에 선언된 *지역 변수*는 지역 변수가 선언된 프로시저가 실행되는 동안에만 존재합니다.  이는 해당 프로시저의 매개 변수와 모든 함수 반환 값에도 적용됩니다.  그러나, 이 프로시저가 다른 프로시저를 호출하는 경우 호출된 프로시저가 실행되는 동안 지역 변수 값은 유지됩니다.  
  
## 수명의 시작  
 지역 변수의 수명은 지역 변수가 선언된 프로시저로 제어가 전달될 때 시작됩니다.  모든 지역 변수는 프로시저가 실행되기 시작하는 즉시 해당 데이터 형식의 기본값으로 초기화됩니다.  프로시저가 초기 값을 지정하는 `Dim` 문을 만나면 코드에서 이미 다른 값을 해당 변수에 할당했을 경우에도 해당 값에 해당 변수를 설정합니다.  
  
 구조체 변수의 각 멤버는 마치 개별적인 변수인 것처럼 초기화됩니다.  이와 비슷하게 배열 변수의 각 요소도 개별적으로 초기화됩니다.  
  
 프로시저 내의 블록에 선언된 `For` 루프 등의 변수는 프로시저가 실행되기 시작할 때 초기화됩니다.  이러한 초기화는 코드에서 해당 블록을 실행하는지 여부에 관계없이 적용됩니다.  
  
## 수명의 종료  
 프로시저가 종료되면 해당 지역 변수의 값이 소실되고 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서는 이 지역 변수에서 사용하던 메모리를 회수합니다.  다음에 프로시저를 호출하면 모든 지역 변수가 다시 만들어지고 초기화됩니다.  
  
 클래스나 구조체의 인스턴스가 종료되면 비공유 변수의 메모리 및 값이 소실됩니다.  클래스 또는 구조체의 새 인스턴스는 각각 해당 비공유 변수를 만들고 초기화합니다.  `Shared` 변수는 응용 프로그램 실행이 중지될 때까지 보존됩니다.  
  
## 수명의 연장  
 `Static` 키워드를 사용하여 지역 변수를 선언한 경우 지역 변수의 수명은 해당 프로시저의 실행 시간보다 깁니다.  다음 표에서는 프로시저 선언에 따라 `Static` 변수의 수명이 결정되는 방법을 보여 줍니다.  
  
|프로시저 위치 및 공유 여부|Static 변수의 수명 시작|Static 변수의 수명 종료|  
|---------------------|----------------------|----------------------|  
|모듈. 기본적으로 shared|프로시저가 처음 호출될 때|응용 프로그램의 실행이 중지될 때|  
|클래스. `Shared`\(프로시저는 인스턴스 멤버가 아님\)|프로시저가 특정 인스턴스나 클래스 또는 구조체 이름에 대해 처음 호출될 때|응용 프로그램의 실행이 중지될 때|  
|클래스의 인스턴스. `Shared` 아님\(프로시저는 인스턴스 멤버임\)|프로시저가 특정 인스턴스에 대해 처음 호출될 때|인스턴스가 GC\(가비지 수집\)를 위해 해제될 때|  
  
## 동일한 이름의 정적 변수  
 둘 이상의 프로시저에서 이름이 같은 정적 변수를 선언할 수 있습니다.  이 경우 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] 컴파일러에서는 각 변수를 개별 요소로 간주합니다.  따라서 그 중 한 변수를 초기화하더라도 다른 변수 값에는 영향을 주지 않습니다.  이것은 일련의 오버로드로 프로시저를 정의하고 각 오버로드에 이름이 같은 정적 변수를 선언하는 경우에도 마찬가지입니다.  
  
## 정적 변수를 포함하는 요소  
 클래스에서, 즉 해당 클래스의 프로시저 내에서 정적 지역 변수를 선언할 수 있습니다.  그러나 구조체에서는 정적 지역 변수를 해당 구조체에 있는 프로시저의 구조체 멤버나 지역 변수로 선언할 수 없습니다.  
  
## 예제  
  
### 설명  
 다음 예제에서는 [Static](../../../../visual-basic/language-reference/modifiers/static.md) 키워드를 사용하여 변수를 선언합니다.  [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md)에서 `Static`과 같은 한정자를 사용하는 경우에는 `Dim` 키워드를 사용하지 않아도 됩니다.  
  
### 코드  
 [!code-vb[VbVbalrKeywords#13](../../../../visual-basic/language-reference/codesnippet/visualbasic/lifetime_1.vb)]  
  
### 설명  
 위 예제에서 변수 `applesSold`는 `runningTotal` 프로시저가 호출 코드로 돌아간 후에도 계속해서 존재합니다.  다음에 `runningTotal`이 호출될 때 `applesSold`는 이전에 계산된 값을 유지합니다.  
  
 `Static`를 사용하지 않고 `applesSold`를 선언한 경우에는 `runningTotal`을 호출할 때마다 이전의 누적 값이 보존되지 않습니다.  다음에 `runningTotal`이 호출될 때 `applesSold`가 다시 만들어지고 0으로 초기화되며 `runningTotal`은 단지 해당 프로시저가 호출될 때의 값을 반환합니다.  
  
### 코드 컴파일  
 정적 지역 변수의 값을 선언의 일부로 초기화할 수 있습니다.  배열을 `Static`으로 선언하면 차수\(차원 수\), 각 차원의 길이 및 개별 요소의 값을 초기화할 수 있습니다.  
  
### 보안  
 위 예제의 모듈 수준에서 `applesSold`를 선언하여 같은 수명을 얻을 수 있습니다.  그러나 이 방법으로 변수의 범위를 변경하면 프로시저가 더 이상 변수에 단독으로 액세스할 수 없게 됩니다.  이 상태에서는 다른 프로시저가 `applesSold`에 액세스하여 값을 변경할 수 있기 때문에 누계를 신뢰할 수 없고 코드 관리가 더욱 어려워질 수 있습니다.  
  
## 참고 항목  
 [Shared](../../../../visual-basic/language-reference/modifiers/shared.md)   
 [Nothing](../../../../visual-basic/language-reference/nothing.md)   
 [Declared Element Names](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)   
 [References to Declared Elements](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)   
 [Scope in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)   
 [Access Levels in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)   
 [Variables](../../../../visual-basic/programming-guide/language-features/variables/index.md)   
 [변수 선언](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)   
 [Troubleshooting Data Types](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)   
 [Static](../../../../visual-basic/language-reference/modifiers/static.md)