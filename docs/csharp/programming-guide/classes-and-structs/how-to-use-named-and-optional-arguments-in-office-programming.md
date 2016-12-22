---
title: "방법: Office 프로그래밍에 명명된 인수와 선택적 인수 사용(C# 프로그래밍 가이드) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "명명된 인수 및 선택적 인수[C#], Office 프로그래밍"
  - "명명된 인수[C#], Office 프로그래밍"
  - "선택적 인수[C#], Office 프로그래밍"
ms.assetid: 65b8a222-bcd8-454c-845f-84adff5a356f
caps.latest.revision: 34
caps.handback.revision: 34
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 방법: Office 프로그래밍에 명명된 인수와 선택적 인수 사용(C# 프로그래밍 가이드)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

[!INCLUDE[csharp_dev10_long](../../../csharp/programming-guide/classes-and-structs/includes/csharp_dev10_long_md.md)]에 도입된 명명된 인수 및 선택적 인수는 C\# 프로그래밍의 편리성, 유연성 및 가독성을 향상시켜 줍니다. 또한 이러한 기능은 Microsoft Office 자동화 API 같은 COM 인터페이스에 매우 쉽게 액세스할 수 있게 해 줍니다.  
  
 다음 예제에서 [ConvertToTable](http://go.microsoft.com/fwlink/?LinkId=145378) 메서드에는 열 및 행의 개수, 서식, 테두리, 글꼴, 색상 같은 표의 특징을 나타내는 매개 변수 16개가 있습니다.  대부분의 경우 모든 매개 변수에 대해 특정 값을 지정할 필요는 없기 때문에 16개 매개 변수가 모두 선택적입니다.  그러나 명명된 인수 및 선택적 인수가 없으면 각 매개 변수에 대해 값 또는 자리 표시자 값이 제공되어야 합니다.  명명된 인수 및 선택적 인수를 사용하면 프로젝트에 필요한 매개 변수에 대해서만 값을 지정할 수 있습니다.  
  
 다음 절차를 완료하려면 Microsoft Office Word가 컴퓨터에 설치되어 있어야 합니다.  
  
 [!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
### 새 콘솔 응용 프로그램을 만들려면  
  
1.  Visual Studio를 시작합니다.  
  
2.  **파일** 메뉴에서 **새로 만들기**를 가리킨 다음 **프로젝트**를 클릭합니다.  
  
3.  **템플릿 범주** 창에서 **Visual C\#**을 확장한 다음 **Windows**를 클릭합니다.  
  
4.  **템플릿** 창 맨 위에 있는 **대상 프레임워크** 상자에 **.NET Framework 4**가 표시되어 있는지 확인합니다.  
  
5.  **템플릿** 창에서 **콘솔 응용 프로그램**을 클릭합니다.  
  
6.  **이름** 필드에 프로젝트 이름을 입력합니다.  
  
7.  **확인**을 클릭합니다.  
  
     **솔루션 탐색기**에 새 프로젝트가 나타납니다.  
  
### 참조를 추가하려면  
  
1.  **솔루션 탐색기**에서 프로젝트 이름을 마우스 오른쪽 단추로 클릭하고 **참조 추가**를 클릭합니다.  **참조 추가** 대화 상자가 나타납니다.  
  
2.  **.NET** 페이지의 **구성 요소 이름** 목록에서 **Microsoft.Office.Interop.Word**를 선택합니다.  
  
3.  **확인**을 클릭합니다.  
  
### 필요한 using 지시문을 추가하려면  
  
1.  **솔루션 탐색기**에서 **Program.cs** 파일을 마우스 오른쪽 단추로 클릭하고 **코드 보기**를 클릭합니다.  
  
2.  코드 파일의 맨 위에 다음 `using` 지시문을 추가합니다.  
  
     [!CODE [csProgGuideNamedAndOptional#4](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidenamedandoptional#4)]  
  
### Word 문서에 텍스트를 표시하려면  
  
1.  Program.cs의 `Program` 클래스에서 다음 메서드를 추가하여 Word 응용 프로그램 및 Word 문서를 만듭니다.  [Add](http://go.microsoft.com/fwlink/?LinkId=145381) 메서드에는 선택적 매개 변수가 4개 있습니다.  이 예제에서는 각 매개 변수의 기본값이 사용됩니다.  따라서, 메서드 호출문에서 인수가 전혀 필요하지 않습니다.  
  
     [!CODE [csProgGuideNamedAndOptional#6](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidenamedandoptional#6)]  
  
2.  메서드 끝부분에 다음 코드를 추가하여 문서에서 텍스트를 표시할 위치 및 표시할 텍스트를 정의합니다.  
  
     [!CODE [csProgGuideNamedAndOptional#7](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidenamedandoptional#7)]  
  
### 응용 프로그램을 실행하려면  
  
1.  다음 문을 Main에 추가합니다.  
  
     [!CODE [csProgGuideNamedAndOptional#8](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidenamedandoptional#8)]  
  
2.  Ctrl\+F5를 눌러 프로젝트를 실행합니다.  지정된 텍스트를 포함하는 Word 문서가 나타납니다.  
  
### 텍스트를 표로 변경하려면  
  
1.  `ConvertToTable` 메서드를 사용하여 표에서 텍스트를 둘러쌉니다.  이 메서드에는 선택적 매개 변수가 16개 있습니다.  다음 그림과 같이 IntelliSense에서는 선택적 매개 변수를 괄호로 둘러쌉니다.  
  
     ![ConvertToTable 메서드의 매개 변수 목록](../../../csharp/programming-guide/classes-and-structs/media/convert_tableparameters.png "Convert\_TableParameters")  
ConvertToTable 매개 변수  
  
     명명된 인수와 선택적 인수를 사용하면 변경할 매개 변수에 대해서만 값을 지정할 수 있습니다.  `DisplayInWord` 메서드의 끝부분에 다음 코드를 추가하여 간단한 표를 만듭니다.  이 인수는 `range`의 텍스트 문자열에 있는 쉼표로 표의 셀이 구분되도록 지정합니다.  
  
     [!CODE [csProgGuideNamedAndOptional#9](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidenamedandoptional#9)]  
  
     이전 버전의 C\#에서 `ConvertToTable`을 호출하려면 다음 코드와 같이 각 매개 변수에 대한 참조 인수가 필요합니다.  
  
     [!CODE [csProgGuideNamedAndOptional#14](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidenamedandoptional#14)]  
  
2.  Ctrl\+F5를 눌러 프로젝트를 실행합니다.  
  
### 다른 매개 변수를 사용하여 테스트하려면  
  
1.  표에 열 1개와 행 3개가 있도록 변경하려면 `DisplayInWord`에서 마지막 줄을 다음 문으로 바꾼 다음 Ctrl\+F5를 누릅니다.  
  
     [!CODE [csProgGuideNamedAndOptional#10](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidenamedandoptional#10)]  
  
2.  미리 정의된 서식을 표에 지정하려면 `DisplayInWord`에서 마지막 줄을 다음 문으로 바꾼 다음 Ctrl\+F5를 누릅니다.  서식은 [WdTableFormat](http://go.microsoft.com/fwlink/?LinkId=145382) 상수 중 하나일 수 있습니다.  
  
     [!CODE [csProgGuideNamedAndOptional#11](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidenamedandoptional#11)]  
  
## 예제  
 다음 코드에는 전체 예제가 포함되어 있습니다.  
  
 [!CODE [csProgGuideNamedAndOptional#12](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidenamedandoptional#12)]  
  
## 참고 항목  
 [명명된 인수 및 선택적 인수](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md)