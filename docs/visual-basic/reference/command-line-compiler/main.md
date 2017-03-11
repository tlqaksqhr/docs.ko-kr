---
title: "/main | Microsoft Docs"
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
  - "main compiler option [Visual Basic]"
  - "/main compiler option [Visual Basic]"
  - "-main compiler option [Visual Basic]"
ms.assetid: 83fc339d-6652-415d-b205-b5133319b5b0
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# /main
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

`Sub Main` 프로시저를 포함하는 클래스나 모듈을 지정합니다.  
  
## 구문  
  
```  
/main:location  
```  
  
## 인수  
 `location`  
 필수 요소.  프로그램이 시작될 때 호출되는 `Sub Main` 프로시저가 들어 있는 클래스나 모듈의 정규화된 위치입니다.  이 위치의 형식은 **\/main:module** 또는 **\/main:namespace.module**입니다.  
  
## 설명  
 실행 파일이나 Windows 실행 프로그램을 만들 때 이 옵션을 사용합니다.  **\/main** 옵션을 생략하면 컴파일러가 모든 공용 클래스와 모듈에서 유효한 공유 `Sub Main`을 검색합니다.  
  
 여러 가지 형식의 `Main` 프로시저에 대한 자세한 내용은 [Main Procedure in Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md)를 참조하십시오.  
  
 `location`이 <xref:System.Windows.Forms.Form>을 상속하는 클래스이면 컴파일러에서 클래스에 `Main` 프로시저가 없는 경우 응용 프로그램을 시작하는 기본 `Main` 프로시저를 제공합니다.  이를 통해 개발 환경에서 작성된 명령줄에서 코드를 컴파일할 수 있습니다.  
  
 [!code-vb[VbVbalrCompiler#16](../../../visual-basic/reference/command-line-compiler/codesnippet/visualbasic/main_1.vb)]  
  
### Visual Studio 통합 개발 환경에서 \/main을 설정하려면  
  
1.  **솔루션 탐색기**에서 프로젝트를 선택합니다.  **프로젝트** 메뉴에서 **속성**을 선택합니다.  
  
     자세한 내용은 [Introduction to the Project Designer](http://msdn.microsoft.com/ko-kr/898dd854-c98d-430c-ba1b-a913ce3c73d7)를 참조하십시오.  
  
2.  **응용 프로그램** 탭을 클릭합니다.  
  
3.  **응용 프로그램 프레임워크 사용** 확인란이 선택되어 있는지 확인합니다.  
  
4.  **시작 개체** 상자의 값을 수정합니다.  
  
## 예제  
 다음 코드에서는 `T2.vb`와 `T3.vb`를 컴파일하여 `Sub Main` 프로시저를 `Test2` 클래스에서 찾을 수 있도록 지정합니다.  
  
```  
vbc t2.vb t3.vb /main:Test2  
```  
  
## 참고 항목  
 [Visual Basic Command\-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [\/target](../../../visual-basic/reference/command-line-compiler/target.md)   
 [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [NIB: Visual Basic Version of Hello, World](http://msdn.microsoft.com/ko-kr/9d030b60-e148-4366-a462-69532f02294c)   
 [Main Procedure in Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md)