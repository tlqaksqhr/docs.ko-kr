---
title: "Error Messages (Visual Basic) | Microsoft Docs"
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
  - "errors [Visual Basic]"
  - "error messages"
  - "trappable errors"
  - "errors [Visual Basic], trappable"
ms.assetid: f2dda05b-baef-41f5-8bb1-598bd7cf239f
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# Error Messages (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

작성, 컴파일, 또는 Visual Basic 응용 프로그램을 실행 하면 다음과 같은 유형의 오류가 발생할 수 있습니다.  
  
1.  디자인 타임 오류 Visual Studio 응용 프로그램을 작성 하는 경우에 발생 합니다.  
  
2.  컴파일 타임 오류 Visual Studio 또는 명령 프롬프트에서 응용 프로그램을 컴파일하는 경우에 발생 합니다.  
  
3.  런타임 오류 Visual Studio 또는 독립 실행형 실행 파일로 응용 프로그램을 실행 하는 경우에 발생 합니다.  
  
 특정 오류를 해결 하는 방법에 대 한 자세한 내용은 [Additional Resources for Visual Basic Programmers](../../../visual-basic/getting-started/additional-resources.md).  
  
## 런타임 오류  
 Visual Basic 응용 프로그램에서 시스템이 실행할 수 없는 작업을 수행 하려고 하면 런타임 오류가 발생 하 고 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] throw는 `Exception` 개체입니다.  [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서는 `Throw` 문을 사용하여 `Exception` 개체를 비롯한 모든 데이터 형식의 사용자 지정 오류를 생성할 수 있습니다.  응용 프로그램의 오류 번호와 메시지를 catch 된 예외를 표시 하 여 오류를 식별할 수 있습니다.  오류가 catch 되지 않으면 응용 프로그램을 종료 합니다.  
  
 코드를 잡고 런타임 오류 검사 수 있습니다.  오류를 생성 하는 코드를 묶습니다 경우는 `Try` 블록 내의 일치 하는 발생된 하는 오류를 catch 할 수 `Catch` 블록.  런타임에 오류를 포착 하 고 코드에 대처 하는 방법에 대 한 자세한 내용은 [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).  
  
## 컴파일 타임 오류  
 Visual Basic 컴파일러는 코드에서 문제가 발견 되 면 컴파일 타임 오류가 발생 합니다.  코드 편집기에서 물결선 코드의 해당 줄에서 나타나기 때문에 코드 줄을 오류를 일으킨 쉽게 식별할 수 있습니다.  물결 모양 밑줄 또는 열기를 가리킬 경우 오류 메시지가 나타납니다의  **오류 목록**, 다른 메시지도 표시 합니다.  
  
 물결 모양의 밑줄이 있는 식별자가 맨 오른쪽 문자 아래에 짧은 밑줄 표시 경우 스텁 클래스, 생성자, 메서드, 속성, 필드 또는 열거형을 생성할 수 있습니다.  자세한 내용은 [관례에서 생성](/visual-cpp/misc/generate-from-usage)을 참조하십시오.  
  
 Visual Basic 컴파일러에서 경고를 확인 하 여 더 빠르게 실행 하 고 버그가 거의 없는 코드를 작성할 수 있습니다.  이러한 경고는 응용 프로그램이 실행 될 때 오류를 일으키는 코드를 식별 합니다.  예를 들어, 사용자가 할당 되지 않은 개체 변수의 멤버를 호출 하면 반환 값을 설정 하지 않고 함수에서 반환 또는 실행 컴파일러에서 경고를 `Try` 블록에서 예외를 catch 하는 논리 오류가 발생 합니다.  경고를 설정 및 해제 하는 방법 등에 대 한 자세한 내용은 [Visual Basic에서 경고 구성](/visual-studio/ide/configuring-warnings-in-visual-basic).